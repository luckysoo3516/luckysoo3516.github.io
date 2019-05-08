---
layout: post
title : [Tutorial 따라하기] 로또 DApp 만들기 - (1)
---

# Lottery DApp 만들기 Tutorial - (1)
Youtube 채널 'dapp campus'의 Lottery Dapp 개발하기 영상을 본 후 작성하였습니다.
영상에 훨씬 자세하고 많은 설명이 있으니 꼭 영상을 보시기 바랍니다!

링크

macOS 10.14.4 Mojave를 기준으로 합니다.

### 1. 개발 환경 세팅
필수
node.js
vscode
truffle
ganache-cli
vscode - solidity extension

이미 설치되어 있기 때문에 설치 과정을 생략하겠습니다.

$truffle version
Truffle v5.0.12 (core: 5.0.12)
Solidity v0.5.0 (solc-js)
Node v10.15.1
Web3.js v1.0.0-beta.37

### 2. 작업할 디렉토리 생성

$ mkdir lottery-smart-contract
$ cd lottery-smart-contract
$ pwd
/Users/soomin/lecture-tutorial/lottery-smart-contract

### 3. 트러플 개발환경 초기화
lottery-smart-contract 디렉토리에서 다음 명령어를 실행합니다.
$ truffle init
$ ls -al
total 16
drwxr-xr-x  6 soomin  staff   192  5  9 01:48 .
drwxr-xr-x  5 soomin  staff   160  5  9 01:48 ..
drwxr-xr-x  3 soomin  staff    96  5  9 01:48 contracts
drwxr-xr-x  3 soomin  staff    96  5  9 01:48 migrations
drwxr-xr-x  2 soomin  staff    64  5  9 01:48 test
-rw-r--r--  1 soomin  staff  4233  5  9 01:48 truffle-config.js

contracts, migrations, test라는 디렉토리와 truffle-config.js라는 파일이 생성된 것을 볼 수 있습니다.

### 4. vscode로 해당 디렉토리 불러오기
$ code .

### 5. contracts 폴더 안에 Lottery.sol 파일 생성
Migration.sol 파일의 solidity 버전을 그대로 가져와 복붙한다.
contract 이름은 Lottery 이다.

pragma solidity >=0.4.21 <0.6.0;

contract Lottery {
    
}

vscode 단축키
New Terminal : control + shift + ₩

### 6. vscode 터미널에서 컴파일
$ truffle compile

Compiling your contracts...
===========================
> Compiling ./contracts/Lottery.sol
> Compiling ./contracts/Migrations.sol
> Artifacts written to /Users/soomin/lecture-tutorial/lottery-smart-contract/build/contracts
> Compiled successfully using:
   - solc: 0.5.0+commit.1d4f565a.Emscripten.clang
   
vscode에서 build 디렉토리가 새로 생성되고 그 안에 컴파일 된 컨트랙트의 정보가 담긴 json 파일이 생성된 것을 볼 수 있다.

