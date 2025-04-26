# Medidor de Resistores com Raspberry Pi Pico e Display OLED SSD1306

Este projeto implementa um **medidor de resistência** usando o **Raspberry Pi Pico**, que lê a resistência desconhecida através do ADC e exibe no display OLED o valor medido, além das **cores correspondentes** à faixa E24 (padrão de resistores comerciais).

---

## Funcionalidades

- Mede um resistor desconhecido usando um divisor de tensão.
- Calcula o valor mais próximo da série E24.
- Mostra a resistência e as três cores correspondentes no display OLED SSD1306 via I2C.
- Permite entrar no modo BOOTSEL (upload de firmware) com o botão B.

---

## Hardware Utilizado

- **Microcontrolador**: Raspberry Pi Pico
- **Display OLED**: SSD1306 (I2C)
- **Resistor conhecido**: 10kΩ
- **Entradas Analógicas**: GPIO 28 (ADC2)
- **Botões**:
- **Botão A**: GPIO 5
- **Botão B**: GPIO 6 (modo BOOTSEL)

---

## Como Funciona

1. **Leitura Analógica**: O ADC lê a tensão no divisor de tensão.
2. **Cálculo da Resistência**: O código cálcula a resitência desconhecida com base no principio do dividor de tensão.
3. **Aproximação E24**: Ajusta o valor calculado para o resistor comercial mais próximo da tabela E24.
4. **Conversão para Cores**: Converte o valor em três faixas de cores padrão.
5. **Exibição**: O display mostra:
    - Cores correspondentes
    - Valor lido no ADC
    - Valor estimado da resistência
6. **Modo BOOTSEL**: Pressione o botão B (GPIO 6) para entrar em modo de atualização de firmware.


---