[In English](README.md)

# M5Burner v3で独自ファームウェアを生成する雛形

## 動作環境

- [PlatformIO](https://platformio.org/)（[PlatformIO IDE for VSCode](https://platformio.org/install/ide?install=vscode)）
- [M5Burner v3](https://docs.m5stack.com/en/download)
- [Git](https://git-scm.com/)

## 使用方法

1. このリポジトリをクローンし，`my_custom_firmware`ディレクトリに移動します。  
    ```bash
    git clone https://github.com/3110/m5burner-user-custom-platformio-template.git my_custom_firmware
    cd my_custom_firmware
    ```
1. 独自ファームウェアに合わせて`platformio.ini`を編集します。少なくとも`board`と`lib_deps`を設定する必要があります。
1. `main.cpp`(M5Stack BASIC用のサンプルコードになっています)を実装します。
1. `pio run`を実行します。
   コマンドラインの場合：  
   ```
   pio run --target firmware
   ```  
   PlatformIO IDE for VSCodeの場合：  
   PlatformIOメニューの「Generate User Custom」をクリックします。  
   [![PlatformIOメニュー](https://i.gyazo.com/653a56dd4d5625d42b4ec259872633de.png)](https://gyazo.com/653a56dd4d5625d42b4ec259872633de)
1. コマンドを実行すると`firmware/custom_firmware_0.0.1.bin`が生成されます。
## カスタマイズ

生成される独自ファームウェアに関する設定を変更したい場合は`platformio.ini`の以下の項目を変更してください。

* ファームウェアの名前  
  `custom_firmware_name`（初期値：`custom_firmware`）
* ファームウェアのバージョン  
  `custom_firmware_version`（初期値：`0.0.1`）
* ファームウェアの拡張子（ドットも必要）  
  `custom_firmware_suffix`（初期値：`.bin`）
* 生成先  
  `custom_firmware_dir`（初期値：`firmware`）

独自ファームウェアのを生成する`pio run`のターゲット（`firmware`）を変更したい場合は，`generate_user_custom.py`の`env.AddCustomTarget()`に渡している`name`パラメータの値を変更してください。
