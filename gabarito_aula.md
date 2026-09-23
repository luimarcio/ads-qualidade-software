# Guia do Professor: Laboratório Prático ISO/IEC 25010

Este documento contém o gabarito esperado para a atividade de refatoração e os pontos-chave de discussão.

## Solução Esperada dos Alunos

```python
def processar_transacoes(dados: list) -> list:
    """Remove transações duplicadas mantendo a ordem original."""
    
    # [ISO 25010 - Confiabilidade / Tolerância a falhas]
    if not isinstance(dados, list):
        raise TypeError("O parâmetro 'dados' deve ser uma lista.")

    # [ISO 25010 - Eficiência de Desempenho / Comportamento no tempo]
    resultado = []
    vistos = set() 
    
    for item in dados:
        if item not in vistos:
            resultado.append(item)
            vistos.add(item)
            
    return resultado
Pontos de Discussão (Conexão com a Norma)
Manutenibilidade (Analisabilidade): A troca de nomes obscuros por nomes descritivos. A adição de Type Hints transforma um código ilegível em algo diagnosticável.

Confiabilidade (Tolerância a falhas): O uso da verificação de tipo (isinstance) impede que a função falhe catastroficamente.

Eficiência de Desempenho (Comportamento no tempo): A estrutura original checava duplicatas de forma ineficiente. A utilização de set() reduz o tempo de checagem drasticamente.
