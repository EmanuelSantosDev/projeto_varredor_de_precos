# Hospedagem VPS


- Vamos hospedar gratuitamente nosso Bot/Automação Selenium em uma VPS utilizando o serviço **Amazon EC2**.


## VPS (Virtual Private Server) 


- Servidor virtualizado hospedado em um servidor físico.
- Cada VPS é isolada, permitindo personalização e controle.
- Compartilha recursos físicos, como CPU, RAM e armazenamento.
- Oferece flexibilidade e escalabilidade para hospedar sites e aplicativos.
- Custa menos que um servidor dedicado, mas mais que hospedagem compartilhada.
- Popular para desenvolvimento, hospedagem de sites e aplicativos.

## Amazon EC2


- Serviço de computação em nuvem da Amazon Web Services (AWS) que oferece capacidade de processamento escalável na nuvem.
- Utiliza virtualização para fornecer instâncias de servidores virtuais.
- Os usuários pagam apenas pelos recursos computacionais que utilizam.


## Passos Iniciais


- Criar um repositório do Projeto no Github
- Criar uma conta na AWS
- Criar uma VPS (Instância do Ubuntu) + Key Pair


## Configurações Obrigatórias do Selenium


```python
# app.py
arguments = ['--lang=en-US', '--window-size=1920,1080',
            '--incognito', '--disable-gpu', '--no-sandbox', '--headless', '--disable-dev-shm-usage']
```


## Operando a VPS


### Conectando-se à VPS


1. EC2
1. Instâncias (em execução)
1. ID da instância
1. Conectar
1. Cliente SSH
1. Copiar o "código de autenticação"
1. Abrir o aplicativo **Terminal** no diretório que está salvo a chave de autenticação 
1. Executar o "código de autenticação"


### Atualizando os Pacotes do Ubuntu


**Atualizando a LISTA de Pacotes Padrão do Ubuntu:**
```
sudo apt-get update -y
```

**Atualizando os Pacotes Padrão do Ubuntu:**
```
sudo apt-get upgrade -y
```


### Instalando o GIT no Ubuntu


```
sudo apt-get install git
```


### Instalando o Google Chrome no Ubuntu


```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
```


Provavelmente emitirá alguns erros durante a instalação. Então, vamos rodar o comando:
```
sudo apt-get install -f
```
Indica que você deseja corrigir pacotes com dependências quebradas.

Após a instalação, pode se excluir do repositório o Pacote de Instalação do Google Chrome.


### Transferindo o Projeto para a VPS


**No terminal da VPS executar:**
```
git clone <endereço-https-repositório>
``` 


### Criando e Ativando o Ambiente Virtual


```
python3 -m venv <nome-do-ambiente>
```

- O próprio terminal irá sugerir uma linha de comando para baixar a biblioteca necessária para a criação de um ambiente virtual.
- Após isso repita o comando para criação do ambiente virtual.


```
python3 -m venv <nome-do-ambiente>
source <nome-do-ambiente>/bin/activate
```


### Com o Ambiente Virtual Ativado vamos Instalar as Bibliotecas
```
pip3 install selenium webdriver-manager
```


### Rodando a Aplicação
```
python3 app.py
```


### Encerrando a Aplicação
```
ctrl + c
```


### Executando Múltiplos Programas (Terminal Desbloqueado)


- ``nohup``: permite que o processo continue em execução mesmo que você feche o terminal ou deslogue.
- ``&``: coloca o comando anterior (no caso, python3 app.py) em segundo plano, permitindo que você continue usando o terminal enquanto o processo está em execução.
- retornará um número de ``id`` que é essencial para identificar o processo (bot) rodando no sistema. 
- cria um arquivo chamado ``nohup.out`` que armazena qualquer saída que normalmente seria exibida no terminal e é útil para verificar mensagens de erro ou outras informações de diagnóstico.

```
nohup python3 app.py &
```

### Verificando o arquivo ``nohup.out``:
```
cat nohup.out
```


### Encerrando o Processo Através do Gerenciador de Tarefas


```
htop
```

- Localizar o processo em execução
- ``F9`` (kill) + ``Enter``



### Desativando o Ambiente Virtual


```
deactivate
```


### Deslogando do Servidor Remoto


```
exit
```