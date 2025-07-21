
# 🔍 Verificador de Duplicatas

Este projeto, desenvolvido em linguagem C, tem como objetivo verificar duplicatas em uma lista de strings inseridas manualmente ou importadas de um arquivo `.csv`. A aplicação utiliza três abordagens distintas para comparação e mostra os tempos de execução de cada uma.

---

## 📌 Objetivo

O programa permite ao usuário identificar duplicatas em uma lista de palavras ou frases usando três métodos diferentes:

1. **Tabela Hash** — usa uma estrutura de hash para detecção eficiente.
2. **Busca Linear** — compara cada elemento com todos os outros.
3. **Ordenação + Comparação** — ordena os dados e verifica duplicatas adjacentes.

O sistema compara a performance de cada abordagem e apresenta os tempos de execução para facilitar a análise de desempenho.

---

## ⚙️ Como compilar e executar

### 🔧 Compilação (versão única)

```bash
gcc VerificadorDuplicata.c -o verificador
./verificador    //  ./verificador "nome do arquivo".csv 
```

### 📂 Estrutura alternativa (modular)

Caso utilize a versão modularizada:

```bash
cd VersãoModulada
gcc src/*.c -Iinclude -o verificador
./verificador   //  ./verificador "nome do arquivo".csv 
```

---

## 💻 Como usar o programa

Ao executar, o programa exibe um menu com as opções:

```
============================
 VERIFICADOR DE DUPLICATAS
============================
1. Inserir manualmente
2. Importar CSV
0. Sair
============================
```

### Inserção Manual
- O usuário informa a quantidade de strings.
- Insere uma a uma no terminal.
- Pode digitar `sair` a qualquer momento para cancelar, retornando ao menu sem os resultados obtidos dos valores já inseridos.

### Importação via CSV
- O usuário fornece o nome de um arquivo `.csv` contendo uma string por linha.
- Em caso de erro na leitura, é oferecida a opção de tentar novamente ou sair.

---

## 🔎 Métodos de Verificação

| Método                      | Descrição                                               | Complexidade |
|-----------------------------|---------------------------------------------------------|--------------|
| **Tabela Hash**             | Armazena strings em uma tabela para detecção rápida.    | O(n)         |
| **Busca Linear**            | Compara cada string com todas as outras.                | O(n²)        |
| **Ordenação + Comparação**  | Ordena as strings e compara pares adjacentes.           | O(n log n)   |


---

## ⏱️ Tabela Comparativa dos Tempos

Resultados obtidos com base em entradas reais:

### Tabela Hash                         

|   Quantidade de entradas   |  Tempo de Execução (segundos) |
|----------------------------|-------------------------------|
|            2000            |         0.003000000           |
|            4000            |         0.006000000           |
|            6000            |         0.004000000           |
|            8000            |         0.011000000           |
|           10000            |         0.014000000           |


### Busca Linear                       

|   Quantidade de entradas   |  Tempo de Execução (segundos) |
|----------------------------|-------------------------------|
|            2000            |         0.137000000           |
|            4000            |         0.274000000           |
|            6000            |         0.396000000           |
|            8000            |         0.539000000           |
|           10000            |         0.651000000           |


### Ordenação + Comparação

|   Quantidade de entradas   |  Tempo de Execução (segundos) |
|----------------------------|-------------------------------|
|            2000            |          0.006000000          |
|            4000            |          0.013000000          |
|            6000            |          0.023000000          |
|            8000            |          0.025000000          |
|           10000            |          0.033000000          |



> Estes tempos foram obtidos usando `clock()` da biblioteca `<time.h>` em testes reais. Os valores podem variar conforme o tamanho da entrada e a máquina utilizada. Além disso, foi observado que a implementação focada no uso de hash não permitiu uma comparação totalmente justa, pois os métodos linear e ordenação + comparação não possuem todas as funcionalidades presentes na versão com hash. Ainda assim, a abordagem com hash se mostrou mais eficiente.

---

## 💬 Problemas enfrentados e soluções

### 🧱 Organização e Modularização
- **Problema:** O código inicial estava monolítico e difícil de manter.
- **Solução:** Separação em múltiplos arquivos `.c` e `.h`, organizados em `src/` e `include/`.

### 🐞 Bugs durante execução
- **Problemas:** Loops, falhas de segmentação e de leitura de arquivos.
- **Soluções:** 
  - Validação de entradas.
  - Uso de validações com ponteiros nulos.
  - Melhor controle de memória com `malloc`, `calloc` e `free`.
  - Mensagens claras de erro e opção de repetição.

### 🧪 Medição de desempenho
- **Problema:** Dificuldade em comparar eficiência dos métodos.
- **Solução:** Implementação de timers com `clock_t` para medição precisa dos tempos de execução.

---

## 📎 Requisitos

- GCC ou compilador C compatível
- Terminal com suporte a entrada interativa
- Arquivos `.csv` com strings (opcional)

---

## 👤 Autor

- **Nomes:** 
      - Sophia Hellen
      - Antonio Andson
      -Levi Filgueira
- **GitHub:** 
      - [https://github.com/Sophiahellen02](https://github.com/Sophiahellen02)
      - [https://github.com/Sophiahellen02](https://github.com/Sophiahellen02)
      - [https://github.com/Sophiahellen02](https://github.com/Sophiahellen02)
---
