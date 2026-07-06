# LeaguePost

LeaguePost は中国地区大学準硬式野球連盟向けの運用支援GUIです。
このフォルダは GitHub にそのままアップロードし、GitHub Actions で Windows x64 版の EXE を作成できるように整理したものです。

## GitHubでEXEを作る手順

1. GitHubで新しいリポジトリを作成します。最初は Private で大丈夫です。
2. このフォルダの中身をリポジトリへアップロードします。
3. GitHubの `Actions` タブを開きます。
4. `Build Windows x64 EXE` を選び、`Run workflow` を押します。
5. 完了後、実行結果の `Artifacts` から `LeaguePost-windows-x64` をダウンロードします。
6. ZIPを展開し、`LeaguePost.exe` を起動します。

## 配布時に含めるもの

GitHub Actionsの成果物には以下が入ります。

- `LeaguePost.exe`
- `UniversityRoster/`
- `Neo_Phoenix/`

`LeaguePost.exe` と2つのフォルダは同じ場所に置いたまま配布してください。

## ローカルで起動する場合

```powershell
python -m pip install -r requirements.txt
python LeaguePost.py
```

## ローカルでEXEを作る場合

```powershell
python -m pip install -r requirements.txt
pyinstaller --noconfirm LeaguePost.spec
```

完成したEXEは `dist/LeaguePost.exe` に作成されます。
