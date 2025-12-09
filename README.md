# 🏆 Sorteador Corporativo - Documentação

Olá Dr. Hasegawa. Este documento serve como guia para a estrutura e funcionalidades do sistema de sorteio corporativo, desenvolvido em um único arquivo HTML para máxima portabilidade e uso simplificado ("download-e-execute").

## 🚀 Uso Simplificado

Basta baixar o arquivo `Sorteador de Nomes` salvar com .html e abri-lo diretamente em qualquer navegador moderno. Todo o código (HTML, CSS e JavaScript) está contido internamente.

## ✨ Funcionalidades Principais

| Funcionalidade | Detalhe |
| :--- | :--- |
| **Sorteio em Tela Cheia** | Ativado pelo botão "INICIAR SORTEIO", usando uma interface dedicada para visualização em telões. |
| **Animação Aleatória (Fade)** | Utiliza o `keyframes fadeRoll` para um efeito de oscilação (`opacity`) suave durante a rolagem de nomes. |
| **Persistência de Dados** | Listas de Candidatos, Sorteados e Log são salvas automaticamente no `LocalStorage` do navegador. |
| **Importação de Nomes** | Permite carregar listas de nomes via arquivo `.txt` ou `.csv` (um nome por linha). |
| **Gerenciamento de Listas** | Funções de adição individual, exclusão de itens e botões de **Limpar Candidatos** e **Resetar Sorteados**. |
| **Modo Automático** | Sorteia repetidamente em um intervalo definido até que a lista de candidatos se esgote. |
| **Exportação e Impressão** | Exporta o histórico de sorteios para CSV e permite imprimir a lista de vencedores. |
| **Controle por Teclado** | Teclas **ESPAÇO** para sortear e **ESC** para sair da tela cheia. |

## 📐 Estrutura Interna do Código (`index.html`)

Para facilitar a manutenção e por ser um arquivo único, o código é organizado na seguinte sequência:

### 1. HTML (`<body>`)
* **Contêiner Principal (`.container`):** Layout da interface de controle.
* **Overlay de Sorteio (`#tela-cheia-overlay`):** Camada de visualização em tela cheia.
* **Bloco `<script>`:** Posicionado antes do fechamento do `</body>` para garantir o carregamento do DOM.

### 2. Estilos CSS (`<style>`)
* **Configurações Globais:** Definição de cores e temas via variáveis CSS (`:root` e `.tema-escuro`).
* **Animação do Sorteio:** O bloco `@keyframes fadeRoll` é o responsável pelo efeito visual no texto durante o sorteio.

### 3. Lógica JavaScript (`<script>`)

O código JS está segmentado por blocos de comentários para clareza:

| Bloco | Responsabilidade | Funções Chave |
| :--- | :--- | :--- |
| **Persistência** | Carregar/Salvar dados do `LocalStorage`. | `carregarJSON()`, `salvarJSON()` |
| **Utilidade** | Sons e Auxiliares. | `playClickBeep()`, `playWinnerMelody()`, `sleep()` |
| **CRUD & Renderização** | Manipulação das listas e interface. | `atualizarLista()`, `adicionarNome()` |
| **Novas Funções** | Importação e Limpeza de Massa. | `importarNomes()`, `limparCandidatos()` |
| **Sorteio Principal** | Lógica do sorteio e animação. | `realizarRodadaDeSorteio()`, `iniciarSorteio()` |
| **Eventos** | Conexão entre o código e o usuário. | `addEventListener` para todos os botões e eventos de teclado. |

---
*Documentação gerada em 09 de Dezembro de 2025.*
