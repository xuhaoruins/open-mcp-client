FROM ghcr.io/astral-sh/uv:python3.12-bookworm-slim

WORKDIR /app

# 安装依赖
COPY . /app/
RUN pip install poetry
RUN poetry config virtualenvs.create false
RUN poetry install --without dev

# 暴露端口
EXPOSE 8123

# 启动服务
CMD ["langgraph", "serve", "--host", "0.0.0.0", "--port", "8123"] 