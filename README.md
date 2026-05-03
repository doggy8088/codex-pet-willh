# Codex Pets：Will 保哥

這裡提供一款以 Will 保哥為主題的 Codex 寵物：[Codex Pets](https://developers.openai.com/codex/app/settings#codex-pets)。

安裝之後，你寫 Code 時就不再是孤軍奮戰。

每當你準備硬幹、亂猜、跳過測試、直接上 Production 的時候，牠就會在旁邊用保哥的眼神看著你，彷彿在說：

「你確定這樣寫，三個月後的你不會回來罵今天的你嗎？」

副作用是：
你可能會開始補文件、補測試、重構命名，甚至突然想吃雞排。

![image](spritesheet.webp)

## 內容

* `pet.json` / `avatar.json`
* `spritesheet.webp`

## 安裝

最簡單的安裝方式是在 Codex app 直接輸入以下提示詞：

```text
安裝 doggy8088/codex-pet-willh repo 的 Codex Pet 給我的 Codex app 使用
```

請在終端機執行：

```sh
curl -sL "https://doggy8088.github.io/codex-pet-willh/willh.codex-pet.zip" -o "/tmp/willh.codex-pet.zip" && mkdir -p "$HOME/.codex/pets/willh" && unzip -o "/tmp/willh.codex-pet.zip" -d "$HOME/.codex/pets/willh"
```

執行後，Codex 會在 `$HOME/.codex/pets/willh` 讀取這個寵物。

> **ℹ️ macOS / Linux 使用者：** Codex 讀取的是 `$HOME/.codex/pets/willh/pet.json`。

### Windows 安裝

在 **PowerShell** 執行以下指令：

```powershell
# 下載寵物壓縮檔
Invoke-WebRequest -Uri "https://doggy8088.github.io/codex-pet-willh/willh.codex-pet.zip" -OutFile "$env:TEMP\willh.codex-pet.zip"

# 解壓縮到正確位置
Expand-Archive -Path "$env:TEMP\willh.codex-pet.zip" -DestinationPath "$env:USERPROFILE\.codex\avatars\willh" -Force

# 清理暫存檔
Remove-Item -Path "$env:TEMP\willh.codex-pet.zip"
```

> **⚠️ Windows 注意事項：**
> - Codex Desktop 是從 `%USERPROFILE%\.codex\avatars\<id>\avatar.json` 讀取自訂寵物，**不是** `.codex\pets\`。
> - 如果你在設定中找不到寵物，請檢查路徑是否為 `%USERPROFILE%\.codex\avatars\willh\`，且裡面有 `avatar.json` 和 `spritesheet.webp` 兩個檔案。
> - 你也可以使用 Git Bash 或 WSL 執行 macOS / Linux 的安裝指令。

## 使用

1. 下載並解壓縮寵物檔案。
2. 確認路徑正確：
   - **macOS / Linux：** `$HOME/.codex/pets/willh` 內有 `pet.json` 與 `spritesheet.webp`
   - **Windows：** `%USERPROFILE%\.codex\avatars\willh` 內有 `avatar.json` 與 `spritesheet.webp`
3. 重新啟動 Codex 並到 **設定** > **外觀** > **寵物**（或 **Avatar**）選取 **Will 保哥**。
4. 到聊天視窗輸入 `/pet` 或輸入 `/` 選取「寵物」即可啟用。
5. 然後在聊天視窗輸入任何指令，這個 Codex Pet 就會動起來了！

## 檔案說明

* `pet.json`：寵物的中繼資料（macOS / Linux 使用）。
* `avatar.json`：寵物的中繼資料備份（Windows Codex Desktop 使用，內容與 `pet.json` 相同）。
* `spritesheet.webp`：寵物的圖像素材。

## Spritesheet 規格（供自訂寵物創作者參考）

如果你想要自己製作寵物，spritesheet 需符合以下規格：

| 項目 | 數值 |
|------|------|
| 總尺寸 | 1536 × 1872 px |
| 欄 × 列 | 8 欄 × 9 列 |
| 每格大小 | 192 × 208 px |
| 格式 | WebP |

**動作列對應：**

| 列 (從 0 開始) | 動作 |
|----|------|
| 0 | idle |
| 1 | running-right |
| 2 | running-left |
| 3 | waving |
| 4 | jumping |
| 5 | failed |
| 6 | waiting |
| 7 | running |
| 8 | review |
