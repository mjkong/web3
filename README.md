# React 를 이용하여 Dapp 개발하기

## 사전 준비 사항
  * Nodejs >=6 이상 설치
  * 개발을 위한 Ethereum 노드
  * HelloWorld 스마트 컨트랙트 배포

배포된 스마트 컨트랙트 정보를 확인합니다.   
* 계약 주소
![](./images/contract_address.png)

* ABI 정보
![](./images/abi_info.png)

## React 설치
React 설치 후 프로젝트를 생성합니다. 

~~~shell
npm install -g create-react-app
create-react-app helloworld_app

cd helloworld_app
~~~

프로젝트 생성 후 `src` 디렉토리에 있는 모든 `.js`파일을 삭제합니다.
~~~shell
cd src
rm -rf *.js
~~~

이더리움 노드와 연동을 위해서 `Web3`를 설치합니다.

~~~shell
cd ../
npm install --save web3@1.0.0-beta.26
~~~

`Web3` 초기화 및 접속을 위해서 `src/web3.js` 파일 생성 후 다음의 코드를 입력합니다.

>> HttpProvider의 IP 주소는 접속하고자 하는 노드의 주소입니다.   

~~~javascript
import Web3 from 'web3';

const web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));
export default web3;
~~~