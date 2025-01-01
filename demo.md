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
    * [Playwright](#playwright)
    * [Jest](#jest)
    * [PyTest](#pytest)
    * [Allure Report](#allure-report)
  * [DevOps](#devops)
    * [Vercel](#vercel)
    * [GKE](#gke)
    * [GitHub Actions](#github-actions)
<!-- TOC -->

## Goal

- [x] Fundamentals
  - [x] Learn [Next.js] + [FastAPI] integration
- [ ] TestOps
  - [x] Add BDD/SBE example using [Playwright]
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

### Playwright

- https://playwright.dev/docs/intro
- [playwright-bdd](https://github.com/vitalets/playwright-bdd)
  - `npx bddgen && npx playwright test`
  - [Executing BDD tests with Playwright](https://willholmes.hashnode.dev/executing-bdd-tests-with-playwright)
  - [Generate BDD tests with ChatGPT and run them with Playwright]([https://medium.com/@vitaliypotapov/generate-bdd-tests-with-chatgpt-and-run-them-with-playwright-e1ce29d7a7bd](https://medium.com/@vitaliypotapov/generate-bdd-tests-with-chatgpt-and-run-them-with-playwright-e1ce29d7a7bd))
  - [Combine BDD with classic playwright tests](https://github.com/vitalets/playwright-bdd/issues/242)
- Ref
  - https://github.com/davidseow/how-to-playwright
  - [Understanding Playwright and Jest: A Strategic Guide for Effective Testing](https://medium.com/@saiyar.jo147th248/understanding-playwright-and-jest-a-strategic-guide-for-effective-testing-9d58c37c89f8)
- BDD/SBE
  - [SBE BDD TDD CDD](https://github.com/ProgramMurTw/pai-sensei/blob/main/tech/sbe-bdd-tdd-cdd.md#what-is-the-most-popular-an-useful-sbe-framework-being-used)

```sh
pnpm create playwright

pnpm exec playwright codegen

pnpm exec playwright test
# pnpm exec playwright test --ui

pnpm exec playwright show-report

# playwright-bdd
pnpm i -D playwright-bdd

# code features & steps
npx bddgen && npx playwright test

# check .features-gen/

# convert webm to gif to show video on GitHub
# ffmpeg -i video.webm -pix_fmt rgb24 output.gif
# gifsicle -O3 output.gif -o optimized.gif

find test-results/ -type f -name "*.webm" -exec bash -c 'ffmpeg -i "$0" -pix_fmt rgb8 "${0%.webm}.gif" && gifsicle --optimize=3 --batch "${0%.webm}.gif"' {} \;
```

<img style="width:60%;" src="test-results/nextjs-fastapi-demo-nextjs-fastapi-demo-firefox/video.gif" alt="">

Others

- [cucumber-js](https://github.com/cucumber/cucumber-js)
  - `pnpm add @cucumber/cucumber`
- [活文件 (living document) - Given When Then](https://alincode.github.io/learning-e2e-testing-with-python/living_document.html)
- [Behave介绍和快速示例](https://blog.csdn.net/oscar999/article/details/134431154) + Selenium
  - [pytest-bdd](https://github.com/pytest-dev/pytest-bdd)

### Jest

### PyTest

- Ref
  - [FastAPI - Testing](https://fastapi.tiangolo.com/tutorial/testing/)

```sh
pip install httpx
pytest
```

`test_example_helloworld.py`

```py
from fastapi import FastAPI
from fastapi.testclient import TestClient

app = FastAPI()


@app.get("/")
async def read_main():
    return {"msg": "Hello World"}


client = TestClient(app)


def test_read_main():
    response = client.get("/")
    assert response.status_code == 200
    assert response.json() == {"msg": "Hello World"}
```

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