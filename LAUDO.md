
Bug: 1
Arquivo: lib/models/ocorrencia.dart
Sintoma: O responsável pela ocorrência podia ser identificado errado.
Causa: O sistema usava o nome em vez do ID da conta.
Correção: Ajustei para usar o ID correto do usuário.
Teste: Cadastrar uma ocorrência e conferir se ela fica ligada à conta certa.

Bug: 2
Arquivo: lib/models/ocorrencia.dart
Sintoma: Uma ocorrência podia aparecer com o status errado.
Causa: O valor de “resolvido” era interpretado incorretamente.
Correção: Ajustei a leitura do status.
Teste: Comparar uma ocorrência aberta com outra resolvida.

Bug: 3
Arquivo: lib/services/central_service.dart
Sintoma: As ocorrências mais antigas apareciam primeiro.
Causa: A consulta estava ordenada na direção errada.
Correção: Configurei para mostrar as mais recentes primeiro.
Teste: Cadastrar duas ocorrências e conferir qual aparece no topo.

Bug: 4
Arquivo: lib/pages/central_page.dart
Sintoma: Era possível tentar cadastrar uma ocorrência sem título ou local.
Causa: A validação dos campos estava incorreta.
Correção: Ajustei a validação para exigir os dois campos.
Teste: Tentar cadastrar deixando o título ou o local vazio.

Bug: 5
Arquivo: lib/pages/central_page.dart
Sintoma: O controle do filtro podia não acompanhar a opção escolhida.
Causa: O sistema invertia o valor em vez de usar o valor selecionado.
Correção: Ajustei a atualização do controle.
Teste: Ligar e desligar o filtro algumas vezes.

Bug: 6
Arquivo: lib/pages/central_page.dart
Sintoma: O filtro podia mostrar ocorrências já resolvidas.
Causa: A condição do filtro selecionava os itens errados.
Correção: Ajustei o filtro para mostrar só as ocorrências não resolvidas.
Teste: Ativar o filtro com uma ocorrência aberta e outra resolvida.

Bug: 7
Arquivo: lib/pages/central_page.dart
Sintoma: Os detalhes da ocorrência não abriam corretamente.
Causa: A tela não recebia a ocorrência selecionada.
Correção: Ajustei o envio da ocorrência para a tela de detalhes.
Teste: Abrir ocorrências diferentes e conferir as informações.

Bug: 8
Arquivo: lib/pages/detalhe_page.dart
Sintoma: O envio de uma pista podia falhar mesmo com o campo preenchido.
Causa: A verificação do campo estava invertida.
Correção: Ajustei a validação para impedir o envio quando o campo está vazio.
Teste: Tentar enviar uma pista vazia e depois uma com texto.

Bug: 9
Arquivo: lib/pages/detalhe_page.dart
Sintoma: A pista podia ser salva sem o texto digitado.
Causa: O envio não usava o conteúdo do campo.
Correção: Passei o texto digitado para o serviço que salva a pista.
Teste: Enviar uma pista e conferir se o texto aparece.

Bug: 10
Arquivo: lib/services/central_service.dart
Sintoma: Uma pista podia ser salva na ocorrência errada.
Causa: O sistema não usava o ID correto da ocorrência.
Correção: Ajustei o caminho usado para salvar as pistas.
Teste: Enviar pistas em duas ocorrências e conferir onde cada uma aparece.

Bug: 11
Arquivo: lib/services/central_service.dart
Sintoma: O sistema podia não identificar corretamente quem criou a ocorrência.
Causa: O autor era identificado pelo e-mail em vez do ID da conta.
Correção: Ajustei para usar o UID do usuário. As regras do Firestore também devem impedir alterações sem autorização.
Teste: Usar duas contas e conferir se apenas a conta autorizada consegue alterar o status.

Bug: 12
Arquivo: lib/services/central_service.dart
Sintoma: O status podia não mudar como esperado.
Causa: O sistema salvava o valor antigo.
Correção: Ajustei a atualização para alternar entre resolvido e não resolvido.
Teste: Marcar uma ocorrência como resolvida e depois reabri-la.