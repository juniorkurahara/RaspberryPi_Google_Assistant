<h1 align="center"> Google Assistant on RaspberryPi </h1>

<h2> Descrição do projeto </h2>
<p> Assistente do Google rodando no Raspberry Pi via SDK </p>

<h2> Status do projeto </h2>
<h4 align="left"> VERSÃO 01 </h4>

![Badge em Desenvolvimento](http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge)

<h2> 🔧 Ferramentas necessárias </h2>

- `Microfone`: Entrada de dados para o Google Assistant (Pode ser BT OU usb)
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





<h2> Autores </h2>

`https://github.com/juniorkurahara`

![Kurahara](https://user-images.githubusercontent.com/68716232/173880477-6429c7f5-bff5-462d-a2c0-6cadf59b07b7.jpg)
<h2> Source: </h2> 
 <p> https://www.youtube.com/watch?v=tplwfET2H1o </p>
 <p> https://developers.google.com/assistant/sdk/guides/library/python </p>
