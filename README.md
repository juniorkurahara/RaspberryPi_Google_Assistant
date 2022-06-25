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





<h2> Autores </h2>

`https://github.com/juniorkurahara`

![Kurahara](https://user-images.githubusercontent.com/68716232/173880477-6429c7f5-bff5-462d-a2c0-6cadf59b07b7.jpg)
<h2> Source: </h2> 
 <p> https://www.youtube.com/watch?v=tplwfET2H1o </p>
 <p> https://developers.google.com/assistant/sdk/guides/library/python </p>
