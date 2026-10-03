FROM python:3.11-slim
RUN pip install --no-cache-dir "laya[serve]"
ENV LAYA_HOST=0.0.0.0 LAYA_PORT=8000
EXPOSE 8000
HEALTHCHECK --interval=30s --timeout=5s --start-period=120s \
  CMD python -c "import urllib.request,sys; sys.exit(0 if urllib.request.urlopen('http://127.0.0.1:8000/health',timeout=5).status==200 else 1)"
CMD ["laya-serve"]