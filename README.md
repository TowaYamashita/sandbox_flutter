# sandbox_flutter

## Environment

```shell
$ code --version
1.87.2
863d2581ecda6849923a2118d93a088b0745d9d6
arm64

$ fvm --version
3.1.3

$ rbenv --version
rbenv 1.2.0

$ xcodebuild -version         
Xcode 15.3
Build version 15E204a

❯ cat /Applications/Android Studio.app/Contents/Resources/product-info.json | grep \"version\":
"version": "AI-232.10227.8.2321.11479570",
```

## Getting Started

- https://apps.apple.com/jp/app/xcode/id497799835?mt=12 からXcodeをインストールする

- https://developer.android.com/studio?hl=ja からAndroid Studioをインストールする
  - インストール後、Android StudioのSettingsからSDK Platform-Toolsをインストールする

- リポジトリをローカル環境に落としてくる

```shell
$ git clone https://github.com/TowaYamashita/sandbox_flutter
$ cd sandbox_flutter
```

- homebrewでfvmをインストールする
```shell
# https://fvm.app/documentation/getting-started/installation
$ brew tap leoafarias/fvm
$ brew install fvm
$ fvm use
```

- homebrewでrbenvをインストールする

```shell
$ brew install rbenv ruby-build
$ cat - << 'EOS' >> ~/.zprofile
eval "$(rbenv init -)"

# gem install 時にrbenvのRubyを使うようにする
# https://guides.cocoapods.org/using/getting-started.html#sudo-less-installation
export GEM_HOME=$HOME/.rbenv/versions/3.2.3/lib/ruby/gems/3.2.0
export PATH=$GEM_HOME/bin:$PATH
EOS
$ source ~/.zprofile

# .ruby-version のバージョンのRubyをインストールする
$ rbenv install
$ rbenv rehash
```

- cocoapodsをインストールする

```shell
$ gem install cocoapods
```

- Xcode や Android Studio, Android toolchain 周りの設定でエラーが出ていないか確認する

```shell
$ flutter doctor --verbose
```

- コマンドパレットを立ち上げて「Flutter: Launch Emulator」を入力して、適当なシミュレータを立ち上げる

- アプリを立ち上げる

```shell
$ flutter run --debug
```
