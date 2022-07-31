[日本語版](README_ja_JP.md)

# Template Repository for Generating User Custom Firmware for M5Burner v3

## System Requirements

- [PlatformIO](https://platformio.org/)([PlatformIO IDE for VSCode](https://platformio.org/install/ide?install=vscode))
- [M5Burner v3](https://docs.m5stack.com/en/download)
- [Git](https://git-scm.com/)

## How to Use

1. Clone the repository and change the current directory to `my_custom_firmware`.  
    ```bash
    git clone https://github.com/3110/m5burner-user-custom-platformio-template.git my_custom_firmware
    cd my_custom_firmware
    ```
1. Edit `platformio.ini` for your custom firmware. You have to set `board` and `lib_deps` at least.
1. Implement `main.cpp`(It has a template code for M5Stack BASIC).
1. Run `pio run`.  
   Command line: 
   ```
   pio run --target firmware
   ```
   PlatformIO IDE for VSCode:  
   Click 'Generate User Custom` on the PlatformIO menu.  
   [![PlatformIO Menu](https://i.gyazo.com/653a56dd4d5625d42b4ec259872633de.png)](https://gyazo.com/653a56dd4d5625d42b4ec259872633de)
1. `firmware/custom_firmware_0.0.1.bin` is generated.

## Customization

You can change the following settings for your custom firmware in `platformio.ini`.

* Firmware Name  
  `custom_firmware_name`(default: `custom_firmware`)
* Firmware Version  
  `custom_firmware_version`(default: `0.0.1`)
* Firmware Extension(with a dot)  
  `custom_firmware_suffix`(default: `.bin`)
* Target Directory  
  `custom_firmware_dir`(default: `firmware`)

If you want to change the target name(`firmware`) for `pio run`, edit the parameter `name` for `env.AddCustomTarget()` in `generate_user_custom.py`.


## References

- [How to Use M5Burner v3](https://zenn.dev/saitotetsuya/articles/m5stack_m5burner_v3)(In Japanese)
