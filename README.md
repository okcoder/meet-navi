# Meet Navi (Electron + TypeScript)

Electron + TypeScript でデスクトップアプリを開発するプロジェクトです。
開発・実行環境は以下を想定しています。

## Development / Runtime Matrix

- WSL Development -> Windows Runtime
- macOS Development -> macOS Runtime

## Tech Stack

- Electron
- TypeScript
- Electron Forge
- Volta（Node.js バージョン管理）

## Version Policy

- 開発時の Node.js は **22.9.0** を使用します。
- バージョン固定は `package.json` の Volta 設定で管理します。
- 通常の開発者セットアップでは `volta pin` は不要です（プロジェクト設定更新時のみ実施）。

## Prerequisites

- Git
- Volta
- 開発環境:
  - WSL2 (Ubuntu など) または macOS
- 実行環境:
  - WSL 開発時は Windows 10/11
  - macOS 開発時は macOS

## Install Volta (if needed)

### Check

```bash
volta --version
```

### WSL / Linux

```bash
curl https://get.volta.sh | bash
```

### macOS

```bash
brew install volta
```

インストール後、シェルを再起動して `volta --version` を再確認してください。

## Setup

```bash
npm install
```

## Development

```bash
npm start
```

## Build / Package

```bash
npm run make
```

## Verify Runtime Versions (optional)

アプリ実行時の Electron / Node.js バージョンは次で確認できます。

```ts
console.log(process.versions.electron, process.versions.node);
```

## Operational Notes

### WSL で開発する場合

- コード編集・依存管理は WSL で行います。
- Electron アプリの起動・動作確認は Windows 側で行います。

### macOS で開発する場合

- コード編集・依存管理・起動確認をすべて macOS 上で行います。

## Notes

- Electron 実行時の Node.js は Electron 同梱版です。
- 開発環境の Node.js（Volta 管理）とは役割が異なります。
