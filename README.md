🧮 Calculadora Simples em JavaScript Puro
![Captura de tela 2025-05-16 141238](https://github.com/user-attachments/assets/24dbaddf-4809-4ed6-bbce-27b57eee571c)


Calculadora web desenvolvida com HTML, CSS e JavaScript vanilla (sem bibliotecas ou frameworks), implementando operações básicas e recursos visuais intuitivos.

✨ Funcionalidades
Operações Suportadas
Adição, subtração, multiplicação e divisão

Porcentagem e sinal negativo (±)

Limpar display (C) e reset total (AC)

Ponto decimal

Teclado físico compatível

Destaques de Código
Lógica Principal (JS)
javascript
function calcular() {
  try {
    // Substitui símbolos visuais por operadores matemáticos
    let expressao = display.value.replace(/×/g, '*').replace(/÷/g, '/');
    const resultado = eval(expressao); // Uso controlado de eval
    display.value = Number.isInteger(resultado) ? resultado : resultado.toFixed(2);
  } catch {
    display.value = 'Erro';
  }
}
Estilização Dinâmica (CSS)
css
.btn-operator {
  background-color: #f69906;
  color: white;
  transition: filter 0.2s;
}

.btn-operator:active {
  filter: brightness(1.2); /* Efeito de clique */
}

.display {
  font-family: 'Segment7', monospace; /* Fonte estilo calculadora antiga */
  text-align: right;
  font-size: 2.5em;
  overflow: hidden;
  text-overflow: ellipsis;
}
Estrutura HTML Semântica
html
<div class="calculadora">
  <input type="text" class="display" readonly>
  <div class="teclado">
    <button class="btn-ac">AC</button>
    <button class="btn-c">C</button>
    <button class="btn-percent">%</button>
    <button class="btn-operator">÷</button>
    <!-- ... outras teclas ... -->
  </div>
</div>
🛠️ Arquitetura do Projeto
/  
├── index.html          # Estrutura principal  
├── style.css           # Estilos completos (Mobile First)  
├── script.js           # Lógica da calculadora (400+ linhas)  
└── assets/             # Opcional: ícones/fontes  
    ├── 7segment.ttf    # Fonte do display  
    └── click.mp3       # Som de tecla (se implementado)  
🎯 Desafios Resolvidos
Precisão Decimal

javascript
// Corrige o problema do 0.1 + 0.2 ≠ 0.3
function ajustarDecimal(num) {
  return parseFloat(num.toFixed(10));
}
Fluxo de Operações

Impede múltiplos operadores consecutivos

Validação de input para evitar eval() malicioso

Responsividade

css
@media (max-width: 500px) {
  .calculadora {
    width: 95vw;
    height: 70vh;
  }
}
🚀 Como Executar
Online: GitHub Pages (adicione link)

Localmente:

bash
git clone https://github.com/seuusuario/calculadora-js.git
cd calculadora-js
# Abra index.html no navegador

🤝 Contribuição
Encontrou um bug? Quer sugerir uma feature?

Abra uma Issue detalhando sua proposta

Faça um Fork e envie um PR com testes

📜 Licença
MIT License - Consulte LICENSE.

⌨️ Desenvolvido por Hyago Garcia de Paiva

"Projeto educativo - parte do meu aprendizado em JS puro"
