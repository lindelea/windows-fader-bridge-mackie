# v1.0.2

## 简体中文

改善应用音频通道新增或移除时 Master 推子跳动的问题。通道列表与选择变化不再强制重发所有电机位置，未改变的 Master 保持不动；通道实际换位时仍会同步对应推子，并保留触摸保护。Windows 暂时读不到音量时，不会将其误当成 0，也不会用旧值打断正在进行的操作。补充电机与触摸诊断记录，不增加周期性电机重发或人为操作延迟。

下载下方安装包，退出桥接器后覆盖安装即可，原有设备与命令设置保留。长时间运行中的偶发情况仍会持续跟踪；若再次出现，请记录时间并保留日志。

## English

Improves Master-fader jumps when application audio channels appear or disappear. Channel-list and selection changes no longer force every motor position to be resent; an unchanged Master stays still. Actual channel reassignment still updates the affected fader with touch protection preserved. A temporary Windows volume-read failure is not treated as zero, and stale values cannot interrupt an ongoing gesture. Adds motor and touch diagnostics without periodic motor resends or deliberate control latency.

Close the bridge and install over the existing version; your device and command settings are preserved. Intermittent behavior during long sessions remains under observation. If it recurs, note the time and retain the logs.

## 日本語

アプリのオーディオチャンネル追加・削除時に Master フェーダーが跳ねる問題を改善しました。チャンネル一覧や選択の変更で全モーターの位置を強制再送せず、音量が変わっていない Master は動かしません。実際にチャンネルの割り当てが変わった場合は、タッチ保護を維持しながら対象のフェーダーを同期します。Windows から音量を一時的に取得できない場合も 0 と誤認せず、古い値で操作中のフェーダーを戻さないようにしました。周期的なモーター再送や意図的な操作遅延を追加せず、モーターとタッチの診断記録を強化しています。

ブリッジを終了してから上書きインストールしてください。デバイスとコマンドの設定は引き継がれます。長時間使用時の偶発的な挙動は引き続き確認します。再発した場合は時刻を記録し、ログを保存してください。

The installer and application are currently unsigned. Verify the SHA-256 value shown below after downloading.

`Windows-Fader-Bridge-for-Mackie-Control-v1.0.2-Setup-x64.exe`
SHA-256: `D4CB005DEBF37724EF0D8D2FDBC462DEC571C3D2986BB02EE46F2E29DE6E3E38`

- [User guides / 使用手册 / ユーザーガイド](https://github.com/lindelea/windows-fader-bridge-mackie)
- [Exact source for v1.0.2](https://github.com/lindelea/windows-fader-bridge/tree/windows-mackie-v1.0.2)

---

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
