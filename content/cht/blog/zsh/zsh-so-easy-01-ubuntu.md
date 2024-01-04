---
author: Meimei
title: Zsh So Easy - Ubuntu
date: 2023-12-29
description: Install Zsh on Ubuntu
tags:
  - zsh
  - oh-my-zsh
  - Powerlevel10k
keywords:
  - zsh
  - oh-my-zsh
  - Powerlevel10k
thumbnail: /images/zsh/zsh.png
---

是不是一直覺得為什麼別人的 `終端機 Terminal` 都比較漂亮好看，有各種圖案，還可以顯示各種資訊，例如 `Git`、`Conda` 等。  
不用再羨慕別人啦！這就教大家如何讓自己電腦的 `終端機 Terminal` 弄的很專業的樣子，即使是電腦白痴，也可以讓別看到你電腦時歎為觀止喔！


</br>

## 安裝 Zsh

首先先更新 `apt`
```bash
sudo apt-get update && sudo apt-get upgrade
```
<center><img src="/images/zsh/01-ubuntu/ubuntu-01-update-apt.png" width="100%"/></center>


利用 `apt` 安裝 `Zsh`
```bash
sudo apt-get install zsh -y
```
<center><img src="/images/zsh/01-ubuntu/ubuntu-02-install-zsh.png" width="100%"/></center>


確認 Zsh 版本來確定 Zsh 是否有成功安裝
```bash
zsh --version
```
<center><img src="/images/zsh/01-ubuntu/ubuntu-03-zsh-version.png" width="100%"/></center>


</br>

## 安裝 Oh My Zsh

利用一行指令安裝

```bash
sh -c "$(curl -fsSL <https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh>)"
```

安裝過程中會詢問是否將 zsh 設定為預設的 shell，依照自己的習慣即可，我習慣使用 zsh 所以輸入 `y` 來幫我設定  
不過這邊要注意，需要重新開機才可以套用此設定
<center><img src="/images/zsh/01-ubuntu/ubuntu-04-install-oh-my-zsh.png" width="100%"/></center>


看到漂亮的 `oh my zsh` 字眼代表安裝成功嚕
<center><img src="/images/zsh/01-ubuntu/ubuntu-05-oh-my-zsh.png" width="100%"/></center>


</br>

## 套用 Powerlevel10k 主題

### 下載 Powerlevel10k

`Oh My Zsh` 有很多漂亮的主題可以使用，這邊我利用我最喜歡的 `Powerlevel10k` 這個主題來做教學  
利用 `git clone` 來將 `Powerlevel10k` 克隆到本地端 `oh my zsh` 存放 theme 的資料夾

```bash
git clone --depth=1 <https://github.com/romkatv/powerlevel10k.git> ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
<center><img src="/images/zsh/01-ubuntu/ubuntu-06-install-powerlevel10k.png" width="100%"/></center>


將 `oh my zsh` 的 `theme` 設定為 `Powerlevel10k`
```bash
vim ~/.zshrc
```
<center><img src="/images/zsh/01-ubuntu/ubuntu-07-set-powerlevel10k.png" width="100%"/></center>


將 `ZSH_THEME="robbyrussell”` 改成 `ZSH_THEME="powerlevel10k/powerlevel10k”`
<center><img src="/images/zsh/01-ubuntu/ubuntu-08-set-powerlevel10k.png" width="100%"/></center>

</br>

### 安裝字體

將下面 4 個字體都下載並安裝
- [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
- [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
- [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
- [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

將 `Terminal 終端機` 字體改成 `MesloLGS NF`
<center><img src="/images/zsh/01-ubuntu/ubuntu-09-terminal-setting.png" width="40%"/></center>


選擇設定檔下方的 `未命名`，然後把 `自訂字形` 打勾
<center><img src="/images/zsh/01-ubuntu/ubuntu-10-terminal-set-font.png" width="100%"/></center>


點擊自訂字形右邊的 `Monospace Regular`，選擇 `MesloLGS NF Regular` 最後點選 `選取`
<center><img src="/images/zsh/01-ubuntu/ubuntu-11-terminal-set-font.png" width="50%"/></center>

</br>

### 設定 Powerlevel10k 參數

重新套用 `zsh` 設定
```bash
source ~/.zshrc
```

過程中一開始會顯示一些特定圖示來讓你確定是否可以正常顯示，如果顯示正常，就輸入 `y`
<center><img src="/images/zsh/01-ubuntu/ubuntu-12-set-powerlevel10k-config.png" width="100%"/></center>


接著會設定一些顯示風格，這邊就自己設定喜歡的風格就好
<center><img src="/images/zsh/01-ubuntu/ubuntu-13-set-powerlevel10k-config.png" width="100%"/></center>


都設定完之後就可以看到漂亮的界面啦
<center><img src="/images/zsh/01-ubuntu/ubuntu-14-set-powerlevel10k-config.png" width="100%"/></center>

</br>

### 顯示 conda 訊息

開啟 `Powerlevel10k` 的 `參數檔`
```bash
vim ~/.p10k.zsh
```

找到 `[ Line #1 ]` 設定的地方，然後加入 `anaconda`
<center><img src="/images/zsh/01-ubuntu/ubuntu-15-show-conda.png" width="100%"/></center>


存檔後，重新開啟 `Terminal 終端機` 就可以看到 `conda` 環境訊息嚕
<center><img src="/images/zsh/01-ubuntu/ubuntu-16-show-conda.png" width="100%"/></center>