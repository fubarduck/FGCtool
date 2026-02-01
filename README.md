# FGC Tool

**[English](#english) | [日本語](#japanese)**

---

<a id="english"></a>
## English

A Windows utility for the fighting game community that ensures your PC is running under optimal display and audio conditions.

### Features

#### Display Optimization
- Automatically detects when fighting games launch
- Verifies your monitor is running at 120Hz or higher
- Checks that your display is at its maximum available refresh rate
- One-click "Fix Now" to optimize settings instantly
- Supports single, extended, and clone/mirror display configurations
- Status overlay shows current display status when games launch

#### Audio Management
- Prevents audio from switching when controllers with headphone jacks are connected
- Automatically restores your preferred audio device
- Quick access to change audio output

#### Controller Hotkey
- Do a long press on the Select/Back/Share/Minus button to show the status overlay
- Supported controllers:
  - Xbox controllers (Back button)
  - DualShock 4 (Share button)
  - PS5 DualSense (Share button, USB only)
  - Nintendo Switch Pro Controller (Minus button, USB only)
  - Nintendo Switch 2 Pro Controller (Minus button, USB only)
  - Most fighting game controllers (Back/Share must use default button mapping)

#### System Tray
- Runs quietly in the background
- Double-click tray icon to open settings
- Right-click for quick menu / fully exit app

#### Automatic Updates
- Checks for new versions on startup
- Notifies you when updates are available

### Minimum Requirements
OS: Windows 10 or Windows 11 (64-bit)
All dependencies are included in the .exe file.

### Installation

1. Download the latest release
2. Extract to any folder
3. Run `FGCtool.exe`

### Usage

#### On Game Launch
When a fighting game is detected, a status overlay appears in the top-right corner showing your display status:
- **Green checkmark**: Your settings are optimal for competitive play
- **Orange warning**: Click the main window to fix settings

If your configuration needs attention, the full alert popup provides a "Fix Now" button to automatically set your monitor to maximum refresh rate.

#### Main Window
- **Display Configuration**: Shows all connected monitors with current refresh rates
  - Yellow warning appears if a monitor isn't at its maximum rate
  - Use dropdown to manually change refresh rate
- **Audio Output**: Select and lock your preferred audio device
- **Language**: Switch between English and Japanese

#### Supported Games
By default, the tool monitors for the following titles:
- Street Fighter 6
- Tekken 8
- Guilty Gear Strive
- Fatal Fury: CotW
- 2XKO

### Configuration

Configuration files are stored in `%LocalAppData%\FGCtool\`.

#### Adding Games (games.txt)

Edit `games.txt` to add or remove monitored games. Each line is a process name without `.exe`:

```
# Lines starting with # are comments
StreetFighter6
GGST-Win64-Shipping
MyCustomGame
```

To find a game's process name, open Task Manager while the game is running and look under the "Details" tab.

**Hot-reload:** Changes to `games.txt` are applied automatically within 1 second. No need to restart the app.

##### Custom Display Names

You can specify a custom display name using the `|` delimiter. This name appears in alerts instead of the process name:

```
# Format: ProcessName|Display Name
SomeGame-Win64-Shipping|Some Game
AnotherTitle|My Favorite Fighter
```

The default games already have built-in friendly names, so you only need this for games you add yourself.

##### Startup Delay

Some games have exclusive loading screens that block overlays. You can configure how long to wait before showing the status overlay:

```
# Format: ProcessName||delay=N  (N = seconds, 5-30)
MySlowGame||delay=15
MyGame|Custom Name|delay=10
```

The default delay is 6 seconds. Built-in games like Guilty Gear Strive (12s) and Tekken 8 (9s) have appropriate defaults, but you can override them if needed.

#### Settings (settings.json)

Important settings are configured through the app. Advanced users can edit `settings.json` directly:

| Setting | Description |
|---------|-------------|
| `EnableControllerHotkey` | Enable/disable the Select button overlay |
| `OverlayDurationSeconds` | How long the status overlay displays (1-10 seconds) |
| `AutoRestoreAudio` | Automatically restore preferred audio device |
| `CheckForUpdatesOnStartup` | Check for updates when app starts |

### Why 120Hz+?

Fighting games run at 60 FPS, but a 120Hz (or higher) monitor provides reduced input lag expected by today's competitive players.

Running at your monitor's maximum refresh rate (144Hz, 165Hz, 240Hz, etc.) provides even better responsiveness.

### Clone Mode Warning

When using clone/mirror mode (for streaming or recording), be aware:
- Windows locks all displays to the lowest common refresh rate
- A 60Hz capture card will limit your gaming monitor to 60Hz
- FGC Tool will warn you if this situation is detected

### Troubleshooting

**"Fix Now" doesn't work**
- Try running as Administrator
- Some monitors require using their On-Screen Display to enable high refresh rates first

**Monitor shows lower than expected max rate**
- Check that your cable supports the resolution + refresh rate (DisplayPort 1.4 or HDMI 2.1 recommended)
- Verify high refresh rate is enabled in your GPU control panel

**Audio keeps switching (no sound)**
- Make sure your preferred device is selected in the Audio section

### Credits

Developed by [@fubarduck](https://twitter.com/fubarduck) for the FGC.

### License

Freeware. Free to use and distribute for personal and commercial purposes. No warranty provided.

---

<a id="japanese"></a>
## 日本語

格闘ゲームコミュニティ向けのWindowsユーティリティです。PCのディスプレイとオーディオ設定を最適な状態に保ちます。

### 機能

#### ディスプレイ最適化
- 格闘ゲームの起動を自動検出
- モニターが120Hz以上で動作しているか確認
- ディスプレイが最大リフレッシュレートで動作しているか確認
- ワンクリックで設定を最適化する「今すぐ修正」機能
- シングル、拡張、クローン/ミラーの各ディスプレイ構成に対応
- ゲーム起動時にステータスオーバーレイを表示

#### オーディオ管理
- ヘッドホン端子付きコントローラー接続時の音声切り替えを防止
- 優先オーディオデバイスを自動的に復元
- オーディオ出力の素早い変更

#### コントローラーホットキー
- Select/Back/Share/Minusボタンを長押しでステータスオーバーレイを表示
- 対応コントローラー:
  - Xboxコントローラー（Backボタン）
  - DualShock 4（Shareボタン）
  - PS5 DualSense（Shareボタン、USB接続のみ）
  - Nintendo Switch Proコントローラー（Minusボタン、USB接続のみ）
  - Nintendo Switch 2 Proコントローラー（Minusボタン、USB接続のみ）
  - ほとんどの格闘ゲームコントローラー（Back/Shareがデフォルトのボタン配置である必要あり）

#### システムトレイ
- バックグラウンドで静かに動作
- トレイアイコンをダブルクリックで設定を開く
- 右クリックでクイックメニュー/アプリ終了

#### 自動アップデート
- 起動時に新しいバージョンをチェック
- アップデートがある場合に通知

### 動作環境
OS: Windows 10またはWindows 11（64ビット）
すべての依存関係は.exeファイルに含まれています。

### インストール

1. 最新リリースをダウンロード
2. 任意のフォルダに解凍
3. `FGCtool.exe`を実行

### 使い方

#### ゲーム起動時
格闘ゲームが検出されると、画面右上にディスプレイ状態を示すステータスオーバーレイが表示されます：
- **緑のチェックマーク**: 設定は競技プレイに最適です
- **オレンジの警告**: メインウィンドウをクリックして設定を修正してください

設定に問題がある場合、完全なアラートポップアップに「今すぐ修正」ボタンが表示され、モニターを最大リフレッシュレートに自動設定できます。

#### メインウィンドウ
- **ディスプレイ構成**: 接続されているすべてのモニターと現在のリフレッシュレートを表示
  - モニターが最大レートでない場合、黄色い警告が表示されます
  - ドロップダウンでリフレッシュレートを手動変更可能
- **オーディオ出力**: 優先オーディオデバイスを選択してロック
- **言語**: 英語と日本語を切り替え

#### 対応ゲーム
デフォルトで以下のタイトルを監視します：
- Street Fighter 6
- 鉄拳8
- GUILTY GEAR -STRIVE-
- 餓狼伝説 City of the Wolves
- 2XKO

### 設定

設定ファイルは `%LocalAppData%\FGCtool\` に保存されます。

#### ゲームの追加 (games.txt)

`games.txt`を編集して監視するゲームを追加・削除できます。各行は`.exe`なしのプロセス名です：

```
# #で始まる行はコメントです
StreetFighter6
GGST-Win64-Shipping
MyCustomGame
```

ゲームのプロセス名を確認するには、ゲーム実行中にタスクマネージャーを開き、「詳細」タブを確認してください。

**ホットリロード:** `games.txt`への変更は1秒以内に自動的に適用されます。アプリの再起動は不要です。

##### カスタム表示名

`|`区切りでカスタム表示名を指定できます。この名前はプロセス名の代わりにアラートに表示されます：

```
# 形式: プロセス名|表示名
SomeGame-Win64-Shipping|Some Game
AnotherTitle|お気に入りの格ゲー
```

デフォルトのゲームにはすでにフレンドリーな名前が組み込まれているため、自分で追加したゲームにのみこの機能が必要です。

##### 起動遅延

一部のゲームはオーバーレイをブロックする専用のローディング画面があります。ステータスオーバーレイを表示するまでの待機時間を設定できます：

```
# 形式: プロセス名||delay=N  (N = 秒数、5-30)
MySlowGame||delay=15
MyGame|カスタム名|delay=10
```

デフォルトの遅延は6秒です。GUILTY GEAR -STRIVE-（12秒）や鉄拳8（9秒）などの組み込みゲームには適切なデフォルトがありますが、必要に応じて上書きできます。

#### 設定 (settings.json)

重要な設定はアプリから変更できます。上級者は`settings.json`を直接編集できます：

| 設定 | 説明 |
|------|------|
| `EnableControllerHotkey` | Selectボタンオーバーレイの有効/無効 |
| `OverlayDurationSeconds` | ステータスオーバーレイの表示時間（1〜10秒） |
| `AutoRestoreAudio` | 優先オーディオデバイスを自動復元 |
| `CheckForUpdatesOnStartup` | 起動時にアップデートを確認 |

### なぜ120Hz以上が必要？

格闘ゲームは60FPSで動作しますが、120Hz以上のモニターは現在の競技プレイヤーが求める低入力遅延を実現します。

モニターの最大リフレッシュレート（144Hz、165Hz、240Hzなど）で動作させると、さらに優れた応答性が得られます。

### クローンモードの警告

クローン/ミラーモード（配信や録画用）を使用する場合の注意：
- Windowsはすべてのディスプレイを最も低い共通リフレッシュレートにロックします
- 60Hzのキャプチャカードはゲーミングモニターを60Hzに制限します
- FGC Toolはこの状況が検出された場合に警告を表示します

### トラブルシューティング

**「今すぐ修正」が機能しない**
- 管理者として実行してみてください
- 一部のモニターは、まずOSD（オンスクリーンディスプレイ）で高リフレッシュレートを有効にする必要があります

**モニターの最大レートが予想より低い**
- ケーブルが解像度+リフレッシュレートに対応しているか確認（DisplayPort 1.4またはHDMI 2.1推奨）
- GPUコントロールパネルで高リフレッシュレートが有効になっているか確認

**オーディオが切り替わり続ける（音が出ない）**
- オーディオセクションで優先デバイスが選択されているか確認

### クレジット

[@fubarduck](https://twitter.com/fubarduck)が格闘ゲームコミュニティのために開発しました。

### ライセンス

フリーウェア。個人および商用目的で自由に使用・配布できます。保証はありません。
