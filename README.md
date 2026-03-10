# Blockchain Lab #2 - Ethereum RPC Practice

## 1. 실습 목적

이번 실습의 목적은 **Ethereum 블록체인과 프로그램이 통신하는 방식**을 이해하는 것이다.  
특히 RPC(Remote Procedure Call)를 이용하여 블록체인 데이터를 가져오는 방법을 실습하였다.

이번 실습에서는 다음 두 가지 방법을 사용하였다.

1. **Raw JSON-RPC 방식**
2. **ethers.js 라이브러리 사용 방식**

이를 통해 **저수준 RPC 호출 방식과 라이브러리를 이용한 방식의 차이**를 이해하는 것을 목표로 한다.

---

## 2. 사용 기술

- Node.js
- Infura (Ethereum RPC Provider)
- JSON-RPC
- ethers.js
- Git / GitHub

---

## 3. 프로젝트 구조
blockchain0310
├ json-rpc
│ └ index.js
├ ethers
│ └ index.js
├ package.json
├ package-lock.json
└ README.md

---

## 4. JSON-RPC 방식

JSON-RPC 방식은 **Ethereum 노드에 직접 HTTP 요청을 보내 블록체인 데이터를 가져오는 방식**이다.

Infura에서 제공하는 RPC endpoint를 이용하여 **최신 Ethereum 블록 번호**를 조회하였다.

동작 과정

1. Infura RPC 서버에 요청 전송
2. `eth_blockNumber` 메서드 호출
3. 최신 블록 번호 반환

실행 방법
node json-rpc/index.js


---

## 5. ethers.js 방식

ethers.js는 **Ethereum 블록체인과 쉽게 상호작용할 수 있도록 만든 JavaScript 라이브러리**이다.

JSON-RPC 요청을 직접 작성하지 않고도 간단한 코드로 블록체인 데이터를 조회할 수 있다.

동작 과정

1. ethers.js provider 생성
2. Infura RPC endpoint 연결
3. `getBlockNumber()` 함수로 최신 블록 조회

실행 방법
node ethers/index.js


---

## 6. JSON-RPC vs ethers.js

| 방식 | 특징 |
|-----|-----|
| JSON-RPC | 저수준 방식, 직접 HTTP 요청 작성 |
| ethers.js | 고수준 라이브러리, 코드가 간단 |

ethers.js를 사용하면 JSON-RPC 요청을 직접 작성하지 않아도 되기 때문에 **개발이 훨씬 편리하다**.

---

## 7. 실행 방법

### 의존성 설치
npm install

### JSON-RPC 실행


node json-rpc/index.js


### ethers.js 실행


node ethers/index.js


---

## 8. 실습 결과

두 가지 방식 모두 **Ethereum 메인 네트워크의 최신 블록 번호를 정상적으로 조회**하는 것을 확인하였다.

이를 통해 **블록체인 데이터를 프로그램에서 가져오는 기본적인 방법과 RPC 통신 구조**를 이해할 수 있었다.
