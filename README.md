# pythondev
pythonの開発環境の勉強

## コンテナ起動・接続
- コンテナ起動
```cmd
$ docker build -t python39docker .
$ docker run -itd -v $(pwd):/opt/mnt -p 18888:8888 python39docker
```
- コンテナ起動(Windows)
```cmd
$ docker build -t python39docker .
$ docker run -itd -v "%CD%":/opt/mnt -p 18888:8888 python39docker
```
- コンテナにVSCodeからの接続
  - VSCode左下のリモートウィンドウ
  -  → Attach to Running Container
  -  → コンテナ側のVSCodeが起動するので、開発する

## その他
- linter, formatter実行
  ```cmd
  $ poetry run isort src tests
  $ poetry run black src tests
  $ poetry run flake8 src tests
  ```

- テスト実行
  ```cmd
  # packageを読み込んでパス設定
  $ poetry install
  # テスト実行
  $ poetry run pytest src tests
  ```

- Jupyter Notebook起動
  ```cmd
  $ jupyter notebook --allow-root --port=8888 --ip=0.0.0.0 &
  ```
## 参考文献
- Python開発環境構築手順（VSCode, Docker, Poetry, isort, black, flake8, pytest）  https://qiita.com/nokoxxx1212/items/da1832468cbd9a762a46
