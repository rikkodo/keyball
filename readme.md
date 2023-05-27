# Keyball series

## About

keyball61の自分用ファームウェア

以下に対応

* Keyboard Quantizerに繋ぐと両方スレーブになってしまうので`MASTER_LEFT`にしてしまう。
* `SAFE_RANGE`がずれていたので、オレオレセーフレンジに書き換え。
  * 0x5DBAを起点とする。

## TODO

というかやりたいけど放置していること。

* LCDにレイヤ情報、モディファイアキー情報を表示するようにする。 (銀弾イメージ）

## 参照

[keyballのための はじめてのQMK firmware環境構築 Mac編](https://note.com/yinouet1001/n/n856b45220ad4)

[goropikariの備忘録 keyball39 を組み立てた 検証2: MASTER_LEFT で固定してしまう](https://goropikari.hatenablog.com/entry/keyball39_build_log#検証2-MASTER_LEFT-で固定してしまう)

<!-- とりあえずオリジナルも残しておく -->

## original below

This directory includes source code of Keyball keyboard seriers:

| Name          | Description
|---------------|-------------------------------------------------------------
|[Keyball46](./keyball46)|A split keyboard with 46 vertically staggered keys and 34mm track ball.
|[Keyball61](./keyball61)|A split keyboard with 61 vertically staggered keys and 34mm track ball.
|[Keyball39](./keyball39)|A split keyboard with 39 vertically staggered keys and 34mm track ball.
|[ONE47](./one47)|A keyboard with 47 vertically keys and 34mm trackball. It will support BLE Micro Pro.
|[Keyball44](./keyball44)|A split keyboard with 44 vertically staggered keys and 34mm track ball.

* Keyboard Designer: [@Yowkees](https://twitter.com/Yowkees)  
* Hardware Supported: ProMicro like footprint
* Hardware Availability: <https://shirogane-lab.com/>

See each directories for each keyboards in a table above.

## How to build

1. Check out this repository.

    ```console
    $ git clone https://github.com/Yowkees/keyball.git keyball
    ```

2. Check out [qmk/qmk_firmware](https://github.com/qmk/qmk_firmware/) repository in another place.

    ```console
    $ git clone https://github.com/qmk/qmk_firmware.git --depth 1 --recurse-submodules --shallow-submodules -b 0.15.13 qmk
    ```

    Currently Keyball firmwares are verified to compile with QMK 0.16.13

3. Create a symbolic link to this `keyball/` directory from [qmk/qmk_firmware]'s `keyboards/` directory.

    ```console
    $ ls
    keyball/ qmk/

    $ cd qmk/keyboards
    $ ln -s ../../keyball/qmk_firmware/keyboards/keyball keyball
    $ ls keyball/
    drivers/  keyball46/  keyball61/  lib/  readme.md
    $ cd ..
    ```

4. `make` your Keyball firmwares.

    ```console
    $ make -j8 SKIP_GIT=yes keyball/keyball61:default
    ```

## How to create your keymap

(to be documented)

