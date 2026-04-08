{
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/Maxcospx/Engenharia_de_Prompt_ia/blob/main/aula07.md\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "**Atividade de Programação assistida por AI**\n",
        "Nome: Marcos Vinicius Paiva"
      ],
      "metadata": {
        "id": "gIn1NcxOfynd"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "Prompt: atue com um dev senior e desenvolva um codigo de uma calculadora simples."
      ],
      "metadata": {
        "id": "T1DkdiPKpIHI"
      }
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "2895ad5c"
      },
      "source": [
        "### Calculadora Simples\n",
        "\n",
        "Este código Python implementa uma calculadora básica que permite realizar operações de soma, subtração, multiplicação e divisão entre dois números."
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 460
        },
        "id": "aefcc455",
        "outputId": "7aa5bdb3-053d-401b-d588-882ed54de0aa"
      },
      "source": [
        "def adicao(x, y):\n",
        "    return x + y\n",
        "\n",
        "def subtracao(x, y):\n",
        "    return x - y\n",
        "\n",
        "def multiplicacao(x, y):\n",
        "    return x * y\n",
        "\n",
        "def divisao(x, y):\n",
        "    if y == 0:\n",
        "        return \"Erro: Divisão por zero!\"\n",
        "    return x / y\n",
        "\n",
        "print(\"Selecione a operação:\")\n",
        "print(\"1. Adição\")\n",
        "print(\"2. Subtração\")\n",
        "print(\"3. Multiplicação\")\n",
        "print(\"4. Divisão\")\n",
        "\n",
        "while True:\n",
        "    escolha = input(\"Digite sua escolha (1/2/3/4): \")\n",
        "\n",
        "    if escolha in ('1', '2', '3', '4'):\n",
        "        try:\n",
        "            num1 = float(input(\"Digite o primeiro número: \"))\n",
        "            num2 = float(input(\"Digite o segundo número: \"))\n",
        "        except ValueError:\n",
        "            print(\"Entrada inválida. Por favor, digite um número.\")\n",
        "            continue\n",
        "\n",
        "        if escolha == '1':\n",
        "            print(f\"{num1} + {num2} = {adicao(num1, num2)}\")\n",
        "\n",
        "        elif escolha == '2':\n",
        "            print(f\"{num1} - {num2} = {subtracao(num1, num2)}\")\n",
        "\n",
        "        elif escolha == '3':\n",
        "            print(f\"{num1} * {num2} = {multiplicacao(num1, num2)}\")\n",
        "\n",
        "        elif escolha == '4':\n",
        "            resultado = divisao(num1, num2)\n",
        "            print(f\"{num1} / {num2} = {resultado}\")\n",
        "\n",
        "        proxima_calculadora = input(\"Deseja fazer outro cálculo? (sim/não): \")\n",
        "        if proxima_calculadora.lower() != 'sim':\n",
        "            break\n",
        "    else:\n",
        "        print(\"Entrada inválida. Por favor, digite uma das opções (1/2/3/4).\")\n"
      ],
      "execution_count": 1,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Selecione a operação:\n",
            "1. Adição\n",
            "2. Subtração\n",
            "3. Multiplicação\n",
            "4. Divisão\n"
          ]
        },
        {
          "output_type": "error",
          "ename": "KeyboardInterrupt",
          "evalue": "Interrupted by user",
          "traceback": [
            "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
            "\u001b[0;31mKeyboardInterrupt\u001b[0m                         Traceback (most recent call last)",
            "\u001b[0;32m/tmp/ipykernel_1406/275569983.py\u001b[0m in \u001b[0;36m<cell line: 0>\u001b[0;34m()\u001b[0m\n\u001b[1;32m     20\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m     21\u001b[0m \u001b[0;32mwhile\u001b[0m \u001b[0;32mTrue\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m---> 22\u001b[0;31m     \u001b[0mescolha\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0minput\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m\"Digite sua escolha (1/2/3/4): \"\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m     23\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m     24\u001b[0m     \u001b[0;32mif\u001b[0m \u001b[0mescolha\u001b[0m \u001b[0;32min\u001b[0m \u001b[0;34m(\u001b[0m\u001b[0;34m'1'\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0;34m'2'\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0;34m'3'\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0;34m'4'\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
            "\u001b[0;32m/usr/local/lib/python3.12/dist-packages/ipykernel/kernelbase.py\u001b[0m in \u001b[0;36mraw_input\u001b[0;34m(self, prompt)\u001b[0m\n\u001b[1;32m   1175\u001b[0m                 \u001b[0;34m\"raw_input was called, but this frontend does not support input requests.\"\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m   1176\u001b[0m             )\n\u001b[0;32m-> 1177\u001b[0;31m         return self._input_request(\n\u001b[0m\u001b[1;32m   1178\u001b[0m             \u001b[0mstr\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mprompt\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m,\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m   1179\u001b[0m             \u001b[0mself\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0m_parent_ident\u001b[0m\u001b[0;34m[\u001b[0m\u001b[0;34m\"shell\"\u001b[0m\u001b[0;34m]\u001b[0m\u001b[0;34m,\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
            "\u001b[0;32m/usr/local/lib/python3.12/dist-packages/ipykernel/kernelbase.py\u001b[0m in \u001b[0;36m_input_request\u001b[0;34m(self, prompt, ident, parent, password)\u001b[0m\n\u001b[1;32m   1217\u001b[0m             \u001b[0;32mexcept\u001b[0m \u001b[0mKeyboardInterrupt\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m   1218\u001b[0m                 \u001b[0;31m# re-raise KeyboardInterrupt, to truncate traceback\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m-> 1219\u001b[0;31m                 \u001b[0;32mraise\u001b[0m \u001b[0mKeyboardInterrupt\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m\"Interrupted by user\"\u001b[0m\u001b[0;34m)\u001b[0m \u001b[0;32mfrom\u001b[0m \u001b[0;32mNone\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m   1220\u001b[0m             \u001b[0;32mexcept\u001b[0m \u001b[0mException\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m   1221\u001b[0m                 \u001b[0mself\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mlog\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mwarning\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m\"Invalid Message:\"\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mexc_info\u001b[0m\u001b[0;34m=\u001b[0m\u001b[0;32mTrue\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
            "\u001b[0;31mKeyboardInterrupt\u001b[0m: Interrupted by user"
          ]
        }
      ]
    }
  ],
  "metadata": {
    "colab": {
      "provenance": [],
      "include_colab_link": true
    },
    "kernelspec": {
      "display_name": "Python 3",
      "name": "python3"
    }
  },
  "nbformat": 4,
  "nbformat_minor": 0
}