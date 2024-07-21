# app

## macOS

```shell
# git config
echo -e "[user]\n        name = Deolin\n        email = splendid.deolin@gmail.com\n[pull]\n        ff = only" > ~/.gitconfig

# 安装oh my zsh（清华Tuna源）
git clone https://mirrors.tuna.tsinghua.edu.cn/git/ohmyzsh.git
cd ohmyzsh/tools
REMOTE=https://mirrors.tuna.tsinghua.edu.cn/git/ohmyzsh.git sh install.sh
omz update
echo 'export ZSH_THEME="cloud"' >> ~/.zshrc && source ~/.zshrc

# 安装Homebrew（清华Tuna源）
export HOMEBREW_INSTALL_FROM_API=1
export HOMEBREW_API_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles/api"
export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles"
export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"
export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"
git clone --depth=1 https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/install.git brew-install
./brew-install/install.sh
rm -rf brew-install

# 为Homebrew设置环境变量
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zshrc
echo 'export HOMEBREW_API_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles/api"' >> ~/.zshrc 
echo 'export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"' >> ~/.zshrc 
source ~/.zshrc

# 除 homebrew/core 和 homebrew/cask 仓库外的 tap 仓库仍然需要设置镜像
brew tap --custom-remote --force-auto-update homebrew/cask-fonts https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask-fonts.git
brew tap --custom-remote --force-auto-update homebrew/cask-versions https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask-versions.git
brew tap --custom-remote --force-auto-update homebrew/command-not-found https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-command-not-found.git
brew tap --custom-remote --force-auto-update homebrew/services https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-services.git

# 安装软件
brew update
brew install --cask 1password
brew install --cask alfred
brew install --cask another-redis-desktop-manager
brew install --cask podman-desktop
brew install --cask easyfind
brew install --cask eudic
brew install --cask google-chrome
brew install --cask iina
brew install --cask iterm2
brew install --cask itsycal
brew install --cask mos
brew install --cask obsidian
brew install --cask corretto@8
echo 'export JAVA_HOME=`/usr/libexec/java_home`' >> ~/.zshrc && source ~/.zshrc
brew install --cask reqable
brew install --cask squirrel
brew install --cask snipaste
brew install --cask sublime-text
brew install --cask tencent-lemon
brew install --cask wpsoffice
brew install --cask mailmaster
brew install --cask neteasemusic
brew install --cask wechat
brew install --cask thunder
brew install --cask font-jetbrains-mono
brew install --cask font-lxgw-wenkai
brew install --ignore-dependencies maven
brew install node@20
echo 'export PATH="/opt/homebrew/opt/node@20/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc
brew install --ignore-dependencies gradle@7
echo 'export PATH="/opt/homebrew/opt/gradle@7/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc

brew install mas
mas install 1565629813 # FastZip
mas install 6443843900 # iBar
mas install 1039633667 # Irvue

# alias
alias mvni="mvn clean source:jar install -Dmaven.test.skip=true" # source:jar install的作用是即使pom没有指定maven-source-plugin，也能生成-sources.jar文件
alias clnproj='find . \( -type d -name ".idea" -o \( -type d -name "target" -a -exec test -e '{}/../pom.xml' \; \) \) -print -exec rm -rf {} +' # 递归地删除当前目录下的.idea目录和与pom.xml同层的target目录
alias gitapl='find . -type d -name .git -exec sh -c "cd \"{}\"/../; echo \"\n`pwd` \"; git rev-parse --abbrev-ref HEAD; git pull" \; 2>&1 | tee log-git-pull-`date +%Y%m%d-%H%m%S`.log' # 递归地在本地仓库执行git pull，打印结果
```

- [Cisco AnyConnect Secure Mobility Client](https://download.syxrzs.cn/anyconnect-4.8.00175.dmg)
- [DataGrip](https://www.jetbrains.com/datagrip/download/#section=mac)
- [IntelliJ IDEA Community](https://www.jetbrains.com/idea/download/?section=mac)
- [Typora](https://github.com/iuxt/src/releases/download/2.0/typora-0-11-18.dmg)

## Windows

- [1password](https://1password.com/zh-cn/downloads/windows/)
- [AnotherRedisDesktopManager](https://github.com/qishibo/AnotherRedisDesktopManager/releases)
- [Everything](https://www.voidtools.com/zh-cn/downloads/)
- [Eudic](https://www.eudic.net/v4/en/app/download)
- [Google Chrome](https://www.google.com/intl/zh-CN/chrome/)
- [Potplayer](https://potplayer.daum.net/?lang=en)
- [Tabby](https://github.com/Eugeny/tabby/releases/tag/v1.0.208)
- [Obsidian](https://obsidian.md/download)
- [Corretto 8](https://docs.aws.amazon.com/corretto/latest/corretto-8-ug/downloads-list.html)
- [Reqable](https://reqable.com/)
- [Rime](https://rime.im/download/)
- [Snipaste](https://www.snipaste.com/download.html)
- [Sublime Text](https://www.sublimetext.com/download)
- [Geek Uninstaller](https://geekuninstaller.com/download)
- [WPS Office](https://www.wps.cn/)
- [网易邮箱大师](https://dashi.163.com/)
- [网易云音乐](https://music.163.com/#/download)
- [微信](https://windows.weixin.qq.com/?lang=zh_CN)
- [迅雷](https://pc.xunlei.com/)
- [Jetbrains Mono](https://www.jetbrains.com/lp/mono/)
- [落霞孤鹜文楷](https://github.com/lxgw/LxgwWenKai/releases)
- [Maven](https://maven.apache.org/download.cgi)
- [Nodejs](https://nodejs.org/dist/v20.15.0/node-v20.15.0-x64.msi)
- [Gradle](https://gradle.org/releases/)
- [7-Zip](https://www.7-zip.org/download.html)
- [Typora](https://github.com/iuxt/src/releases/download/2.0/typora-setup-x64_0.9.96.exe)

## Jetbrains

- [GenerateAllSetter](https://plugins.jetbrains.com/plugin/9360-generateallsetter)
- [Grep Console](https://plugins.jetbrains.com/plugin/7125-grep-console)
- [Lombok](https://plugins.jetbrains.com/plugin/6317-lombok)
- [Maven Helper](https://plugins.jetbrains.com/plugin/7179-maven-helper)
- [MyBatisCodeHelperPro](https://plugins.jetbrains.com/plugin/9837-mybatiscodehelperpro)
- [Nyan Progress Bar](https://plugins.jetbrains.com/plugin/8575-nyan-progress-bar)
- [One Dark theme](https://plugins.jetbrains.com/plugin/11938-one-dark-theme)
- [RestfulTool](https://plugins.jetbrains.com/plugin/14280-restfultool)
- [String Manipulation](https://plugins.jetbrains.com/plugin/2162-string-manipulation)

```vm
# custom DataGrip VM options (expand/override 'bin/datagrip.vmoptions')

-Dsplash=true

-XX:+UnlockExperimentalVMOptions

# 开启ZGC
-XX:+UseZGC

# 堆内存指定为1G
-Xmx1g

# macOS启用Metal渲染加速
--illegal-access=warn
-Dsun.java2d.metal=true
--add-opens=java.desktop/java.awt.event=ALL-UNNAMED
--add-opens=java.desktop/sun.font=ALL-UNNAMED
--add-opens=java.desktop/java.awt=ALL-UNNAMED
--add-opens=java.desktop/sun.awt=ALL-UNNAMED
--add-opens=java.base/java.lang=ALL-UNNAMED
--add-opens=java.base/java.util=ALL-UNNAMED
--add-opens=java.desktop/javax.swing=ALL-UNNAMED
--add-opens=java.desktop/sun.swing=ALL-UNNAMED
--add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED
--add-opens=java.desktop/java.awt.peer=ALL-UNNAMED
--add-opens=java.desktop/javax.swing.text.html=ALL-UNNAMED
--add-exports=java.desktop/sun.font=ALL-UNNAMED
--add-exports=java.desktop/com.apple.eawt=ALL-UNNAMED
--add-exports=java.desktop/com.apple.laf=ALL-UNNAMED
--add-exports=java.desktop/com.apple.eawt.event=ALL-UNNAMED
```

```
# custom IntelliJ IDEA VM options (expand/override 'bin/idea.vmoptions')

-Dsplash=true

-XX:+UnlockExperimentalVMOptions

# 开启ZGC
-XX:+UseZGC

# 堆内存指定为3G
-Xmx3072M

# macOS启用Metal渲染加速
--illegal-access=warn
-Dsun.java2d.metal=true
--add-opens=java.desktop/java.awt.event=ALL-UNNAMED
--add-opens=java.desktop/sun.font=ALL-UNNAMED
--add-opens=java.desktop/java.awt=ALL-UNNAMED
--add-opens=java.desktop/sun.awt=ALL-UNNAMED
--add-opens=java.base/java.lang=ALL-UNNAMED
--add-opens=java.base/java.util=ALL-UNNAMED
--add-opens=java.desktop/javax.swing=ALL-UNNAMED
--add-opens=java.desktop/sun.swing=ALL-UNNAMED
--add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED
--add-opens=java.desktop/java.awt.peer=ALL-UNNAMED
--add-opens=java.desktop/javax.swing.text.html=ALL-UNNAMED
--add-exports=java.desktop/sun.font=ALL-UNNAMED
--add-exports=java.desktop/com.apple.eawt=ALL-UNNAMED
--add-exports=java.desktop/com.apple.laf=ALL-UNNAMED
--add-exports=java.desktop/com.apple.eawt.event=ALL-UNNAMED
```
