# Code Review Checklist

## Geral

-   O código funciona? Ele desempenha o papel esperado, a lógica está correta, etc?
-   O código é facilmente entendido?
-   O código respeita as convenções de codificação definidas para o projeto?
-   Existe algum código redundante ou duplicado?
-   O código é o mais modular possível?
-   Algum código de log ou debug pode ser removido?
-   Se a tarefa exigir a inclusão de uma nova biblioteca/componente no composer.json ou no bower.json toda a equipe deve ser informada para evitar problemas de compatibilidade. O mesmo caso seja necessária uma atualização de versão de uma biblioteca/componente já existente
-   Código comentado foi removido?

## Segurança

-   Todos os inputs foram validados (tipo correto, tamanho, formato, valores válidos)?
-   Os parâmetros inválidos foram tratados?

## Documentação

-   É necessário executar o algum comando extra (composer, grunt,bower, etc) para que o código funcione ? Deve ser avisado na descrição do PR se for o caso.
-   O código possui documentação? Nos principais métodos e lógicas complexas?
-   Todas as variáveis foram definidas com nomes significativos, consistentes e claros?

##  Performance

-   As consultas do Doctrine (ou do banco de dados, ou Zend\\Sql, etc) foram otimizadas pensando-se em melhoria de performance?
-   Informações que podem ser armazenadas em cache estão sendo cacheadas?
-   Processamentos redundantes ou lentos foram otimizados?
-   Foi evitado o uso de construções IF-ELSE para diminuir a complexidade da execução?
-   Na visão foram utilizados os componentes e layouts para optimizar o desenvolvimento?

## Testes

-   Se a tarefa envolver apenas um módulo, executar os testes daquele módulo. Se envolver mais de um, rodar todos os testes do sistema.
-   Os testes unitários devem ser rodados com todos os erros do PHP habilitados de modo à garantir que nenhum notice,warning,deprecated entre na base.
-   Se for uma tarefa que crie ou altere uma API devem ser criados/alterados os testes de Api referentes a tarefa (caso o projeto possua este tipo de teste)
-   Os testes unitários devem cobrir tanto dos casos de sucesso quanto dos casos de erro
-   Testar a interface seguindo os requisitos mínimos de navegadores:
    -   Microsoft Internet Explorer 8.0
    -   Chrome 35.0
    -   Safari 8
    -   Firefox version 35
-   Caso não consiga testar em todos os navegadores deve descrever na descrição do PR em quais navegadores realizou os testes
