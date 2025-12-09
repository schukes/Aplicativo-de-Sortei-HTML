# 🏆 Sorteador Sequencial Interativo

Este é um projeto simples de Front-End (HTML, CSS e JavaScript Vanilla) que implementa um sistema de sorteio corporativo com foco na **interatividade e controle manual** do fluxo de vencedores.

O código-fonte completo é composto por um único arquivo `.html` que contém toda a lógica e estilos.

---

## ✨ Funcionalidade Principal: Sequencial Interativo

O sistema foi desenhado para realizar sorteios **um a um**, permitindo que o apresentador ou operador controle o tempo entre a revelação de cada vencedor.

1.  **Sorteio de 1 Vencedor:** Ao clicar em **"Sortear Vencedor"**, o sistema executa uma animação de rolagem rápida (com efeitos sonoros) e anuncia o ganhador com confetes.
2.  **Pausa Obrigatória:** Após revelar o vencedor, o sorteio **pausa automaticamente**. O nome do ganhador é fixado na área de resultado para visualização.
3.  **Continuação Manual:** O botão **"Sortear Vencedor"** é substituído por **"Continuar Sorteio"**. O sorteio só prossegue para o próximo nome quando o usuário clica neste botão.
4.  **Exclusão Imediata:** Cada nome sorteado é movido instantaneamente da lista **"Candidatos"** para a lista **"Sorteados"** (Vencedores).

O processo é repetido sequencialmente até que a lista de Candidatos esteja vazia.

---

## 💾 Persistência e Controles

O sistema utiliza o **`localStorage`** do navegador para garantir que os dados das listas de Candidatos e Sorteados não sejam perdidos ao recarregar a página.

### Controles de Lista (Sempre Ativos)

Os botões auxiliares de gerenciamento de listas permanecem **ativos** mesmo durante a pausa interativa do sorteio (após um vencedor ser revelado), permitindo ações administrativas a qualquer momento:

| Botão | Função | Estado durante a Pausa |
| :--- | :--- | :--- |
| **Imprimir Vencedores** | Abre a janela de impressão com a lista formatada dos sorteados. | **ATIVO** |
| **Voltar Nomes p/ Sorteio** | Move **todos** os nomes da lista de Sorteados de volta para a lista de Candidatos. | **ATIVO** |
| **Limpar Sorteados** | Esvazia a lista de Sorteados. | **ATIVO** |
| **Adicionar/Excluir** | Adicionar um novo nome ou excluir um candidato existente. | **BLOQUEADO** (Apenas durante a pausa ou rolagem, para proteger a integridade do sorteio em andamento). |

---
Para usalo basta baixar o documeto e salvar com .html e abrir com o navegador

## ⚙
