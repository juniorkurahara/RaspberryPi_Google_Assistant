<h1 align="center"> Google Assistant on RaspberryPi </h1>

<h2> Descrição do projeto </h2>
<p> Assistente do Google rodando no Raspberry Pi via SDK. </p>

<h2> Status do projeto </h2>
<h4 align="left"> VERSÃO 01 </h4>

![Badge em Desenvolvimento](http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge)

<h2> 🔧 Ferramentas necessárias </h2>

- `Microfone`: Entrada de dados para o Google Assistant (Pode ser BT ou USB)
- `Auto-falante / fone`: Saída de dados do Google Assistant (Pode ser BT, USB ou P2)
- `Raspberry Pi (desejável versão 4)`: Processamento e interface do Google Assistant
- `Conta no Google`: Item imprescindível 😆

<h2> :hammer: Funcionalidades do projeto </h2>

A principal funcionalidade deste projeto é fazer o Google Assistant rodar em um dispositivo baseado em Linux, neste caso um Raspberry Pi 4.

- `Google Assistant`: é um aplicativo de software de assistente virtual desenvolvido pelo Google que está disponível principalmente em dispositivos móveis e de automação residencial. Com base na inteligência artificial, o Google Assistant pode se envolver em conversas bidirecionais, ao contrário do assistente virtual anterior da empresa, o Google Now. (By Wikipédia)

 
<h2> 💻: Tecnologias utilizadas </h2>

- `SDK Google Assistant`

<h2> ✍️ Hands on </h2>

Antes de começar: Obtenha um Raspberry Pi, instale o sistema operacional Raspian, certifique-se que possui acesso a internet e certifique-se que possui o microfone e o fone, conforme o item :hammer: Funcionalidades do projeto.


<h3> Criação do projeto no Google Cloud </h3>

- `1º passo:` Acesse o endereço: https://console.actions.google.com/, crie um novo projeto no botão <b> NEW PROJECT </b>, dê um nome de sua preferência e salve o projeto.

- ![image](https://user-images.githubusercontent.com/68716232/175789329-70c14247-7798-4577-b5d2-0a1d6aec1d44.png)

`2º passo:` Clique no link para registrar um dispositivo.

![image](https://user-images.githubusercontent.com/68716232/175789452-13236e8a-d470-45a8-b2e6-a716df9bb4d4.png)

`3º passo:` Na tela de registro do modelo, insira o product name (qualquer), manufacturer name (qualquer), no campo device type coloque a opção speaker, <b>copie seu Model-Id</b> (🚨 Importante 🚨) e clique no botão para registrar.

![image](https://user-images.githubusercontent.com/68716232/175789590-795cddd4-6934-44df-a9cb-0938d3e0d1f6.png)

`4º passo:` Na próxima tela faça o download de sua credencial (guarde pois será utilizada mais tarde), clique em next e depois no botão save traits. 

![image](https://user-images.githubusercontent.com/68716232/175789642-ec2b96f4-c762-4cd6-949a-4dafa5f8985b.png)

`5º passo:` Acesse o endereço: https://console.cloud.google.com/apis, certifique-se que está no projeto em que acabou de criar e clique no botão ativar apis e serviços.

![image](https://user-images.githubusercontent.com/68716232/175789761-c5b1fdea-4153-4e35-9c5f-7a8f495f0e45.png)

`6º passo:` Pesquise por: Google Assistant API, selecione o serviço e clique no botão ativar.

![image](https://user-images.githubusercontent.com/68716232/175789820-fbf4aa96-2bfc-46bd-85fe-4eba23e29574.png)

`7º passo:` Na próxima tela, vá até credenciais, depois configurar tela de consentimento, selecione a opção EXTERNO e depois clique no botão criar.

![image](https://user-images.githubusercontent.com/68716232/175789887-f5d632b7-8355-4e67-af55-7e58827a065f.png)

![image](https://user-images.githubusercontent.com/68716232/175789926-eeadc9e0-d5cc-4acb-a04b-63f79b623133.png)

`7º passo:` Na tela de permissão OAUTH, insira seu e-mail nos dois campos indicados, salve e continue até voltar ao painel princial.

![image](https://user-images.githubusercontent.com/68716232/175789982-3a4bf5ec-4d15-46de-ab77-89a21bf43879.png)

![image](https://user-images.githubusercontent.com/68716232/175790010-12d3c9d5-fe93-4385-bf19-0017f79f44a8.png)


<h3> Habilitando a permissão de APP terceiros </h3>

- Acesse o endereço: https://myaccount.google.com, acesse o controle de atividades (activity controls) e habilite o item: <i>Incluir atividade de voz e áudio. </i>.

![image](https://user-images.githubusercontent.com/68716232/175830932-0757b6b4-54c4-4192-9be0-0826d3fea4c9.png)

<b>Nota:</b> Certifique-se que está logado na mesma conta do google em todas etapas do projeto.


<h3> Configurando os dispositivos de áudio </h3>

- `1º passo:` Abra o terminal e digite o comando `arecord -l`, isso irá mostrar os dispositivos de gravação conectados no Raspberry Pi (no caso de dispositivos BT não aparece neste comando, mas vamos ver como testar seu funcionamento no passo 4.

- `2º passo:` Digite o comando `speaker-test -t -wav`, para reproduzir um áudio teste.

- `3º passo:` Digite o comando `arecord -- format=S16_LE --duration=5 --rate=16000 --file-type=raw out.raw`, isso irá gravar um áudio durante 5 segundo após pressionar enter.

- `4º passo:` Digite o comando `aplay -- format=S16_LE --rate=16000 out.raw`, isso irá reproduzir o áudio gravado.

- `5º passo:` Digite o comando `sudo apt-get update` e depois `sudo apt-get upgrade` para atualizar as possiveis modificações.


<h3> Configurando um novo ambiente virtual para o Python </h3>

Pressupondo que já possui o Python 3 ou superior...

- `1º passo:` Digite  o comando `sudo apt-get install python3-dev python3-venv`

- `2º passo:` Digite  o comando `python3 -m venv env`

- `3º passo:` Digite  o comando `env/bin/python -m pip install --upgrade pip setuptools wheel`

- `4º passo:` Digite  o comando `source env/bin/activate`


<h3> Instalando as bibliotecas </h3>

- `1º passo:` Digite  o comando `sudo apt-get install portaudio19-dev libffi-dev libssl-dev libmpg123-dev`

- `2º passo:` Digite  o comando `python -m pip install --upgrade google-assistant-library`

- `3º passo:` Digite  o comando `python -m pip install --upgrade google-assistant-sdk[samples]`


<h3> Gerando as credenciais </h3>

- `1º passo:` Digite  o comando `python -m pip install --upgrade google-auth-oauthlib[tool]`

- `2º passo:` Copie o arquivo da credencial (Conforme 4º passo do item Criação do projeto no Google Cloud) e cole na pasta `home/pi`

- `3º passo:` Digite  o comando `google-oauthlib-tool --scope https://www.googleapis.com/auth/assistant-sdk-prototype --save --headless --client-secrets [cole aqui apenas o nome do arquivo da credencial com a extensão .json (Conforme 4º passo do item Criação do projeto no Google Cloud)]`

![image](https://user-images.githubusercontent.com/68716232/175842189-3bc9138f-75a8-4883-83b8-21371022c279.png)

- `4º passo:` Será necessário entrar no link fornecido para autorizar o acesso. Após autorizar, digite o código fornecido pelo Google no terminal

![image](https://user-images.githubusercontent.com/68716232/175842493-d363020e-ea78-4629-a748-c8643091fd14.png)

![image](https://user-images.githubusercontent.com/68716232/175842630-d8746c40-7481-4132-8737-04d9e23d928f.png)

![image](https://user-images.githubusercontent.com/68716232/175842685-0de61624-00c8-47a6-9286-1dfec57adda0.png)

- `5º passo:` Por fim, para rodar o modelo, digite o comando `googlesamples-assistant-hotword --project-id [ID do projeto] --device-model-id [nome do dispositivo]`


- <b>Caso não tenha o ID do projeto e nome do dispositivo, sigam esses passos:</b>

Acesse o site https://console.actions.google.com/, acesse seu projeto, nos 3 pontinhos no canto superior direito da tela acesse as configurações do projeto e pronto!

![image](https://user-images.githubusercontent.com/68716232/175843215-25472f5e-d2e9-4b27-9df5-e969be3168aa.png)

![image](https://user-images.githubusercontent.com/68716232/175843335-657727f0-79b7-4fc7-a8fc-2bb25f43bac8.png)

Nota: No primeiro acesso, precisei confirmar meus dispositivos de áudio e não funcionou o comando de voz "OK GOOGLE", então fechei e abri o terminal e reescrevi os comandos a partir da etapa <i>Configurando um novo ambiente virtual para o Python</i>. Após isso funcionou muito bem! 😄 


<h2> Autores </h2>

`https://github.com/juniorkurahara`

![Kurahara](https://user-images.githubusercontent.com/68716232/173880477-6429c7f5-bff5-462d-a2c0-6cadf59b07b7.jpg)
<h2> Source: </h2> 
 <p> https://www.youtube.com/watch?v=tplwfET2H1o </p>
 <p> https://developers.google.com/assistant/sdk/guides/library/python </p>
