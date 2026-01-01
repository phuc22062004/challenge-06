## Yêu Cầu Hệ Thống

Trước khi bắt đầu, bạn cần cài đặt các công cụ sau:

- [Node.js (>= v20.18.3)](https://nodejs.org/en/download/)
- [Yarn (v1 hoặc v2+)](https://yarnpkg.com/getting-started/install)
- [Git](https://git-scm.com/downloads)

## Hướng Dẫn Chạy Code Từng Bước

### Bước 1: Cài Đặt Dependencies

Mở terminal và chạy lệnh sau để cài đặt tất cả các package cần thiết:

```bash
yarn install
```


### Bước 2: Khởi Động Local Blockchain

Mở một terminal mới và chạy lệnh sau để khởi động mạng blockchain local (Hardhat Network):

```bash
yarn chain
```


### Bước 3: Deploy Smart Contracts

Mở một terminal thứ hai và chạy lệnh sau để deploy các smart contracts lên local blockchain:

```bash
yarn deploy
```


### Bước 4: Khởi Động Frontend

Mở một terminal thứ ba và chạy lệnh sau để khởi động ứng dụng frontend:

```bash
yarn start
```


### Bước 5: Truy Cập Ứng Dụng

Mở trình duyệt và truy cập:

```
http://localhost:3000
```


### Bước 6: Lấy ETH từ Faucet (Nếu Cần)

Nếu bạn cần ETH để test, có thể lấy từ local faucet:

1. Trong ứng dụng, tìm phần **"Faucet"** hoặc **"Get ETH"**
2. Click vào nút để nhận ETH miễn phí cho tài khoản của bạn


## Deploy Lên Testnet

### Bước 1: Tạo Deployer Account

```bash
yarn generate
```

Lệnh này sẽ tạo một mnemonic và lưu locally.

### Bước 2: Xem Thông Tin Account

```bash
yarn account
```

### Bước 3: Gửi ETH vào Deployer Account

Bạn cần gửi ETH vào deployer address từ ví của bạn hoặc từ faucet của testnet.

### Bước 4: Cấu Hình Network

Mở file `packages/hardhat/hardhat.config.ts` và chỉnh `defaultNetwork` thành network bạn muốn deploy (ví dụ: `sepolia`, `optimismSepolia`).

### Bước 5: Deploy Lên Testnet

```bash
yarn deploy --network sepolia
```

Hoặc:

```bash
yarn deploy --network optimismSepolia
```

## Deploy Frontend Lên Vercel

### Bước 1: Cấu Hình Frontend Network

Mở file `packages/nextjs/scaffold.config.ts` và chỉnh `targetNetwork` thành network bạn đã deploy contracts (ví dụ: `chains.sepolia`).

### Bước 2: Đăng Nhập Vercel

```bash
yarn vercel:login
```

### Bước 3: Deploy Frontend

```bash
yarn vercel
```

## Verify Smart Contracts trên Etherscan

Sau khi deploy lên testnet, verify contracts:

```bash
yarn verify --network sepolia
```

Hoặc:

```bash
yarn verify --network optimismSepolia
```