# MiniArcade
Um mini arcade feito com Raspberry Pi para o trabalho de Microcontroladores

### Materiais Utilizados

* Raspberry Pi 3 Model B
* Cartão de Memória
* Tela touchscreen de 7 polegadas para o Raspberry Pi
* 8 Botões de arcade
* 1 Joystick de arcade
* 1 Protoboard com GPIO Extension Board
* Fios
* Terminais Macho para conectar os fios na protoboard

### Equipamentos Utilizados

* Ferro de solda
* Alicate
* CNC Router para cortar a madeira

### Instruções para a caixa

1. Modelar as peças no Solid (arquivos fornecidos na pasta: Projetos do Solid/).
2. Exportar as peças na extensão .DXF (arquivos fornecidos na pasta: Arquivos DXF/).
3. Realizar o corte das peças na CNC Router.
4. Colar as peças.
5. Soldar os fios nos terminais dos botões e joystick.
6. Prender os botões e joystick na caixa.

### Instruções do Raspberry Pi

1. Formatar o cartão de memória
2. Baixar a imagem do retropie: https://retropie.org.uk/download/
3. Instalar o retropie no cartão memória (Programa recomendado: Etcher).
4. Instalar a biblioteca Adafruit-Retrogame para utilizar os GPIO's
    1. Ligar o Raspberry Pi com o cartão de memória e aperta F4.
    2. Rodar os comandos:
        ```
        cd
        curl https://raw.githubusercontent.com/adafruit/Raspberry-Pi-Installer-Scripts/master/retrogame.sh >retrogame.sh
        sudo bash retrogame.sh
        ```
    3. Escolher a opção "PiGGRL 2".
    4. Abrir o arquivo retrogame.cfg localizado em /boot/retrogame.cfg.
    5. Confirmar o arquivo de configuração:
        ```
        # Sample configuration file for retrogame.
        # Really minimal syntax, typically two elements per line w/space delimiter:
        # 1) a key name (from keyTable.h; shortened from /usr/include/linux/input.h).
        # 2) a GPIO pin number; when grounded, will simulate corresponding keypress.
        # Uses Broadcom pin numbers for GPIO.
        # If first element is GND, the corresponding pin (or pins, multiple can be
        # given) is a LOW-level output; an extra ground pin for connecting buttons.
        # A '#' character indicates a comment to end-of-line.
        # File can be edited "live," no need to restart retrogame!
 
        # Here's a pin configuration for the PiGRRL 2 project:
 
        LEFT       4  # Joypad left
        RIGHT     19  # Joypad right
        UP        16  # Joypad up
        DOWN      26  # Joypad down
        LEFTCTRL  14  # 'A' button
        LEFTALT   15  # 'B' button
        Z         20  # 'X' button
        X         18  # 'Y' button
        SPACE      5  # 'Select' button
        ENTER      6  # 'Start' button
        A         12  # Left shoulder button
        S         13  # Right shoulder button
        ESC       5 6  # Exit ROM; PiTFT Button 1
        1         22  # PiTFT Button 2
        2         23  # PiTFT Button 3
        3         27  # PiTFT Button 4
 
        # For configurations with few buttons (e.g. Cupcade), a key can be followed
        # by multiple pin numbers.  When those pins are all held for a few seconds,
        # this will generate the corresponding keypress (e.g. ESC to exit ROM).
        # Only ONE such combo is supported within the file though; later entries
        # will override earlier.
        ```
    6. Mais informações: https://learn.adafruit.com/retro-gaming-with-raspberry-pi/adding-controls-hardware?view=all#download-and-install-4-3
5. Instalar as ROM's no Raspberry Pi: https://retropie.org.uk/docs/Transferring-Roms/
6. Conectar os fios nas seguintes GPIO's:

    Botão | GPIO 
    --- | --- 
    Cima | 16
    Baixo | 26
    Direita | 19
    Esquerda | 4
    A | 14
    B | 15
    X | 20
    Y | 18
    *Shoulder* Esquerdo | 12
    *Shoulder* Direito | 13
    Start | 6
    Select | 5
