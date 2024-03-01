# Hospedagem VPS


- Vamos hospedar gratuitamente nosso Bot/Automação Selenium utilizando o serviço **Amazon EC2**.


## Amazon EC2


- Serviço de computação em nuvem da Amazon Web Services (AWS) que oferece capacidade de processamento escalável na nuvem.
- Utiliza virtualização para fornecer instâncias de servidores virtuais.
- Os usuários pagam apenas pelos recursos computacionais que utilizam.


## Passos Iniciais


- Criar uma conta Amazon
- Criar uma VPS
- Colocar nossa automação dentro da VPS


## Configurações Obrigatórias para o uso de VPS


```python
# app.py
arguments = ['--lang=en-US', '--window-size=1920,1080',
            '--incognito', '--disable-gpu', '--no-sandbox', '--headless', '--disable-dev-shm-usage']
```


