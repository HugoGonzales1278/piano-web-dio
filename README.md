# piano-web-dio
projeto piano virtual
# 🎹 Piano Arranjador Digital — 61 Teclas

Um teclado arranjador interativo completo, feito em **HTML + CSS + JavaScript puro**, sem dependências externas. Roda direto no navegador com som gerado pela Web Audio API.

![Piano Arranjador](https://img.shields.io/badge/HTML-5-orange?style=flat-square&logo=html5)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=flat-square&logo=javascript)
![Web Audio API](https://img.shields.io/badge/Web%20Audio%20API-nativo-blue?style=flat-square)
![Licença](https://img.shields.io/badge/licença-MIT-green?style=flat-square)

---

## ✨ Funcionalidades

- **61 teclas** interativas (brancas e pretas) com resposta visual ao clique
- **40 timbres** com síntese de som via osciladores e envelope ADSR
- **40 ritmos** selecionáveis no painel
- **Display LED** mostrando nota tocada, timbre ativo e BPM em tempo real
- **Metrônomo** sonoro com acento no tempo forte
- **Sustain** para sustentar as notas após soltar a tecla
- **Vibrato** via LFO (oscilador de baixa frequência a 5.5 Hz)
- **Acorde Automático** — toca tríade maior ao pressionar qualquer nota
- **Gravação e Reprodução** com timestamp preciso de cada nota
- **5 melodias de demonstração** integradas
- **Teclado do computador** mapeado para as teclas do piano
- Totalmente **responsivo** e **sem dependências** externas

---

## 🚀 Como usar

### Opção 1 — Abrir direto no navegador

```bash
git clone https://github.com/seu-usuario/piano-arranjador.git
cd piano-arranjador
# Abra o arquivo no navegador:
open piano-arranjador.html        # macOS
xdg-open piano-arranjador.html   # Linux
start piano-arranjador.html       # Windows
```

### Opção 2 — Servidor local (recomendado para evitar restrições de CORS)

```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .
```

Acesse `http://localhost:8080` no navegador.

---

## ⌨️ Controles do teclado do computador

| Tecla do computador | Nota musical |
|---|---|
| `A` | Dó (C4) |
| `W` | Dó# (C#4) |
| `S` | Ré (D4) |
| `E` | Ré# (D#4) |
| `D` | Mi (E4) |
| `F` | Fá (F4) |
| `T` | Fá# (F#4) |
| `G` | Sol (G4) |
| `Y` | Sol# (G#4) |
| `H` | Lá (A4) |
| `U` | Lá# (A#4) |
| `J` | Si (B4) |
| `K` | Dó (C5) |

> **Dica:** use o slider **Oitava** para transpor todas as teclas para cima ou para baixo.

---

## 🎛️ Painel de controles

| Controle | Descrição |
|---|---|
| **Timbre** | Seleciona o instrumento (40 opções) |
| **Ritmo** | Seleciona o estilo rítmico (40 opções) |
| **Volume** | Volume geral do instrumento |
| **Ritmo Vol** | Volume do metrônomo/ritmo |
| **Tempo** | BPM — de 40 a 240 |
| **Oitava** | Transpõe o teclado de C2 a C6 |
| **Sustain** | Mantém as notas ressoando após soltar |
| **Vibrato** | Adiciona modulação de frequência à nota |
| **Metrônomo** | Liga/desliga o metrônomo sonoro |
| **Acorde Auto** | Toca automaticamente a tríade maior |

---

## 🎼 Botões de transporte

| Botão | Função |
|---|---|
| ⏺ **Gravar** | Inicia/para a gravação das notas tocadas |
| ▶ **Reproduzir** | Reproduz as notas gravadas com timing original |
| ⏹ **Parar** | Para a reprodução e silencia todas as notas |
| ♪ **Demo** | Toca uma das 5 melodias de demonstração |
| ✕ **Limpar** | Apaga a gravação atual |

---

## 🔊 Como o som é gerado

O projeto usa exclusivamente a **Web Audio API** nativa do navegador — sem bibliotecas externas.

Cada instrumento é modelado com:

- **Oscilador** (`OscillatorNode`) com forma de onda selecionada por timbre: `sine`, `triangle`, `sawtooth` ou `square`
- **Envelope ADSR** via `GainNode` com rampa linear para Attack, Decay, Sustain e Release
- **LFO** (`OscillatorNode` de 5.5 Hz conectado à frequência principal) quando o Vibrato está ativo
- **GainNode master** para controle de volume em tempo real

```
Oscilador → GainNode (ADSR) → AudioContext.destination
    ↑
  LFO → LFO GainNode (quando Vibrato ativo)
```

---

## 🎹 Timbres disponíveis

Piano Acústico, Piano Elétrico, Cravo, Órgão Clássico, Órgão Hammond, Guitarra Acústica, Guitarra Elétrica, Guitarra Distorcida, Baixo Elétrico, Baixo Fretless, Cordas, Violino, Viola, Violoncelo, Contrabaixo, Flauta, Flauta Doce, Oboé, Clarinete, Fagote, Saxofone Alto, Saxofone Tenor, Trompete, Trombone, Tuba, Corne Francês, Sintetizador Lead, Sintetizador Pad, Sintetizador Bass, Vibrafone, Marimba, Xilofone, Glockenspiel, Acordeão, Harpa, Alaúde, Banjo, Mandolim, Ukulele, Sitar.

---

## 🗂️ Estrutura do projeto

```
piano-arranjador/
└── piano-arranjador.html   # Arquivo único — HTML + CSS + JS
```

Todo o código está em um único arquivo autocontido, sem nenhuma dependência externa.

---

## 🛠️ Tecnologias

- HTML5
- CSS3 (Grid, Flexbox, Custom Properties)
- JavaScript ES6+ (Web Audio API, Pointer Events, Classes)

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Abra uma _issue_ ou envie um _pull request_.

1. Faça um fork do repositório
2. Crie sua branch: `git checkout -b feature/minha-feature`
3. Commit suas mudanças: `git commit -m 'feat: adiciona nova funcionalidade'`
4. Push para a branch: `git push origin feature/minha-feature`
5. Abra um Pull Request

---

## 📄 Licença

Este projeto está sob a licença [MIT](LICENSE).

---

> Feito com ♪ e JavaScript puro.
