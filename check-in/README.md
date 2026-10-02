# Check In (Turismo)

Este projeto implementa um formulário simples de registro de check-in para o turista ou agente de Turismo dar Check-in no local em foi visitado (?)

## Ideias propostas

- URL base: https://govtursabara.lovable.app/check-in

- Para cada local que o formulário quiser atender, terá um path diferente amigável, a exceção do CAT, que será o endereço da raiz /check-in. Por exemplo:
  - Solar do Padre Corrêa: .../check-in/solar-padre-correa
  - Biblioteca de Sabará: .../check-in/biblioteca
  - Igreja do Ó: .../check-in/igreja-do-o
  - Borrachalioteca: .../check-in/borrachalioteca
  - CAT: .../check-in

- A imagem lateral esquerda mudar de acordo com o local que o QR-Code corresponder.

- Salvar os dados que o usuário preencher localmente e recuperá-los quando a página for novamente carregada para um novo path - para evitar que o usuário envie por engano várias e várias vezes o mesmo formulário. Dar feedback ao usuário que houve recuperação dos dados armazenados.

- Formular um Termos de Uso dos Dados e Política de Privacidade, sobre a manipulação dos dados que forem informados pelo usuário no formulário e possível contato posteriormente.

- Deixar checkbox da Concordância com os termos de serviço já marcado (verificar LGPD sobre isso), para facilitar o preenchimento do formulário pelo usuário.

- O input de cidade de origem deve ter uma opção com autocomplete que carregue todos os municípios do país, seguido da UF dos estados para facilitar o preenchimento do usuário. Pensar uma forma de recomendar cidades "mais relevantes", carregar de forma fluída e sem pesar a página e o usuário selecionar.

- Usar máscara para o número de telefone - sempre exigir um número com o padrão: (DD) XXXXX-XXXX. Utilizar inputmode=numeric para que, no celular, já apareça o teclado numérico.

- Implementar validações enquanto o usuário preenche o formulário, já retornando feedback sobre o que ele faz - evitando mandar feedback apenas quando concluir a operação.

- Direcionar o usuário, após o preenchimento, envio e registro do formulário para uma página sobre a cidade, o que fazer, talvez até mesmo o Instagram: descubra.sabara
