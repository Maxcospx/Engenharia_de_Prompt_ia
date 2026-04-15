Exercicios : 

1.Organizador de Pastas:

Prompt: criar um programa que organize arquivos bagunçados em pastas automaticamente, baseando-se apenas na extensão do arquivo(ex: .pdf,.jpg)


import os
import shutil

def organize_files_by_extension(source_dir, destination_dir):
    if not os.path.exists(source_dir):
        print(f"Erro: O diretório de origem '{source_dir}' não existe.")
        return

    if not os.path.exists(destination_dir):
        os.makedirs(destination_dir)
        print(f"Diretório de destino '{destination_dir}' criado.")

    print(f"Organizando arquivos de '{source_dir}' para '{destination_dir}'...")

    for filename in os.listdir(source_dir):
        source_path = os.path.join(source_dir, filename)

        # Ignora diretórios, processa apenas arquivos
        if os.path.isfile(source_path):
            # Obtém a extensão do arquivo
            _, file_extension = os.path.splitext(filename)

            # Remove o ponto e converte para maiúsculas para o nome da pasta
            if file_extension:
                folder_name = file_extension[1:].upper() + "_Files"
            else:
                folder_name = "No_Extension_Files"
            
            destination_folder = os.path.join(destination_dir, folder_name)

            # Cria a pasta de destino se não existir
            if not os.path.exists(destination_folder):
                os.makedirs(destination_folder)

            destination_path = os.path.join(destination_folder, filename)

            try:
                shutil.move(source_path, destination_path)
                print(f"Movido: '{filename}' para '{folder_name}'")
            except shutil.Error as e:
                print(f"Erro ao mover '{filename}': {e}")
            except Exception as e:
                print(f"Um erro inesperado ocorreu ao mover '{filename}': {e}")
    
    print("Organização de arquivos concluída!")

# --- Exemplo de uso ---
# IMPORTANTE: Mude estes caminhos para os seus diretórios reais.
# Por exemplo:
# source_directory = '/content/files_baguncados'
# destination_directory = '/content/files_organizados'

# Cria alguns arquivos de exemplo para teste (apenas se os diretórios não existirem)
# if not os.path.exists('/content/files_baguncados'):
#     os.makedirs('/content/files_baguncados')
#     with open('/content/files_baguncados/documento.pdf', 'w') as f: f.write('pdf content')
#     with open('/content/files_baguncados/imagem.jpg', 'w') as f: f.write('jpg content')
#     with open('/content/files_baguncados/relatorio.docx', 'w') as f: f.write('docx content')
#     with open('/content/files_baguncados/sem_extensao', 'w') as f: f.write('no extension')
#     print('Arquivos de exemplo criados em /content/files_baguncados')

# Defina seus diretórios aqui:
# source_directory = input("Digite o caminho do diretório de origem (onde estão os arquivos bagunçados): ")
# destination_directory = input("Digite o caminho do diretório de destino (onde as pastas serão criadas): ")

# Para testar rapidamente sem input, você pode descomentar as linhas abaixo
source_directory = '/content/files_baguncados'
destination_directory = '/content/files_organizados'

# Certifique-se de que o diretório de origem existe e crie alguns arquivos para teste
if not os.path.exists(source_directory):
    os.makedirs(source_directory)
    # Criando alguns arquivos de exemplo para demonstração
    with open(os.path.join(source_directory, 'documento1.pdf'), 'w') as f: f.write('dummy pdf content')
    with open(os.path.join(source_directory, 'imagem1.jpg'), 'w') as f: f.write('dummy jpg content')
    with open(os.path.join(source_directory, 'apresentacao.pptx'), 'w') as f: f.write('dummy pptx content')
    with open(os.path.join(source_directory, 'texto_importante.txt'), 'w') as f: f.write('dummy txt content')
    with open(os.path.join(source_directory, 'outro_documento.pdf'), 'w') as f: f.write('another dummy pdf content')
    with open(os.path.join(source_directory, 'arquivo_sem_extensao'), 'w') as f: f.write('content without extension')
    print(f"Diretório de origem '{source_directory}' e arquivos de exemplo criados para demonstração.")

organize_files_by_extension(source_directory, destination_directory)



2.CEP:

Prompt:criar um programa que organize arquivos bagunçados em pastas automaticamente, baseando-se apenas na extensão do arquivo(ex: .pdf, .jpg)

# Primeiro, certifique-se de ter a biblioteca 'requests' instalada.
# Se não tiver, execute a linha abaixo:
# !pip install requests

import requests

def consultar_cep(cep):
    url = f"https://viacep.com.br/ws/{cep}/json/"
    
    try:
        response = requests.get(url)
        response.raise_for_status()  # Levanta um erro para status codes HTTP ruins (4xx ou 5xx)
        
        data = response.json()
        
        if "erro" in data:
            print(f"Erro: CEP '{cep}' não encontrado ou inválido.")
            return
            
        print("--- Informações do Endereço ---")
        print(f"CEP: {data.get('cep', 'N/A')}")
        print(f"Logradouro: {data.get('logradouro', 'N/A')}")
        print(f"Complemento: {data.get('complemento', 'N/A')}")
        print(f"Bairro: {data.get('bairro', 'N/A')}")
        print(f"Localidade: {data.get('localidade', 'N/A')} - {data.get('uf', 'N/A')}")
        print(f"IBGE: {data.get('ibge', 'N/A')}")
        print(f"GIA: {data.get('gia', 'N/A')}")
        print(f"DDD: {data.get('ddd', 'N/A')}")
        print(f"SIAFI: {data.get('siafi', 'N/A')}")
        print("-------------------------------")
        
    except requests.exceptions.HTTPError as http_err:
        print(f"Erro HTTP ao consultar o CEP: {http_err}")
    except requests.exceptions.ConnectionError as conn_err:
        print(f"Erro de Conexão: Verifique sua conexão com a internet. {conn_err}")
    except requests.exceptions.Timeout as timeout_err:
        print(f"Timeout: A requisição demorou muito para responder. {timeout_err}")
    except requests.exceptions.RequestException as req_err:
        print(f"Ocorreu um erro inesperado na requisição: {req_err}")
    except ValueError:
        print("Erro ao decodificar a resposta JSON. A API pode ter retornado algo inesperado.")

# --- Exemplo de uso ---
cep_digitado = input("Digite o CEP (apenas números): ")
if cep_digitado.isdigit() and len(cep_digitado) == 8:
    consultar_cep(cep_digitado)
else:
    print("CEP inválido. Por favor, digite 8 dígitos numéricos.")
