Calculadora Simples: 

o Prompt foi o seguinte: "elabore um codigo de uma calculadora simples em python."

A resposta da AI foi o seguinte código:

def calculadora():
    print("=== Calculadora Simples ===")
    print("Escolha uma operação:")
    print("1 - Soma")
    print("2 - Subtração")
    print("3 - Multiplicação")
    print("4 - Divisão")

    opcao = input("Digite o número da operação (1/2/3/4): ")

    num1 = float(input("Digite o primeiro número: "))
    num2 = float(input("Digite o segundo número: "))

    if opcao == "1":
        resultado = num1 + num2
        print("Resultado:", resultado)

    elif opcao == "2":
        resultado = num1 - num2
        print("Resultado:", resultado)

    elif opcao == "3":
        resultado = num1 * num2
        print("Resultado:", resultado)

    elif opcao == "4":
        if num2 != 0:
            resultado = num1 / num2
            print("Resultado:", resultado)
        else:
            print("Erro: divisão por zero não é permitida.")

    else:
        print("Opção inválida.")


calculadora()

esse foi o prompt entregue um código simples e limpo.
