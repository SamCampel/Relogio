# Relógio Analógico com CSS e JavaScript

Este projeto é um relógio analógico desenvolvido juntamente ao curso JavaScript30 que monstra as horas, minutos e segundos em tempo real.

## Estrutura do Projeto

O projeto consiste em um único arquivo HTML que contém:

- **HTML**: Estrutura do relógio.
- **CSS**: Estilização do relógio, incluindo o design circular e os ponteiros.
- **JavaScript**: Lógica para atualizar os ponteiros do relógio com base no horário atual.

## Pré-visualização

O relógio possui um design minimalista com:

- Fundo gradiente.
- Ponteiros estilizados para horas, minutos e segundos.
- Animação suave para os movimentos dos ponteiros.

## Como Usar

1. Faça o download ou clone este repositório.
2. Abra o arquivo `ClockCSS+JS.html` em qualquer navegador moderno.
3. O relógio será exibido e começará a funcionar automaticamente.

## Código Principal

### CSS
O estilo do relógio é definido diretamente no arquivo HTML dentro da tag `<style>`. Ele inclui:

- Um fundo gradiente para o corpo.
- Um design circular para o relógio.
- Estilização dos ponteiros com animações suaves.

### JavaScript
O script utiliza o método `setInterval` para atualizar os ponteiros a cada segundo. A lógica principal está na função `setDate`, que calcula os ângulos de rotação com base no horário atual.

```javascript
const secondHand = document.querySelector('.second-hand');
const minuteHand = document.querySelector('.minute-hand');
const hourHand = document.querySelector('.hour-hand');

function setDate() {
    const now = new Date();

    const seconds = now.getSeconds();
    const secondsDegrees = ((seconds / 60) * 360);
    secondHand.style.transform = `rotate(${secondsDegrees}deg)`;

    const mins = now.getMinutes();
    const minsDegrees = ((mins / 60) * 360);
    minuteHand.style.transform = `rotate(${minsDegrees}deg)`;

    const hour = now.getHours();
    const hourDegrees = ((hour % 12) / 12) * 360 + (mins / 60) * 30;
    hourHand.style.transform = `rotate(${hourDegrees}deg)`;
}

setInterval(setDate, 1000);
setDate();
