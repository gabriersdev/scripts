# Check-in Turístico

Este projeto implementa um formulário digital para registro de check-in de turistas e agentes de viagens, com o objetivo de contabilizar e documentar as visitas aos pontos turísticos da cidade de forma prática e rápida.

## Funcionalidades e Requisitos Planejados

- **URL base:** `https://govtursabara.lovable.app/check-in`

- **Rotas Dinâmicas e Amigáveis:** Cada local de visitação terá um caminho (path) amigável específico na URL. A exceção será o CAT (Centro de Atendimento ao Turista), que responderá pela rota raiz (`/check-in`). Exemplos de rotas:
  - Solar do Padre Corrêa: `.../check-in/solar-padre-correa`
  - Biblioteca de Sabará: `.../check-in/biblioteca`
  - Igreja do Ó: `.../check-in/igreja-do-o`
  - Borrachalioteca: `.../check-in/borrachalioteca`
  - CAT: `.../check-in`

- **Personalização Visual Dinâmica:** A imagem de destaque (lateral esquerda) será alterada automaticamente, refletindo o ponto turístico correspondente ao QR-Code lido ou à rota acessada.

- **Persistência de Dados (Local Storage):** Os dados preenchidos serão salvos localmente no navegador. Caso o turista acesse a página novamente para um novo ponto turístico, suas informações serão recuperadas automaticamente. O sistema deve exibir um aviso (feedback) amigável informando que os dados foram recuperados com sucesso. Essa medida visa evitar o preenchimento repetitivo e múltiplos envios acidentais.

- **Termos de Uso e Política de Privacidade:** Elaborar um documento de Termos de Uso e Política de Privacidade claro, explicando o tratamento e armazenamento dos dados fornecidos e as regras para um eventual contato posterior.

- **Concordância com Termos de Serviço:** Avaliar a viabilidade jurídica (sob a ótica da LGPD) de manter o checkbox de aceite dos termos de serviço pré-marcado, visando facilitar a conversão e o preenchimento por parte do usuário.

- **Autocompletar Inteligente para Cidades:** O campo de "cidade de origem" deverá contar com recurso de autocompletar consultando uma base de todos os municípios do país (Cidade - UF). A implementação deve garantir o carregamento fluido, sem perda de performance, e, idealmente, destacar as cidades mais relevantes ou de origem mais frequente.

- **Máscara e Teclado Numérico para Telefone:** Aplicar máscara de formatação obrigatória para o campo de telefone no padrão `(DD) XXXXX-XXXX`. Utilizar o atributo `inputmode="numeric"` na tag HTML para acionar automaticamente o teclado numérico em dispositivos móveis.

- **Validação de Dados em Tempo Real:** Fornecer feedback imediato (validação inline) enquanto o usuário preenche o formulário (ex: e-mail inválido, formato incorreto), evitando que as mensagens de erro apareçam somente na tentativa de submissão final.

- **Redirecionamento Pós-Check-in:** Após a conclusão do registro, direcionar o visitante para uma página com informações e roteiros da cidade, ou diretamente para o perfil oficial de turismo no Instagram (ex: `@descubra.sabara`).
