# 🏆 Sorteador Corporativo Simples (HTML/CSS/JS)

Um aplicativo de sorteio de nomes robusto, que funciona em uma única página HTML, sem dependências externas (exceto para os confetes). Ideal para eventos internos, com animação, áudio do Tema da Vitória e persistência de dados.

## 🚀 Como Usar

1.  **Baixe:** Salve o código completo em um arquivo `.html` (ex: `sorteio.html`).
2.  **Abra:** Dê um duplo clique no arquivo para executá-lo no seu navegador.

> **Nota:** Seus dados (candidatos e sorteados) são salvos automaticamente no seu navegador (`localStorage`).

---

## ✨ Funcionalidades

| Ação | Descrição |
| :--- | :--- |
| **Sorteio Múltiplo** | Sorteia vários vencedores de uma vez com animação. |
| **Persistência** | Mantém as listas salvas após fechar e reabrir o arquivo. |
| **Tema da Vitória** | Toca uma melodia de celebração e lança confetes ao sortear. |
| **`↩️ Voltar Nomes`** | Move todos os vencedores de volta para a lista de Candidatos (Reset). |
| **`🖨️ Imprimir`** | Gera um formato limpo para imprimir a lista de vencedores. |

---

## 💻 Estrutura Técnica

O projeto utiliza puramente **HTML, CSS e JavaScript Vanilla**.

* O JavaScript usa a **Web Audio API** para gerar os sons dinamicamente.
* O gerenciamento de dados é feito com **`localStorage`**.
