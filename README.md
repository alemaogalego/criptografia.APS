# Tabela de Cifra Aleatória

Este projeto implementa um sistema de criptografia baseado em uma tabela de substituição aleatória de caracteres ASCII para Tralho semestral de Análise e Projeto de Sistemas. O código permite criptografar e descriptografar mensagens utilizando coordenadas da tabela gerada aleatoriamente.

## Como funciona

1. **Geração da Tabela**: Uma tabela 16x16 é criada contendo caracteres da tabela ASCII em posições aleatórias.
2. **Criptografia**: Cada caractere da mensagem é convertido em coordenadas dentro da tabela.
3. **Descriptografia**: A mensagem codificada é reconvertida em texto original utilizando as coordenadas da tabela.

## Estrutura do Código

- `rand(min, max)`: Gera um valor aleatório para inserir em posições aleatórias.
- `gerar_tabela()`: Cria a tabela onde os caracteres se encontrarão em posições aleatórias.
- `gerarString(x, formato='%02s')`: Gera os indices para exibição da tabela.
- `mostrartabela(tabela)`: Exibe a tabela gerada.
- `encrypt(tabela, palavras)`: Codifica uma mensagem utilizando a tabela.
- `decrypt(tabela, numeros)`: Decodifica uma mensagem cifrada.

## Como Usar

1. Execute o código Python.
2. A tabela será gerada e exibida.
3. A mensagem "Maca e banana!" será criptografada e depois descriptografada.
4. Os resultados serão exibidos no console.

## Exemplo de Saída
```
-------------------
 01 02 03 04 ... 16
1  A  B  C  ... Z
2  a  b  c  ... z
...
16 @  #  $  ... ~
-------------------
Aqui está o seu arquivo encriptado: 0412031108...
Aqui está o seu arquivo decriptado: Maca e banana!
```

## Requisitos
- Python 3.x
- Import biblioteca random

## Observações
- Cada execução gera uma tabela diferente, tornando a criptografia única.
- A tabela precisa ser mantida para descriptografar corretamente.

## Autor
Este código foi criado para fins educacionais e demonstração de conceitos básicos de criptografia baseada em tabelas de substituição para Tralho semestral de Análise e Projeto de Sistemas Desenvolvido por Lucas César, Guilherme Henrique e Pedro Palmeira.

