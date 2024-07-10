#lệnh 1
# FROM node:17-alpine

# WORKDIR /app

# COPY . .

# RUN npm install

# # Lệnh này chỉ định cổng mà container sẽ lắng nghe thời gian chạy.
# EXPOSE 4000 

# # Lệnh này chỉ định lệnh mặc định để chạy khi container khởi động.
# CMD ["node", "app.js"]


#lệnh 2
FROM node:17-alpine

RUN npm install -g nodemon

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

# Lệnh này chỉ định cổng mà container sẽ lắng nghe thời gian chạy.
EXPOSE 4000 

# Lệnh này chỉ định lệnh mặc định để chạy khi container khởi động.
CMD ["npm", "run", "dev"]

# Lệnh 2 tối ưu hơn vì:
# 1. Sử dụng cache hiệu quả hơn:
#    - COPY package.json .` và `RUN npm install` trước khi sao chép toàn bộ mã nguồn giúp Docker sử dụng lại cache nếu chỉ có mã nguồn thay đổi, không phải cài đặt lại các gói.
# Trong khi đó, lệnh 1 sẽ cài đặt lại các gói mỗi khi có thay đổi trong mã nguồn, làm tăng thời gian build.