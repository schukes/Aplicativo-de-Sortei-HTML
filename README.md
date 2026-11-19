🏆 Sorteador Corporativo - Documentação

Olá Dr. Hasegawa. Este documento é o guia da estrutura e das funcionalidades do sistema de sorteio corporativo, feito em um único arquivo HTML para máxima portabilidade ("baixar e abrir").

🚀 Uso Simplificado

Salve o arquivo como sorteio.html e abra-o diretamente em qualquer navegador moderno. Todo o código (HTML, CSS e JavaScript) está contido nele.

Dois recursos dependem de internet, mas o sorteio funciona sem eles: a fonte Montserrat (Google Fonts) e o confete (CDN canvas-confetti). Sem conexão, a página usa a fonte padrão do sistema e o confete simplesmente não aparece.

Dica para o dia do evento: abra sempre o mesmo arquivo, no mesmo navegador e na mesma pasta. Os dados salvos ficam presos a essa combinação.

✨ Funcionalidades Principais
Funcionalidade	Detalhe
Título do sorteio	Campo editável no topo. Aparece na tela cheia, na aba do navegador, na impressão e no nome do CSV.
Sorteio em Tela Cheia	Botão "INICIAR SORTEIO EM TELA CHEIA", com interface dedicada para telões.
Animação Aleatória (Fade)	@keyframes roll faz o texto oscilar (opacity) durante a rolagem de nomes. Respeita a preferência de movimento reduzido do sistema.
Sorteio justo	Usa crypto.getRandomValues (gerador criptográfico do navegador) em vez de Math.random().
Retomada após queda de energia	Todo o estado é salvo a cada mudança. O vencedor é definido e salvo antes da animação, então nada se perde nem se repete. Ao reabrir, a página mostra "Sorteio retomado".
Vencedor ausente	Botão na tela cheia que descarta o vencedor atual e sorteia outro. O nome fica no log, riscado, com status "ausente".
Importação de Nomes	Carrega .txt ou .csv (um nome por linha). Aceita UTF-8 e Windows-1252 (Excel brasileiro), remove BOM e usa só a primeira coluna (;, , ou tab).
Duplicados	A checagem ignora maiúsculas, acentos e espaços extras. Os nomes ficam como digitados.
Gerenciamento de Listas	Adicionar, remover, Limpar Candidatos, Devolver Sorteados e Excluir Sorteados. As duas últimas ações também limpam o log.
Modo Automático	Sorteia em intervalo definido (1 a 60 s) até acabar os candidatos. Configuração salva.
Backup e Restauração	💾 Backup baixa um JSON com todo o estado. 📥 Restaurar carrega esse arquivo.
Exportação e Impressão	CSV (abre com acentos corretos no Excel) com sorteio, ordem, nome, data/hora, status e candidatos restantes. Impressão da lista de vencedores com o título.
Tema claro/escuro	Alternável e salvo.
Controle por Teclado	ESPAÇO sorteia o próximo. ESC fecha a tela cheia.
Responsivo	Em telas pequenas as listas ficam empilhadas.
💾 Persistência e Backup
Onde fica: localStorage do navegador, na chave sorteio_estado_v2. Os dados da versão antiga são migrados automaticamente.
O que é salvo: título, candidatos, sorteados, log, tema, modo automático e intervalo.
Aviso de falha: se o navegador não conseguir gravar, aparece uma faixa laranja no topo.
Limitação: limpar os dados do navegador, usar janela anônima ou mudar o arquivo de pasta apaga ou isola o estado.
Recomendação: faça um 💾 Backup antes do evento e outro ao final.
📐 Estrutura Interna do Código (sorteio.html)
1. HTML (<body>)
Overlay (#overlay): camada de tela cheia, com título, contador, nome sorteado e botões Próximo, Vencedor ausente e Parar Auto.
Contêiner Principal (.container): título, progresso, listas, controles, log e backup.
.print-container: área montada sob demanda para impressão.
Bloco <script>: antes do </body>, para garantir que o DOM já exista.
2. Estilos CSS (<style>)
Variáveis e temas: cores em :root e body.tema-escuro.
Animações: @keyframes roll (rolagem) e @keyframes zoom (entrada do vencedor).
Responsivo e impressão: @media (max-width: 700px) e @media print.
3. Lógica JavaScript (<script>)

O estado fica em um único objeto E (titulo, nomes, sorteados, log, tema, auto, intervalo).

Bloco	Responsabilidade	Funções Chave
Persistência	Carregar e salvar o estado.	carregar(), salvar(), avisar()
Auxiliares	Aleatoriedade, normalização e totais.	randInt(), chave(), existe(), sleep()
Sons	Áudio criado só após o primeiro clique.	audio(), beep(), melodia()
Renderização	Desenha as listas via DOM seguro (sem innerHTML).	render(), mudou()
Tela cheia	Abrir e fechar o overlay, confete.	abrirTelaCheia(), fecharTelaCheia(), confete()
Sorteio	Rodada, animação e modo automático.	rodada(), iniciarSorteio(), proximo(), marcarAusente(), agendarAuto()
Nomes	Adicionar, importar e limpar.	adicionarNome(), importarNomes(), limparCandidatos(), limparSorteados(), resetarSorteados()
Saída de dados	Impressão, CSV e backup.	imprimir(), exportarCSV(), backup(), restaurar()
Eventos	Liga botões, teclado e fullscreenchange.	addEventListener
Como o sorteio funciona (rodada())
Escolhe o vencedor com randInt().
Move o nome de candidatos para sorteados, grava no log e salva.
Roda a animação mostrando nomes aleatórios da lista, desacelerando no final.
Exibe o vencedor com som, zoom e confete.
Se o overlay for fechado durante a animação, ela é cancelada (rodadaId), mas o vencedor continua registrado.

Documentação atualizada em 19 de Novembro de 2026.
