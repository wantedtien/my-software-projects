# my-software-projects
AM I DOIONG THIS RIGHT
.github/
  └── workflows/
        └── ci.yml


name: CI Pipeline
on:
  push:
    branches:
      - develop
      - feature/*
      - release/*
  pull_request:
    branches:
      - develop
      - master
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3
      - name: Set up Python
        uses: actions/setup-python@v3
        with:
          python-version: 3.x
      - name: Install dependencies
        run: |
          pip install -r requirements.txt
      - name: Run tests
        run: |
          pytest

git add .github/workflows/ci.yml
git commit -m "Add GitHub Actions CI pipeline"
git push origin develop

