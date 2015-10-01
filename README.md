# Brewfile
参考サイト
http://ochiailab.blogspot.jp/2015/03/homebrew-mac.html
http://tech.rockme.co.jp/entry/homebrewcask

#準備
##brewのインストール
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
##Developer tool のインストール
xcode-select --install

sudo xcodebuild -license
##git の設定
git config --global user.name "Your Name"

git config --global user.email "your_email@example.com"

ssh-keygen -t rsa -C "your_email@example.com"
 ~/.ssh/id_rsa.pub の内容を GitHub に登録。
#Homebrew-caskのインストール
#####シンボリックリンクの生成先を /Application に変更するため、~/.zshrc へ下記を追加。
#####caskのDL先をbrewと同じ/usr/local/以下に、シンボリック先を/Applications/に変更
export HOMEBREW_CASK_OPTS="--appdir=/Applications --caskroom=/usr/local/Caskroom"

brew install caskroom/cask/brew-cask

#Homebrew-file のインストール
##brew-file のインストール
brew tap rcmdnk/file

brew install brew-file
##GitHub 上の Brewfile を紐付け
brew file set_repo -r [GitHub のアカウント名]/Brewfile

#アプリのインストール
brew file install
