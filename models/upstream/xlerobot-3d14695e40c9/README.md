# XLeRobot 官方 URDF 參考模型

此目錄保存可直接取得的官方模型與全部配套網格，供 Anvil 後續外觀修改與模擬探索。這是上游參考版本，尚未改成 Roy 的實物版本。

## 檔案位置與取得方式

在本 repo 根目錄，主要模型為 `models/upstream/xlerobot-3d14695e40c9/xlerobot.urdf`。

- [主要 URDF](./xlerobot.urdf)
- [front 版本 URDF](./xlerobot_front.urdf)
- [SRDF](./xlerobot.srdf)
- [完整 meshes](./meshes/)
- [來源與雜湊清單](./source-manifest.json)

Clone 本 repo 或在 GitHub 選 Code → Download ZIP，即可取得這個資料夾。URDF 必須和 `meshes/` 一起保存，不能只下載 XML 檔後刪掉網格。若使用既有 checkout，取得包含本目錄的 commit 後即可使用。

## 來源與授權

- 原始專案：[Vector-Wangel/XLeRobot](https://github.com/Vector-Wangel/XLeRobot)。
- 固定 commit：`3d14695e40c9c68229c0aacffca6053c75cd3eb6`。
- 原始路徑：`simulation/Maniskill/assets/xlerobot/`。
- 取得日期：2026-09-07。
- 51 份上游原檔完整保留、未修改：兩份 URDF、一份 SRDF、47 個 mesh，以及上游根目錄的 [Apache-2.0 LICENSE](./LICENSE)。此子目錄的上游模型不套用 repo 根目錄 MakerMods 的 MIT 授權。
- `source-manifest.json` 是本次加入的來源／驗證紀錄，包含每份原檔的 Git blob SHA、SHA-256 與下載網址。

## Tnkr 預覽的關係

[MakerMods Tnkr 頁面](https://tnkr.ai/ryans-workspace/xlerobot#overview) 的預覽 URDF 與本目錄 `xlerobot.urdf` 逐位元一致，SHA-256 為 `73e947aa4f3636819bd039c3fcd03c625760e9ad32ccadfea05710afa6bf5578`。取回的 24 個 STL 也與官方一致；另五個夾爪 collision PLY 在 Tnkr 回傳 HTTP 403，官方包則完整包含。

這能確認預覽模型的來源，不能證明它已包含 MakerMods 每一項改件或符合 Anvil 的實物尺寸。

## 已驗證與尚未驗證

已檢查兩份 URDF 的 XML、32 links／31 joints、17 個非固定關節（包括虛擬底座關節）。各自引用的 29 個 mesh 全部存在，joint 的 parent／child link 有效。51 份上游原檔的 Git blob SHA 與固定 commit 一致。

尚未做 viewer、物理引擎載入、動力學校準或真機測試；沒有因此取得新的 Anvil motion 或 simulation PASS。

## 建議後續使用

保留此目錄不變，另外建立 Anvil 修改版。以 URDF 作骨架，搭配 repo 的 MakerMods `3mf/` 核對支架、頸部、電池與電子外殼。先做可查看的目標外觀；需要描述當前實物時，另外標出未安裝的部件。進入物理模擬前，再核對尺度、座標、關節限位、碰撞與慣性。
