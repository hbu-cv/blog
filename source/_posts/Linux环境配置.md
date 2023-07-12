---
title: Linux 环境搭建
date: 2023/7/12 20:46:25
categories: 
- 环境搭建
---
## 更换清华源
```bash
sudo apt-get install vim
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
sudo vim /etc/apt/sources.list
sudo apt-get update && sudo apt-get upgrade
```
```
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
#deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
#deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
#deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
#deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse multiverse
```
## 配置git
```bash
sudo apt install git
```
配置用户
```bash
git config --list
git config --global user.name [username]
git config --global user.email [email]
```
生成ssh秘钥
```bash
ssh-keygen
```
## 安装ZSH
```bash
# 安装zsh
sudo apt-get install zsh

# 内网安装
# 下载文件
git clone https://github.com/ohmyzsh/ohmyzsh
# 若因为网速问题，无法抵达可以用我搬运至码云的链接下载
git clone https://gitee.com/jasonli0012/ohmyzsh
# 赋予安装脚本可执行权限
cd ohmyzsh/tools
chmod +x install.sh
# 安装

./install.sh
rm -rf /home/ray/.oh-my-zsh
./install.sh

# 设置为默认终端
chsh -s /bin/zsh
```
### 设置主题
```bash
# 配置皮肤
sudo gedit ~/.zshrc
sudo vim ~/.zshrc
source ~/.zshrc
# 在文本中找到内容ZSH-THEME修改其后值为所选主题
# 主题目录 ~/ohmyzsh/themes

#安装pk10
git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
vim ~/.zshrc
ZSH_THEME="powerlevel10k/powerlevel10k"
ZSH_THEME="ys"
```
### 主题
```bash
den.zsh-theme                  darkblood.zsh-theme            gallois.zsh-theme              kennethreitz.zsh-theme         norm.zsh-theme                 steeef.zsh-theme
Soliah.zsh-theme               daveverwer.zsh-theme           garyblessington.zsh-theme      kiwi.zsh-theme                 obraun.zsh-theme               strug.zsh-theme
adben.zsh-theme                dieter.zsh-theme               gentoo.zsh-theme               kolo.zsh-theme                 peepcode.zsh-theme             sunaku.zsh-theme
af-magic.zsh-theme             dogenpunk.zsh-theme            geoffgarside.zsh-theme         kphoen.zsh-theme               philips.zsh-theme              sunrise.zsh-theme
afowler.zsh-theme              dpoggi.zsh-theme               gianu.zsh-theme                lambda.zsh-theme               pmcgee.zsh-theme               superjarin.zsh-theme
agnoster.zsh-theme             dst.zsh-theme                  gnzh.zsh-theme                 linuxonly.zsh-theme            pygmalion-virtualenv.zsh-theme suvash.zsh-theme
alanpeabody.zsh-theme          dstufft.zsh-theme              gozilla.zsh-theme              lukerandall.zsh-theme          pygmalion.zsh-theme            takashiyoshida.zsh-theme
amuse.zsh-theme                duellj.zsh-theme               half-life.zsh-theme            macovsky-ruby.zsh-theme        random.zsh-theme               terminalparty.zsh-theme
apple.zsh-theme                eastwood.zsh-theme             humza.zsh-theme                macovsky.zsh-theme             re5et.zsh-theme                theunraveler.zsh-theme
arrow.zsh-theme                edvardm.zsh-theme              imajes.zsh-theme               maran.zsh-theme                refined.zsh-theme              tjkirch.zsh-theme
aussiegeek.zsh-theme           emotty.zsh-theme               intheloop.zsh-theme            mgutz.zsh-theme                rgm.zsh-theme                  tjkirch_mod.zsh-theme
avit.zsh-theme                 essembeh.zsh-theme             itchy.zsh-theme                mh.zsh-theme                   risto.zsh-theme                tonotdo.zsh-theme
awesomepanda.zsh-theme         evan.zsh-theme                 jaischeema.zsh-theme           michelebologna.zsh-theme       rixius.zsh-theme               trapd00r.zsh-theme
bira.zsh-theme                 fino-time.zsh-theme            jbergantine.zsh-theme          mikeh.zsh-theme                rkj-repos.zsh-theme            wedisagree.zsh-theme
blinks.zsh-theme               fino.zsh-theme                 jispwoso.zsh-theme             miloshadzic.zsh-theme          rkj.zsh-theme                  wezm+.zsh-theme
bureau.zsh-theme               fishy.zsh-theme                jnrowe.zsh-theme               minimal.zsh-theme              robbyrussell.zsh-theme         wezm.zsh-theme
candy-kingdom.zsh-theme        flazz.zsh-theme                jonathan.zsh-theme             mira.zsh-theme                 sammy.zsh-theme                wuffers.zsh-theme
candy.zsh-theme                fletcherm.zsh-theme            josh.zsh-theme                 mortalscumbag.zsh-theme        simonoff.zsh-theme             xiong-chiamiov-plus.zsh-theme
clean.zsh-theme                fox.zsh-theme                  jreese.zsh-theme               mrtazz.zsh-theme               simple.zsh-theme               xiong-chiamiov.zsh-theme
cloud.zsh-theme                frisk.zsh-theme                jtriley.zsh-theme              murilasso.zsh-theme            skaro.zsh-theme                ys.zsh-theme
crcandy.zsh-theme              frontcube.zsh-theme            juanghurtado.zsh-theme         muse.zsh-theme                 smt.zsh-theme                  zhann.zsh-theme
crunch.zsh-theme               funky.zsh-theme                junkfood.zsh-theme             nanotech.zsh-theme             sonicradish.zsh-theme
cypher.zsh-theme               fwalch.zsh-theme               kafeitu.zsh-theme              nebirhos.zsh-theme             sorin.zsh-theme
dallas.zsh-theme               gallifrey.zsh-theme            kardan.zsh-theme               nicoulaj.zsh-theme             sporty_256.zsh-theme
```
## Linux安装搜狗输入法
### 安装fcitx
```
sudo apt-get install fcitx
```
### [下载](https://shurufa.sogou.com/linux)
### 安装
```
sudo dpkg -i sogoupinyin_版本号_amd64.deb
```
### 安装依赖
```
sudo apt install libqt5qml5 libqt5quick5 libqt5quickwidgets5 qml-module-qtquick2
sudo apt install libgsettings-qt1
```
## 安装谷歌浏览器
### [下载](https://www.google.cn/chrome/index.html)
### 安装
```
sudo dpkg -i google-chrome-stable_current_amd64.deb
```
## 安装Clash，科学上网
### 下载Linux X64版本的Clash，[下载地址](https://github.com/Fndroid/clash_for_windows_pkg/releases)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/28005866/1685950543240-f5e8cfec-6415-4542-915f-44cfd197b14d.png#averageHue=%23fefefe&clientId=u16afd352-dad6-4&from=paste&height=361&id=uf5c8ee3f&originHeight=542&originWidth=1339&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=116029&status=done&style=none&taskId=ubaab0394-b28e-4146-a624-f646439f655&title=&width=892.6666666666666)
### 解压
```bash
tar -zvxf 安装包
```
### 运行cwf，启动 clash for windows
```bash
setsid ./cwf
```
### 导入节点
### 配置Ubuntu的Network Proxy成下图所示
```bash
Seetings -> Network -> Network Proxy
```
![img_v2_a6d483bf-19de-433b-ab02-716fa8e5a96g.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/28005866/1685951541346-7cbce220-1992-4683-8fd3-1e67333d2372.jpeg#averageHue=%233a3a3a&clientId=u16afd352-dad6-4&from=paste&height=274&id=u5027f59b&originHeight=411&originWidth=453&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=43042&status=done&style=none&taskId=u6b92e61e-1782-4061-9649-23dc87df4e3&title=&width=302)
### 关闭终端在后台运行程序
```bash
setsid ./app
```
## 安装VScode
### [下载](https://code.visualstudio.com/docs/?dv=linux64_deb)
### 安装
```cpp
sudo dpkg -i code_1.79.2-1686734195_amd64.deb
```
### 打开VScode
```bash
code .
```
### 调节标题栏颜色
```bash
设置搜索 : titlestyle
选择： custom
```
## 安装WPS
### [下载](https://linux.wps.cn/)
### 安装
```
sudo dpkg -i wps-office_11.1.0.11698_amd64.deb
```
## 安装飞书
```
sudo dpkg -i Feishu-linux_x64-6.1.12.deb
```
## [安装Zotero](https://www.zotero.org/support/installation)
```bash
sudo mkdir /opt/zotero
./set_launcher_icon
ln -s /opt/zotero/zotero.desktop ~/.local/share/applications/zotero.desktop
```
## 安装SMPlayer播放器
```
sudo add-apt-repository ppa:rvm/smplayer 
sudo apt-get update 
sudo apt-get install smplayer smplayer-themes smplayer-skins 
```
## [安装截屏软件](https://github.com/flameshot-org/flameshot/releases/tag/v12.1.0)
### 设置快捷方式
Settings-> Keyboard Shortcuts
![image.png](https://cdn.nlark.com/yuque/0/2023/png/28005866/1687669857862-f10a8b13-8ea0-49cc-a37b-accb029e06d2.png#averageHue=%23b0aeae&clientId=u78c7db5d-51ea-4&from=paste&height=559&id=ua3034129&originHeight=1118&originWidth=1940&originalType=binary&ratio=2&rotation=0&showTitle=false&size=166588&status=done&style=none&taskId=ue6c059ad-81df-4ae7-a286-9d07e6f3515&title=&width=970)
## [安装Ulauncher](https://ulauncher.io/#Download)
```bash
sudo add-apt-repository ppa:agornostal/ulauncher && sudo apt update && sudo apt install ulauncher
```
