1)91

<br>
2)def fibonacci(n):
    sequence = [0, 1]
    while sequence[-1] < n:
        sequence.append(sequence[-1] + sequence[-2])
    return sequence

def is_in_fibonacci(n):
    fib_sequence = fibonacci(n)
    if n in fib_sequence:
        return f"O número {n} pertence à sequência de Fibonacci."
    else:
        return f"O número {n} não pertence à sequência de Fibonacci."

# Example usage:
num = int(input("Informe um número: "))
print(is_in_fibonacci(num))
<br>

3)import json

# Carregar os dados do faturamento mensal de um arquivo JSON
def carregar_dados(arquivo_json):
    with open(arquivo_json, 'r') as arquivo:
        return json.load(arquivo)

# Calcular o menor valor de faturamento ocorrido em um dia do mês
def menor_faturamento(dados):
    return min(dados, key=lambda x: x['valor'])

# Calcular o maior valor de faturamento ocorrido em um dia do mês
def maior_faturamento(dados):
    return max(dados, key=lambda x: x['valor'])

# Calcular a média mensal de faturamento
def media_mensal(dados):
    valores = [x['valor'] for x in dados if x['valor'] > 0]
    return sum(valores) / len(valores)

# Calcular o número de dias no mês em que o valor de faturamento diário foi superior à média mensal
def dias_superiores_media(dados, media):
    return len([x for x in dados if x['valor'] > media])

# Main
def main():
    arquivo_json = 'faturamento.json'
    dados = carregar_dados(arquivo_json)
    
    menor_valor = menor_faturamento(dados)
    maior_valor = maior_faturamento(dados)
    media = media_mensal(dados)
    dias_superiores = dias_superiores_media(dados, media)
    
    print(f"Menor valor de faturamento: {menor_valor['valor']}")
    print(f"Maior valor de faturamento: {maior_valor['valor']}")
    print(f"Média mensal de faturamento: {media}")
    print(f"Dias com faturamento superior à média: {dias_superiores}")

if name == 'main':
    main()
    
    para criar arquivo json
    3.1)[
    {"dia": 1, "valor": 1000.0},
    {"dia": 2, "valor": 2000.0},
    {"dia": 3, "valor": 0.0},
    {"dia": 4, "valor": 3000.0},
    {"dia": 5, "valor": 4000.0},
    {"dia": 6, "valor": 0.0},
    {"dia": 7, "valor": 5000.0},
    {"dia": 8, "valor": 6000.0},
    {"dia": 9, "valor": 0.0},
    {"dia": 10, "valor": 7000.0},
    {"dia": 11, "valor": 8000.0},
    {"dia": 12, "valor": 0.0},
    {"dia": 13, "valor": 9000.0},
    {"dia": 14, "valor": 10000.0},
    {"dia": 15, "valor": 0.0},
    {"dia": 16, "valor": 11000.0},
    {"dia": 17, "valor": 12000.0},
    {"dia": 18, "valor": 0.0},
    {"dia": 19, "valor": 13000.0},
    {"dia": 20, "valor": 14000.0},
    {"dia": 21, "valor": 0.0},
    {"dia": 22, "valor": 15000.0},
    {"dia": 23, "valor": 16000.0},
    {"dia": 24, "valor": 0.0},
    {"dia": 25, "valor": 17000.0},
    {"dia": 26, "valor": 18000.0},
    {"dia": 27, "valor": 0.0},
    {"dia": 28, "valor": 19000.0},
    {"dia": 29, "valor": 20000.0},
    {"dia": 30, "valor": 0.0}
]

4)# Defina os valores de faturamento mensal por estado
faturamento_mensal = {
    "SP": 67836.43,
    "RJ": 36678.66,
    "MG": 29229.88,
    "ES": 27165.48,
    "Outros": 19849.53
}

# Calcule o valor total mensal
valor_total_mensal = sum(faturamento_mensal.values())

# Imprima o valor total mensal
print(f"Valor total mensal: R${valor_total_mensal:.2f}")

# Calcule e imprima o percentual de representação de cada estado
for estado, valor in faturamento_mensal.items():
    percentual = (valor / valor_total_mensal) * 100
    print(f"{estado}: R${valor:.2f} ({percentual:.2f}%)")

    5)def inverter_string(s):
    """
    Inverte os caracteres de uma string.

    Args:
        s (str): A string a ser invertida.

    Returns:
        str: A string invertida.
    """
    invertida = ""
    for i in range(len(s) - 1, -1, -1):
        invertida += s[i]
    return invertida

# Exemplo de uso:
entrada = input("Digite uma string: ")
invertida = inverter_string(entrada)
print("String invertida:", invertida)
