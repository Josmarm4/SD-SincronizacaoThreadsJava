# Relatório de Análise de Sincronização

Neste relatório, vou compartilhar as execuções dos programas das atividades práticas 01, 02 e 03, explicando como foi o comportamento das threads e o que entendi com cada uma delas.

## Atividade Prática 01: Execução de `MeuDadoThreadsJava`

Na primeira atividade, executei o programa `MeuDadoThreadsJava`, que mosrava como o gerenciamento de threads pode ser feito com base em prioridades. O programa cria duas threads, uma com **alta prioridade** e outra com **baixa prioridade**, para observar como cada uma delas se comporta durante a execução.

### O que aconteceu:
Os logs gerados mostraram claramente que a thread de alta prioridade executava mais frequentemente do que a de baixa prioridade, como era de se esperar. Isso ocorreu por causa do método `setPriority`, que ajusta as prioridades de execução das threads.

### O que eu achei:
Foi bem interessante ver como a diferença de prioridades afeta o tempo de execução das threads. A thread de baixa prioridade não ficou completamente bloqueada, porque o método `yield()` foi usado para dar uma chance para ela ser executada, o que ajudou a equilibrar a carga de trabalho.

## Atividade Prática 02: Execução de `MeuDadoMonitorJava`

A segunda atividade envolveu a execução do programa `MeuDadoMonitorJava`, que usava **monitores** para sincronizar o acesso das threads a uma seção crítica do código. O programa utilizou o comando `synchronized` para garantir que apenas uma thread acessasse a parte crítica de cada vez.

### O que aconteceu:
Os logs mostraram que a sincronização foi bem-sucedida, com cada thread acessando a seção crítica de maneira exclusiva. Isso garantiu que não houvesse condições de corrida, o que poderia gerar resultados inesperados.

### O que eu achei:
A sincronização com monitores foi eficaz, mas percebi que as threads precisaram aguardar sua vez para acessar a seção crítica. Isso pode ter impactado o desempenho, mas, no geral, foi uma solução bem prática para garantir que as threads não interferissem umas nas outras.

## Atividade Prática 03: Execução de `MeuDadoEventJava`

A última atividade foi a execução de `MeuDadoEventJava`, que utilizou **eventos** para coordenar a execução das threads. O programa fez uso dos métodos **`Object.wait()`** e **`Object.notify()`** para controlar quando as threads deveriam continuar a execução.

### O que aconteceu:
A execução foi tranquila, e os logs mostraram que as threads esperavam pelos eventos corretamente. Quando o evento era acionado, as threads podiam continuar, o que fez a execução ser sincronizada de forma eficaz.

### O que eu achei:
A sincronização com eventos foi uma técnica mais avançada, mas também muito interessante. Ela permitiu um controle mais preciso sobre as threads, evitando conflitos e garantindo que as ações acontecessem na ordem certa. Foi uma ótima oportunidade de aprender algo novo e ver como a sincronização pode ser feita de maneiras diferentes.

## Comparação das Três Atividades

Cada uma dessas atividades abordou um aspecto diferente da sincronização de threads:

- Na **Atividade 01**, o foco foi nas **prioridades das threads**, mostrando como elas se comportam quando têm prioridades diferentes.
- Na **Atividade 02**, o uso de **monitores** garantiu que apenas uma thread acessasse a seção crítica por vez, evitando condições de corrida.
- Já na **Atividade 03**, o controle de **eventos** ajudou a coordenar as threads de forma mais precisa, com um controle mais fino sobre o fluxo da execução.

Embora todas as atividades envolvam sincronização, cada uma utiliza uma técnica distinta, que pode ser mais adequada dependendo do tipo de problema que se quer resolver.

## Considerações Finais

Fazer essas atividades foi uma excelente oportunidade para entender melhor como funcionam as diferentes técnicas de sincronização em Java. Cada abordagem tem suas vantagens e desvantagens, e a escolha de qual usar depende dos requisitos do projeto. 

Aprender sobre threads e como sincronizá-las é fundamental para desenvolver sistemas que funcionam bem em ambientes concorrentes, e essas atividades me ajudaram bastante a entender esses conceitos na prática.
