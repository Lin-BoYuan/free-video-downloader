1. 部署后端
```bash
    cd backend
    docker build -t free-video-downloader-backend .

    docker run -d \
    --name free-video-downloader-backend \
    --env-file .env \
    -v db-data:/app/data \
    -p 8000:8000 \
    free-video-downloader-backend
```
2. 部署前端
```bash
    cd frontend
    docker build -t free-video--downloader-frontend .

    docker run -d \
    --name free-video--downloader-frontend  \
    -e BACKEND_URL=http://192.168.1.15:8000 \
    -p 9999:80 \
    free-video-downloader-frontend 
```