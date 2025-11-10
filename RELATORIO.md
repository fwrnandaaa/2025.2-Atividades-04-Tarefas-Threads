# Relatório de Observações - Atividade de Threads

## Informações do Aluno
- **Nome:** Fernanda Dantas do Nascimento
- **Matrícula:** 20242014040031
- **Data:** 10/11/2025

## Ambiente de Execução

- [X] Executado localmente
- [] Executado em Docker/Fedora

**Sistema Operacional:** Windows 11 

**Processador:** AMD Ryzen 5  

**Número de Cores:** 4

---

## Execução 1

### Resultados Observados

**Thread CPU (Thread 1):**
- Tempo de execução: 0.43 segundos
- Soma dos primos: 37550402023
- Ordem de conclusão:  3ª

**Thread I/O (Thread 2):**
- Tempo de execução: 0.14 segundos
- Linhas processadas: 10000
- Ordem de conclusão: 2ª

**Thread Mista (Thread 3):**
- Tempo de execução: 0.05 segundos
- Total de cálculos: 3482527859448382464
- Ordem de conclusão: 1ª

**Tempo Total do Programa:** <1 segundo

### Observações sobre a Saída

Descreva como as mensagens das threads apareceram no console:

As mensagens das três threads apareceram intercaladas no console, mostrando que estavam executando simultaneamente. As threads começaram juntas, cada uma realizando suas operações específicas (CPU, I/O e mista), e suas mensagens de progresso e conclusão foram exibidas em ordem variada.

---

## Execução 2 (Com Docker)

### Resultados Observados

**Thread CPU (Thread 1):**
- Tempo de execução: 0.42 segundos
- Ordem de conclusão: 3ª

**Thread I/O (Thread 2):**
- Tempo de execução: 0.01 segundo
- Ordem de conclusão: 1ª

**Thread Mista (Thread 3):**
- Tempo de execução: 0.03 segundos
- Ordem de conclusão: 2ª

**Tempo Total do Programa:** <1 segundo

### Diferenças entre Execuções

Houve pequenas diferenças nos tempos de execução de cada thread, principalmente nas threads de I/O e mista, que terminaram mais rapidamente na execução com Docker.

---

## Análise e Conclusões

### 1. Qual thread terminou primeiro? Por quê?

A thread I/O e a mista terminaram primeiro, pois elas executam tarefas mais rápidas e menos intensivas que a de CPU.

### 2. Por que os tempos de execução variam entre diferentes execuções?

Isso ocorre por causa do escalonamento e prioridades do sistema operacional, além da carga momentânea do computador.

### 3. Como o sistema operacional gerencia a execução das threads?

O sistema operacional usa escalonamento e time-sharing para alternar rapidamente entre as threads, permitindo que todas pareçam rodar ao mesmo tempo. Ele decide qual thread executa em cada núcleo do processador, trocando entre elas em intervalos curtos para garantir que compartilhem os recursos de forma justa e eficiente.

### 4. Qual seria o impacto de aumentar o número de threads?

Aumentar o número de threads pode melhorar o paralelismo, pois mais tarefas são executadas ao mesmo tempo, aproveitando os núcleos do processador. Porém, se houver threads demais, o sistema operacional precisa escalonar e alternar entre elas, gerando overhead.

### 5. O que aconteceria se executássemos as mesmas operações sequencialmente?

Não haveria concorrência nem paralelismo, pois cada tarefa só começaria quando a anterior terminasse. O tempo total seria maior e as saídas apareceriam em ordem fixa, sem intercalamento das mensagens das threads.

