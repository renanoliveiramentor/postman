<b>SFMC POSTMAN  - NÃO OFICIAL</b>

Os arquivos necessários estão neste repositório e o aplicativo Postman pode ser instalado a partir deste link: https://www.getpostman.com

<b>Descrição:</b>

•	SFMC.json.postman_collection: Este arquivo precisa ser importado para o Postman. Ele hospeda as chamadas REST e SOAP para a API SFMC.

•	useraccount.postman_environment: Este arquivo precisa ser importado para o Postman. Contém variáveis de ambiente específicas para cada conta SFMC individual à qual você deseja acessar. Você pode clonar para configurar várias contas SFMC conforme necessário.

<b>Requisitos da API REST:</b>

• Para executar as chamadas da API REST, você precisará preencher pelo menos as variáveis clientID e clientSecret no ambiente userAccount.

<b>Requisitos da API SOAP:</b>

<b>Você precisará preencher a variável soapEndPoint mais pelo menos um dos seguintes conjuntos de variáveis:</b>

•	Para o nome de usuário / Senha (WS-Security), é chamado  de soapUsername e soapPassword.

•	Para o Token (OAuth) chama-se clientID e clientSecret.

•	Você deve chamar a API REST Auth / RequestToken para obter um acesso de 60 minutos antes de fazer chamadas de API SOAP baseadas em token.

<b>Import para Postman:</b>

Você deve importar essa coleção e variáveis de ambiente para sua instância do Postman.

<b>Para importar a “Collection”:</b>

•	Clique em “Collection > Import” selecione o arquivo "SFMC.json.postman_collection".

![Alt Text](https://github.com/jsds96/sfmc-postman/blob/master/img/Import_postman_collection.png)

<b>Uma vez que isso seja concluído, você terá uma nova “collection” dentro de sua instância do Postman. :+1:</b>

<b>Para importar o “Environment”:</b>

•	Clique na “Engrenagem > Manage environments > Import” selecione o arquivo “useraccount.postman_environment”.

![Alt Text](https://github.com/jsds96/sfmc-postman/blob/master/img/Manage_Environments.png)

<b>Criando Packages em SFMC:</b>

•	Acesse: https://mc.exacttarget.com/

•	Vá para “Settings > Administration”

•	No menu “Account” clique em “Installed Packages”

•	Clique em “new” de um nome e uma descrição.

<b>Adicionando componente:</b>

•	Clique em “Add componente” depois clique em “API Integration” e “Next”.

•	Em “Channels” selecione todos os checkboxs e faça o mesmo para “Assets, automation, contacts, data, hub, provisioning e webhooks” e clique em “Save”

•	Guarde os valores de “AccountID”, “ClientID” e “ClientSecret”.

<b>Editando o “Environments”:</b>

•	Clique na “Engrenagem > Manage environments “ clique em “useraccount” altere o nome para sua preferencia.

<b>Edite os seguintes valores:</b>

•	ClientID > ClientID copiado da plataforma.

•	ClientSecret > ClientSecret copiado da plataforma.

•	SoapUserName > Seu login na plataforma.

•	SoapPassword > Seu senha na plataforma.

•	BusinessUnit > MID da sua conta.

•	Clique em “Update”, feche o “Manage Environments”.

•	Selecione o “environments”

<b>Uma vez que você tenha concluído as duas importações, você está pronto para terminar a configuração do envrionment. Nesta última etapa, o Postman configurará o restante das variáveis de ambiente necessárias.</b>

<b>Execute primeiro a chamada de autenticação:</b>

•	Clique na “Collection” importada, após isso clique em “Auth” de um duplo click em “Request SFMC Token” e clique em “Send”

•	Recupera um token de autenticação antes de executar a plataforma chamada.

![Alt Text](https://github.com/jsds96/sfmc-postman/blob/master/img/Request_Token.png)

• Deve retornar algo como isso:
“{
    "accessToken": "xxxx1xxxx2xxxx3xxxx4",
    "expiresIn": 3479
}”

•	Em segundo lugar, execute a chamada Platform / Retrieve Endpoints para injetar as variáveis SOAP & Rest em seu ambiente atual.

![Alt Text](https://github.com/jsds96/sfmc-postman/blob/master/img/Request_EndPoint.png)

Popula variáveis no "ambiente atualmente selecionado" do Postman, depois que esta chamada for concluída, a conta do usuário terá chaves / valores adicionais completas. :clap:

•	SOAP API end point information here: http://help.exacttarget.com/en/technical_library/web_service_guide/working_with_soap_web_service_api/

•	SOAP API code samples here: http://help.exacttarget.com/en/technical_library/web_service_guide/technical_articles/

