# Demo

<!-- TOC -->
* [Demo](#demo)
  * [Goal](#goal)
  * [Fundamentals](#fundamentals)
    * [Setup Environment](#setup-environment)
    * [Setup Project](#setup-project)
    * [Next.js](#nextjs)
    * [FastAPI](#fastapi)
    * [Integration](#integration)
  * [TestOps](#testops)
    * [BDD/SBE](#bddsbe)
    * [Playwright](#playwright)
    * [Behave](#behave)
    * [TDD](#tdd)
    * [Jest](#jest)
    * [PyTest](#pytest)
    * [Allure Report](#allure-report)
  * [DevOps](#devops)
    * [Vercel](#vercel)
    * [GKE](#gke)
    * [GitHub Actions](#github-actions)
<!-- TOC -->

## Goal

- [ ] Fundamentals
  - [ ] Learn [Next.js] + [FastAPI] integration
- [ ] TestOps
  - [ ] Add BDD/SBE example using [Playwright] & [Behave]
  - [ ] Add TDD example using [Jest] & [PyTest] 
  - [ ] Add [Allure] to integrate test reports
- [ ] DevOps
  - [ ] Deploy to Vercel
  - [ ] Deploy to GKE
  - [ ] Add GitHub Actions

## Fundamentals

### Setup Environment

彙整 安裝並管理 `${ENV}` 等相依套件 `in macos zshrc` 的最佳作法 與 指令

- `Next.js: React, Node.js, TypeScript, nvm, pnpm/npx; ESLint, Prettier`
  - [nvm](https://github.com/nvm-sh/nvm), [pnpm](https://github.com/pnpm/pnpm)
    - [lazynvm.sh](https://gist.github.com/fl0w/07ce79bd44788f647deab307c94d6922)
    - [淺談 JS 生態系的套件管理機制與發展](https://oldmo860617.medium.com/淺談-js-生態系的套件管理機制與發展-5cb10b7e2f72)
    - [PNPM — 更優化的套件管理工具](https://blog.twjoin.com/pnpm-更優化的套件管理工具-1cc5576c53c3)
    - [指令 npm cli & package.json](https://pjchender.dev/npm/npm-cli-and-package-json/)
    - [指令 pnpm](https://pjchender.dev/npm/npm-pnpm-cli/)
  - [ESLint](https://eslint.org/docs/latest/use/getting-started)
    - [Understanding ESLint Configuration: .eslintrc.js vs .eslintrc vs .eslintrc.json](https://medium.com/@ritz.sh/understanding-eslint-configuration-eslintrc-js-vs-eslintrc-vs-eslintrc-json-287ec5e95bf4)
    - [VS Code 安裝 Prettier、ESLint](https://medium.com/@ars37111337/vs-code-%E5%AE%89%E8%A3%9D-prettier-eslint-70dbb12c5cab)
    - https://nextjs.tw/docs/basic-features/eslint
    - https://github.com/jsx-eslint/eslint-plugin-react
    - https://github.com/airbnb/javascript
  - Ref
    - [monorepo: pnpm + eslint + prettier + husky + lintstaged + commitlint + changesets](https://github.com/muravjev/configs)
    - [pnpm搭建Monorepo工程涵盖集成ts + eslint + prettier + husky + lint-staged + commitizen](https://juejin.cn/post/7358398963840647219)
- `FastAPI: python3, pyenv, pip`

```sh
# DO NOT use homebrew to install nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
source ~/.zshrc
nvm --version   # 0.40.1
nvm install --lts  # 安裝最新 LTS 版本的 Node.js. 
nvm alias default node

node -v   # v22.12.0
npm -v    # 10.9.0 

npm install -g pnpm
pnpm --version    # 9.15.2
```

### Setup Project

- Check http://localhost:3000
  - `api/index.py`: http://localhost:3000/api/py/helloFastApi
  - `app/api/helloNextJs` http://localhost:3000/api/helloNextJs
  - FastApi: http://127.0.0.1:8000

```sh
git clone https://github.com/androchentw/nextjs-fastapi.git
cd nextjs-fastapi

python3 -m venv venv
source venv/bin/activate

pnpm install

# run the development server(python dependencies will be installed automatically here)
pnpm dev

# Additional

# code .eslintrc.json
pnpm add -D prettier eslint-config-prettier eslint-plugin-prettier
pnpm add -D @typescript-eslint/parser @typescript-eslint/eslint-plugin
pnpm add -D eslint-config-airbnb-base
pnpm update --latest

pnpm run lint   # 檢查程式碼規範問題
pnpm run format # 自動格式化程式碼
```

### Next.js

### FastAPI

### Integration

## TestOps

### BDD/SBE

### Playwright

### Behave

### TDD

### Jest

### PyTest

### Allure Report

## DevOps

### Vercel

### GKE

### GitHub Actions

<!-- Links -->

[Next.js]: https://github.com/vercel/next.js/
[FastAPI]: https://github.com/fastapi/fastapi
[Playwright]: https://github.com/microsoft/playwright
[Behave]: https://github.com/behave/behave 
[Jest]: https://github.com/jestjs/jest
[PyTest]: https://github.com/pytest-dev/pytest
[Allure]: https://github.com/allure-framework/allure2