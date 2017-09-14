# ansible-mac-provisioning

Macの開発環境をAnsibleで構築していきます。まだまだ完成とは言えないので、Pull Requestもらえると助かります。

## 注意事項

現時点ではフル自動ではないので、XCodeのcommand line toolとHomebrewとansibleとpythonは自力でいれてください。

## 事前準備

### XCodeのインストール

```bash
sudo xcodebuild -license # パスワードを入力
```

### Homebrewのインストール

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Ansibleのインストール

```bash
brew install python
brew install ansible
```

## 使い方

### git clone

```bash
git clone https://github.com/patorash/ansible-mac-provisioning.git ~/ansible-mac-provisioning
```

### playbookを実行

```bash
cd ~/ansible-mac-provisioning
ansible-playbook -i hosts localhost.yml
```

## 設定される内容

- homebrewで色々入る
- homebrew-caskで色々入る
- anyenvでrbenvとndenvのインストール
  - Ruby
    - 2.3.4
    - 2.4.1
  - Node
    - v8.5.0
- Macの設定
  - finderの設定
    - 拡張子を表示
    - 隠しファイルを表示
  - Dock
    - 自動的に隠す
  - Safari
    - デバッグメニューを表示