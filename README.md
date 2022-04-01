<div align="center">
  <p>
    <h3>PostgreSQL in GitHub Actions</h3>
  </p>
  <p>启动一个 PostgreSQL ，用于单元测试</p>
</div>

---

## 简介

使用docker容器启动一个 PostgreSQL 实例，用于自动化单元测试。  
默认账号 postgres / postgres  

## 用法

```yaml
name: test

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Git checkout
        uses: actions/checkout@v2
  
      - name: Setup PostgreSQL
        uses: nnhy/postgresql-action@v1.0
  
      - name: Test
        run: dotnet test -c Release XUnitTestClient/XUnitTestClient.csproj
```
