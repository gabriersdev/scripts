# Registro de Carimbo

Este projeto implementa um formulário simples de registro de carimbo com validação em tempo real utilizando JavaScript (Vanilla).

## Regras de Negócio e Validações

O formulário valida dois campos principais antes de permitir o envio:

### 1. Número do Carimbo (`#stamp-number`)
- **Obrigatório:** Deve conter no mínimo 1 caractere.
- **Formato:** Aceita **apenas números**.
- **Máscara Numérica e Visual:** Bloqueia instantaneamente a digitação de qualquer caractere não numérico e formata automaticamente o valor inserindo pontos como separador de milhares (ex: `123.456`).
- Não há limite máximo de tamanho de caracteres definido.

### 2. Data de Marcação (`#date`)
- **Obrigatória e Padrão:** O campo já é inicializado com a data de hoje no fuso horário local de Brasília (GMT-3).
- **Formato (Máscara):** Uma máscara formata automaticamente a digitação no padrão `DD/MM/AAAA`.
- **Tamanho Fixo:** O valor inserido deve conter obrigatoriamente 10 caracteres (`DD/MM/AAAA`).
- **Data Válida:** O script verifica se a data informada realmente existe no calendário (ex: bloqueia "30/02/2023").
- **Datas Futuras Bloqueadas:** A data não pode ser maior que o momento atual. É permitido registrar apenas dados do passado ou de hoje (GMT-3).
- **Datas Muito Antigas Bloqueadas:** A data não pode ser anterior a 30 dias contados a partir da data atual (limite restrito a um histórico máximo de 1 mês).
- **Datepicker Nativo:** O ícone de calendário aciona um `<input type="date">` invisível, que aproveita o datepicker nativo do navegador/dispositivo móvel, formatando automaticamente a seleção de volta para o padrão `DD/MM/AAAA` do formulário.

## Comportamento do Formulário

- **Validação em Tempo Real:** O usuário recebe feedback (textos em vermelho abaixo dos campos) instantaneamente caso a validação falhe.
- **Botão de Submissão:** O botão "Registrar" fica desabilitado (`disabled`) por padrão e se mantém bloqueado sempre que os campos não passarem integralmente nas regras de negócio.
- **Mensagens Centralizadas:** As mensagens de erro estão centralizadas no topo do script em um objeto JavaScript (`validationMessages`), o que facilita a manutenção, alteração e até a internacionalização (caso seja acoplado em outro framework futuramente).
- **Submissão com Sucesso:** Ao submeter dados válidos, o usuário receberá um modal de confirmação visual. O formulário será limpo automaticamente na sequência, retornando à data padrão do dia atual.
- **Limpar Formulário:** O botão de "Limpar" reinicia o formulário, removendo os avisos e restaurando a data para o padrão inicial.
