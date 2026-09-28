# v1.0.1

## 简体中文

修复启用触摸保护时，控制器的实体推子可能在用户没有操作、Windows 音量仍然正确的情况下停在错误位置的问题。当未触摸的推子回报位置与 Windows 当前音量不一致时，桥接器会短暂等待可能稍晚到达的触摸消息；确认没有触摸后，仅重新发送正确的电机位置，不会改动 Windows 音量。正常电机回声不会触发重复发送，也没有加入周期性刷新。

## English

Fixes a physical fader that could remain at an incorrect position while touch protection was enabled, even though the user had not touched it and the Windows volume was still correct. If an untouched fader reports a position that disagrees with Windows, the bridge briefly waits for a possibly delayed touch message, then resends only the authoritative motor position. Windows volume is not changed, matching motor echoes stay silent, and no periodic refresh is added.

## 日本語

タッチ保護が有効な状態で、ユーザーが操作しておらず Windows の音量も正しいのに、実機フェーダーだけが誤った位置に残ることがある問題を修正しました。未タッチのフェーダーが Windows と異なる位置を通知した場合、遅れて届く可能性のあるタッチ信号を短時間待ち、タッチがなければ正しいモーター位置だけを再送します。Windows の音量は変更せず、正常なモーターエコーによる再送ループや周期的な更新も追加しません。

The installer and application are currently unsigned. Verify the SHA-256 value shown below after downloading.

`Windows-Fader-Bridge-for-Mackie-Control-v1.0.1-Setup-x64.exe`
SHA-256: `32A309200423CC7805736ABE6D9659F38CFFD3405D6408FEFA45348E6165950A`

---

# v1.0.0

## 简体中文

首个面向用户的正式版本。提供 Windows 11 x64 安装程序、中英双语应用界面、中英日三语使用手册、实时 Windows 音频控制、峰值表、播放信息，以及按键、旋钮和 Jog/Move/Zoom 自定义。已用 iCON P1-Nano 实机验证；同时支持通用 MCU 配置。

## English

First public user release. Includes a Windows 11 x64 installer, English/Chinese app UI, English/Chinese/Japanese guides, real-time Windows audio control, meters, playback information, and configurable buttons, encoders, and Jog/Move/Zoom. Physically verified with iCON P1-Nano and also provides a generic MCU profile.

## 日本語

一般ユーザー向け初回正式リリースです。Windows 11 x64 インストーラー、中英対応アプリ画面、中英日ユーザーガイド、Windows オーディオのリアルタイム操作、メーター、再生情報、ボタン／エンコーダー／Jog・Move・Zoom の割り当てを収録しています。iCON P1-Nano で実機確認済みで、汎用 MCU プロファイルにも対応します。

The installer and application are currently unsigned. Verify the SHA-256 value shown below after downloading.

`Windows-Fader-Bridge-for-Mackie-Control-v1.0.0-Setup-x64.exe`  
SHA-256: `2001C1E94E5064AF5D6765A1EC148CFF29DF61721893C12816A02E2B763D495B`
