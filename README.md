# Curso STM32

Minhas anotações e atividades do treinamento do professor Gabriel Moreira Vigiano sobre os microcontroladores da família [STM32 32-bit ARM Cortex MCUs](https://www.st.com/en/microcontrollers-microprocessors/stm32-32-bit-arm-cortex-mcus.html).

Este repositório contém exercícios, códigos de exemplo, documentação e recursos sobre o curso. Utilize os links abaixo para acessar rapidamente os conteúdos.

---

## Documentação e Ferramentas

- **Fabricante**: [STMicroelectronics](https://www.st.com/content/st_com/en.html)
- [STM32 MPU wiki](https://wiki.st.com/stm32mpu)
- [STM32 MCU wiki](https://wiki.st.com/stm32mcu)
- [HALs disponibilizado pela ST](https://www.st.com/content/st_com/en/search.html#q=hardware%20abstraction%20layer%20-t=resources-page=1)

- [STM32Cube github](https://github.com/STMicroelectronics)
- [STM32CubeIDE resource portal on wiki](https://wiki.st.com/stm32mcu/index.php?title=STM32CubeIDE:Introduction_to_STM32CubeIDE&sfr=stm32mcu)
---

## Módulos

### 1. [Microcontroladores e Processadores ARM](#1-microcontroladores-e-processadores-arm)

A família do Cortex tem três categorias principais:
1. ARM Cortex-A (p/ processadores)
2. ARM Cortex-R (p/ aplicações em tempo real)
3. ARM Cortex-M (p/ microcontroladores)

![Famílias Cortex](imgs/familias_cortex.png)

- [8-bit vs. 32-bit MCU: Choosing the Right Microcontroller for Your PCB Design](https://resources.altium.com/p/8-bit-vs-32-bit-mcu-choosing-right-microcontroller-your-pcb-design)

Alguns conceitos:
- **Firmware** -  um tipo de software que é armazenado em um dispositivo eletrônico e que controla o funcionamento deste dispositivo.
- **Linguagens de programação para MCU's** - C, C++, Assembly, Python, Java Basic e Pascal.
- **Bare Metal** - programação de um sistema operacional instalado diretamente no hardware, sem camadas de software de gestão e hipervisores.
- **HAL (Hardware Adstraction Layer) e LL (Low-Layer) APIs** - O HAL é uma camada de software que permite a comunicação entre o software e o hardware, e o Low-Layer APIs são mais detalhadas e específicas do que as High-Level APIs, permitindo um controle mais granular.

### 2. [Softwares e Recursos](#2-softwares-e-recursos)
- **IDE**: [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html)
- **Gravador**: [STM32CubeProg](https://www.st.com/en/development-tools/stm32cubeprog.html)
- **Servidor ST-LINK**: [ST-LINK server](https://www.st.com/en/development-tools/st-link-server.html)
- **Núcleo Board**: [NUCLEO-L476RG](https://www.st.com/en/evaluation-tools/nucleo-l476rg.html), [UM1724: STM32 Nucleo-64 boards (MB1136)](https://www.st.com/content/ccc/resource/technical/document/user_manual/98/2e/fa/4b/e0/82/43/b7/DM00105823.pdf/files/DM00105823.pdf/jcr:content/translations/en.DM00105823.pdf), [Schematic MB1136-C05](https://www.st.com/resource/en/schematic_pack/mb1136-default-c05_schematic.pdf), [Datasheet STM32L476xx](https://www.st.com/resource/en/datasheet/stm32l476je.pdf). 
- **Upgrade St-Link**: ![U](imgs/upgrade_stlink.png)

### 3. [Revisão de Linguagem C Básica](#3-revisão-de-linguagem-c-básica)

- Pratique em [Dev-C++](https://sourceforge.net/projects/orwelldevcpp/).

- [Tabelas de valores e unidades em C](https://www.each.usp.br/digiampietri/ACH2023/tabelasemc.html)

- [Tabela ASCII](https://www.ibm.com/docs/pt-br/aix/7.3?topic=adapters-ascii-decimal-hexadecimal-octal-binary-conversion-table)

- [Calculadora de Conversão de Bases Numéricas](https://www.calculadoraonline.com.br/conversao-bases)

- [Guia da linguagem C - Embarcados](https://embarcados.com.br/linguagem-c-guia-completo/)  

### 4. [Ambientes, Projetos e Depurador SWD](#4-ambientes-projetos-e-depurador-swd)

- Board Selector: [NUCLEO-L476RG](https://www.st.com/en/evaluation-tools/nucleo-l476rg.html#overview)

- Compilar: *Project>Build All*
- Debugger: *Run>Debug As>1 STM32 Cortex-M C/C++ Application*

    Click em *Apply* e *OK* na janela de configuração do debugger.
    ![alt text](imgs/win_config_debugger.png)

-  Debugger Serial:   
    ![alt text](imgs/config_debugger_serial.png)

    Em *Run>Debug Configurations*, habilite em *Debugger* o recurso *Serial Wire Viewr (SWV)*. 
    
    ![alt text](imgs/swv.png)

    Ao entrar do modo *Debugger* vai em *Window>Show View> SWV>SWV Data Trace Timerline Graph*

    Click em *Configure trace* e na aba inicializada deixe as seguinte opções:
    ![alt text](imgs/swv2.png)

### 5. [Gravação, Bootloader e Customização](#5-gravação-bootloader-e-customização)
- Modelos de ST-Links: [ST-LINK/V2](https://www.st.com/en/development-tools/st-link-v2.html) e [STLINK-V3](https://www.st.com/en/development-tools/stlink-v3set.html)

- Habilitando a geração dos arquivos Bin e Hex ao compilar: 
    
    Va em "*Project>Properties>C/C++ Build>Settings*", e deixe marcado as seguinte opções:
    ![alt text](imgs/config_gerar_bin_hex.png)


- [STM32 M4 Clicker](https://www.mikroe.com/clicker-stm32f4)    

- STM32 microcontroller system memory boot mode: [AN2606](https://www.st.com/content/ccc/resource/technical/document/application_note/b9/9b/16/3a/12/1e/40/0c/CD00167594.pdf/files/CD00167594.pdf/jcr:content/translations/en.CD00167594.pdf)

![alt text](imgs/boot_modes.png)

- Para gravação do firmware via UART, use o [FLASHER-STM32](https://www.st.com/en/development-tools/flasher-stm32.html) ou o [STM32CubeProg](https://www.st.com/en/development-tools/stm32cubeprog.html), e faça uma das conexão indicadas na tabela 152 do ***application note* AN2606**. 

    NOTA: Coloque o **BOOT0** em nível logico alto para gravação do firmware. ![alt text](imgs/pin_boot0.png)

- Cuidados com o ***Option Bytes***: [AN4758](https://www.st.com/resource/en/application_note/an4758-proprietary-code-readout-protection-on-stm32l4-stm32l4-stm32g4-and-stm32wb-series-mcus-stmicroelectronics.pdf) e [AN4701](https://www.st.com/resource/en/application_note/an4701-proprietary-code-readout-protection-on-microcontrollers-of-the-stm32f4-series-stmicroelectronics.pdf)

- Bootloader Customizado
    - Referencias: [AN3155](https://www.st.com/resource/en/application_note/an3155-usart-protocol-used-in-the-stm32-bootloader-stmicroelectronics.pdf) e AN2606.
    - Terminal RS232: [Termite](https://www.compuphase.com/software_termite.htm)
    - O *baud rate* deve está entre 1200 e 115200, e a paridade em *even*.

    ![Figura 1 - AN3155](imgs/an3155-fig1.png)

    USART bootloader commands: ![Tabela 2 - AN3155](imgs/an3155-tab2.png)

### 6. [Clocks do STM32](#6-clocks-do-stm32)
- Documentação: [AN2867](https://www.st.com/resource/en/application_note/an2867-guidelines-for-oscillator-design-on-stm8afals-and-stm32-mcusmpus-stmicroelectronics.pdf)

- Configurado em ***System Core>RCC***: 

    ![alt text](imgs/config_clock.png)

- Ociladores - Crytal X3
    - Valores de *load capacitance*:![alt text](imgs/clock_load_capacitance.png)

        **NOTA**: A capacitância de dispersão $C_S$ pode se estimado como $2pF$ ou $5pF$, o $C_L$ é fornecido pelo fabricante do crytal selecionado, e $C_{L1}$ e $C_{L2}$ são os valores dos capacitores C33 e C34.

        ![alt text](imgs/cirtuito_crytal_externo.png)
- Ociladores - Crytal Externo
    - Pinos para conexão externa: 
    ![alt text](imgs/conexão_crytal_externo.png)
        **NOTA**: Recomendado utilizar crytal de $16MHz$ ou $8MHz$ para projetos com HSE.

### 7. [Gpio's do STM32](#7-gpios-do-stm32)
- Documentação: [AN4899](https://www.st.com/resource/en/application_note/an4899-stm32-microcontroller-gpio-hardware-settings-and-lowpower-consumption-stmicroelectronics.pdf)

- **NOTA**: Na seção ***"Output driving current"*** do datasheet,  encontram-se as informações sobre a corrente máxima que os pinos de GPIO podem suportar, seja ao receber (sink) da carga conectada, ou ao fornecer (source) para ela. 

- Opções de configura:
    - GPIO mode: ![alt text](imgs/gpio_mode.png)

- **Debounce** é uma técnica que evita que um interruptor físico seja detectado múltiplas vezes quando pressionado ou liberado. 
    - **NOTA**: Ao utilizar um botão, use um capacito ($1uF$) em paralelo ao mesmo.

- **Interrupção** é uma funcionalidade que interrompe a tarefa atual do processador para processar um evento.

### 8. [Timers do STM32](#8-timers-do-stm32)

### 9. [OC, IC e PWM, DeadTime e Frequência Variável](#9-oc-ic-e-pwm-deadtime-e-frequência-variável)

### 10. [ADC (Conversor Analógico Digital)](#10-adc-conversor-analógico-digital)

### 11. [DAC (Conversor Digital Analógico)](#11-dac-conversor-digital-analógico)

### 12. [WDT - Watchdog com STM32](#12-wdt---watchdog-com-stm32)

### 13. [Modos de Baixo Consumo (Low Power Modes)](#13-modos-de-baixo-consumo-low-power-modes)

### 14. [RTC (Real Time Clock Interno do STM32)](#14-rtc-real-time-clock-interno-do-stm32)

### 15. [Comunicação Serial - USART](#15-comunicação-serial---usart)

### 16. [Comunicação I2C](#16-comunicação-i2c)

### 17. [Comunicação SPI](#17-comunicação-spi)
- ***Serial Peripheral Interface* (SPI)**:
    - Alta velocidade (20MHz)
    - Conexões e Pinos:
    ![alt text](imgs/spi_conexao.jpg)

    - **Modos de Operação**: consistem em quatro combinações de *Clock Polarity*(CPOL) e *Clock Phase* (CPHA).

        | Modo | CPOL | CPHA | Borda de Troca | Transição | Nível em IDLE |
        |:-: | :-: | :-: |:-----:| :--------: | :----: |
        | 0  | 0   | 0   | Subida | Meio do bit | 1 |
        | 1  | 0   | 1   | Decida | Começo do bit | 0 |
        | 2  | 1   | 0   | Decida | Meio do bit | 0 |
        | 3  | 1   | 1   | Subida | Começo do bit |1 |

        **NOTA**: Os modos 0 e 3 são os mais utilizados.

        ![alt text](imgs/spi_modos.png)

        **NOTA**: O CPOL define o nível inicial do clock, sendo 0 para nível baixo e 1 para nível alto, enquanto o CPHA determina o momento da transição, sendo 0 para a transição no meio do bit, e 1 para a transição no início do bit.

    - Informações Complementares:

        [Artigo: Hardware - Interface SPI by Leonardo Ritter](https://www.hardwarecentral.net/single-post/2018/08/29/hardware-interface-spi) 

        ![alt text](imgs/spi_inf_complementar.png)
        ![alt text](imgs/spi_inf_complementar_01.png)
        ![alt text](imgs/spi_inf_complementar_02.png)

- Componente que usam comunicação SPI: [MCP4921](https://ww1.microchip.com/downloads/en/DeviceDoc/21897B.pdf), [MCP3008](https://ww1.microchip.com/downloads/aemDocuments/documents/MSLD/ProductDocuments/DataSheets/MCP3004-MCP3008-Data-Sheet-DS20001295.pdf), [ADE9000](https://www.analog.com/en/products/ade9000.html).

### 18. [FreeRTOS](#18-freertos)

### 19. [LCD 16x2](#19-lcd-16x2)

### 20. [SdCard](#20-sdcard)

### 21. [TouchGF Designer](#21-touchgf-designer)

### 22. [Nextion Display](#22-nextion-display)

### 23. [Modbus - RTU Serial e Ethernet](#23-modbus---rtu-serial-e-ethernet)

### 24. [Processamento Digital de Sinais](#24-processamento-digital-de-sinais)

### 25. [Comunicação CAN](#25-comunicação-can)

### 26. [CMSIS-DSP](#26-cmsis-dsp)

### 27. [Memória Flash Interna do STM32](#27-memória-flash-interna-do-stm32)

### 28. [Bootloader - Sistema de Memória](#28-bootloader---sistema-de-memória)

---

