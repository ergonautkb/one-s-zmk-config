# ZMK Firmware for Ergonaut One S keyboard

This is a repository for a ZMK Firmware for Ergonaut One S keyboard.

## Default keymap

Visual representation of the default keymap in keymap-drawer: [keymap-drawer.streamlit.app](https://caksoylar.github.io/keymap-drawer?keymap_yaml=H4sIAAAAAAAC_71WaXfSQBT93l8xnmpplTZl6YbHcwwhUCRAJKGbSwxkECRhMEuRg_jbncybhLRSG9Tjl3tf7sy8ebmzJNuoWlcUVG-hHrbJDA1G2LbQbOQPkYluTTvAyB6NMVp8dcbGGM97xHStEhpg1x15gjfDeLrc2kbERQvi-kNi2OacBH4JLbypPaLsuwHOIpfMvBIqZFGf2IEzofFRFvnDwOnRML8MU3gYo6HvT72SIHym8we9gz5xhL459sjcNl2Bzu6Y033LNWfYFXo26QmOOZoIDfm6KaqGpsrSgWNtQwFbvI4thO5W3ifuBBsu8U0fW7w1qlkRr9td3WCVG4VvR0YhTINdL0xj4YEZ2CzjPnrL8JKhzLDDUGd4zbDLsM6wzVBluKAziVk0pPPVuvVlrGmgiYq-0iqgSXpHWYlVELXzKu9ZY3ged3hzv0MoNtalUtbM-fJebTcMrxhKDC8Ylhm2GDYZZrIZxgcMhTijrEksp4OtkZl4YVWUZNYwMW9Xsi6WoTcJPLySO7LOZG_urMSypkLqSZBQKzK81yCYhCLNDquWyaQlpbZ7sRdFUhxdxdFNFHVhgUMLIQgNhij0P5lUElUNWmTeUGlfgn9d2Bqdeu1cT1tjvQXZzttN2IJqDVVaUcQzyq1KcszCn09xCQ3pIV8mdWourCn1EyqTw5dgS7Cpd7_3dQO__huZ1pc0JiWJbeXSBttJ0XaLe3tJsdypR-sVhnzB_sKolX7RVqLUYchTxzn_jWsP2RS5qeltmFcFanb1cJ_Sk8p9e8fTnXA-5XzG-cMGFUVBkfMR52POrx5wKuFqbHRs0yc-KMc5z7kA_D5teXAfZg65uJ_CRnrLcZcWvPcO5-fAu_C0TO9RCfgpPD2Dp48MX_yBOT942iecX3Pe5vw9dWXwKnA2jBRbi17r4E01lwc-AToFOoNdp0mdVtoSqrkccBHoCOgYNrIiNTY3qJo75AzESy1AcWJXk-mxl8VG2hJFfozYVxN-NsRyiuuLtpZW30v4htKtuPxFy63R8mu0whqtmFIrpJxjXS1RzWUdSUonCtXORRS2rvituOPNPcPFHvajs9MjxLeJaWH3YeXeoETCu9NEk9NfRaS3a3FcVuQ47mrlRxc02e_--CjvQwfh8U_UT6nvgYnZCwAA)

This layout is heavily inspired by [Miryoku layout](https://github.com/manna-harbour/miryoku)

## FAQ

- [FAQ](#faq)
  - [How to change the keymap?](#how-to-change-the-keymap)
  - [How to flash the keyboard?](#how-to-flash-the-keyboard)
  - [How to pair halves?](#how-to-pair-halves)
  - [Problems](#problems)
    - [I'm getting File Transfer Error after copying firmware to the keyboard](#im-getting-file-transfer-error-after-copying-firmware-to-the-keyboard)

### How to change the keymap?

1. Fork or use this repository as a template https://github.com/ergonautkb/one-s-zmk-config.
2. Enable Github Actions for your repository if needed.

You have two options on how to configure your desired keymap:

#### Option 1. Keymap Editor

1. Open [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/).
2. Connect it to your Github account and give an access to your repository to Keymap Editor's app.
3. Make changes to your keymap and press `Save` - it will trigger software build. Wait for it to complete.
4. Grab the `firmware.zip` archive.

#### Option 2. Manual

1. Make changes to the [ergonaut_one.keymap](config/boards/shields/ergonaut_one_s/ergonaut_one_s.keymap) file using your favorite text editor.
2. Commit changes to your repository.
3. Go to `Actions` tab in your Github repository, locate the latest build and wait for it to complete.
4. Grab the `firmware.zip` archive

### How to flash the keyboard?

1. Obtain `firmware.zip`
2. Unzip `firmware.zip` - you should have `ergonaut_one_s_left-seeeduino_xiao_ble-zmk.uf2` and `ergonaut_one_s_right-seeeduino_xiao_ble-zmk.uf2` files
3. Turn off the power for selected halve (move slider to position `OFF`)
4. Connect selected halve to the PC via USB-C cable
5. Press `RESET` button **twice** to enter DFU mode - you should see new USB device in your file manager
6. Copy the corresponding firmware to the root directory of the new USB device
7. Disconnect selected halve from the PC
8. Repeat steps 3-7 for the other halve

### How to pair halves?

1. Turn off the power for both halves (move slider to position `OFF`)
2. Turn on the power for both halves (move slider to position `ON`)
3. Press `RESET` button **once** on both halves **simultaneously**

### Problems

#### I'm getting File Transfer Error after copying firmware to the keyboard

It's OK. Proof: https://zmk.dev/docs/troubleshooting#file-transfer-error
