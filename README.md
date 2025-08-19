## **Tutorial JPA - Disciplina Persistência Orientada a Objetos**

Esta é uma atividade Java Web chamado Galeria de Arte. 
Projeto realizado para a disciplina Persistência Orientada a Objetos do 4º Semestre no curso de Sistemas para Internet - IFMT.

## Orientações 

- Criar um projeto Java Web chamado Galeria de Arte
- Usar o framework Hibernate
- Apagar os arquivos do Hibernate 4.X que foram trazidos pela IDE Importar os JARs do MySQL Conector ( https://dev.mysql.com/downloads/connector/j/ ), Hibernate e JPA ( https://hibernate.org/orm/releases/5.4/ )
- Apagar o hibernate.cfg.xml Crie uma unidade de persistência (persistence.xml).

**Obs.:** Não coloque src/conf (netbeans)

## **Tutorial JPA**

**Criar o projeto**

Crie um projeto Java Web chamado Galeria de Arte na IDE, definindo o nome do projeto e o pacote base.

**Passo 1:**
 - Com o NetBeans aberto, vá até a barra de menus no topo da janela.
- Clique na opção "File" (primeira opção da esquerda para a direita).
- No menu suspenso que aparece após clicar em "File", passe o cursor até a opção "New Project...".
- Clique em "New Project...".
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/8e829efe-d06d-4d88-95c9-6fa678f8a0bc" />

**Passo 2:**
- Na janela "New Project", você verá duas colunas principais:
     - Categories (à esquerda)
     - Projects (à direita)
- Em Categories, clique na pasta "Java with Ant" para expandir.
- Dentro da pasta, selecione a opção "Java Web" (destaque verde na imagem).
- Em Projects, escolha a opção "Web Application".
- Após selecionar Web Application, clique no botão "Next >" (na parte inferior da janela).
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/f7418f20-3f02-4266-bd55-1d11cd7e01f2" />

**Passo 3:**
- Na tela “Name and Location”, localize o campo “Project Name”.
- Digite o nome desejado para seu projeto.
     - Exemplo da imagem: GaleriadeArtee
- O campo “Project Location” indica onde o projeto será salvo no seu computador.
- O campo “Project Folder” mostra a pasta final onde o projeto será armazenado.
- Clique no botão “Next >” na parte inferior da janela para prosseguir.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/11c707b1-8690-4d55-b083-036fb418b853" />

**Passo 4:**
- Na tela "Server and Settings", localize o campo "Server".
- Selecione o servidor de aplicação que será usado para executar o projeto.
     - Exemplo da imagem: GlassFish Server
- Se ainda não tiver nenhum servidor configurado, clique no botão "Add..." para adicionar um.
- No campo "Java EE Version", selecione a versão da especificação Java EE (ou Jakarta EE) a ser usada pelo projeto.
     - Exemplo da imagem: Java EE 6 Web
- Deixe a opção "Enable Contexts and Dependency Injection" desmarcada, a menos que saiba que precisará de CDI.
- No campo "Context Path", o NetBeans preenche automaticamente com base no nome do projeto.
- Clique no botão “Next >” para ir à próxima etapa.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/a4d0ec00-986e-4d48-9d13-4aabe1d9f0d1" />

**Passo 5:**
- Na tela “Frameworks”, você pode escolher bibliotecas/frameworks adicionais para sua aplicação web.
- As opções disponíveis normalmente incluem:
     - Spring Web MVC
     - JavaServer Faces (JSF)
- Se você não precisa de nenhum framework adicional neste momento (como mostrado na imagem), deixe todas as opções desmarcadas.
       ℹ️ Você poderá adicionar frameworks ao projeto mais tarde, se necessário.
- Clique no botão “Finish” para concluir o assistente e gerar a estrutura do projeto.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/83739e6c-da7c-43e5-b687-f7c935fe3092" />

**Passo 6:**
Assim o projeto seja criado.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/407fc3ff-10e4-4d90-9e54-5d00a8a33d8a" />

**Remover Hibernate antigo da IDE**

Na aba de Libraries do projeto, remova as bibliotecas Hibernate 4.x adicionadas automaticamente pela IDE para evitar conflito com a versão que você vai usar.

**Passo 7:**
- No painel lateral esquerdo Projects, localize o nome do seu projeto.
- Clique com o botão direito do mouse sobre o nome do projeto para abrir o menu de contexto.
- No final da lista, clique em "Properties" (ou Propriedades, se o NetBeans estiver em português).
     - Isso abrirá a janela de propriedades do projeto, onde é possível modificar configurações avançadas.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/e8c23142-ffa5-4fd3-ac6c-028d1eb742e8" />

**Adicionar dependências (JARs)**

Adicione manualmente os JARs do MySQL Connector/J, Hibernate ORM 5.4.x e JPA ao projeto (ou configure via build tool, se preferir).

**Passo 8:**
- Na janela Project Properties, no menu lateral esquerdo, clique na categoria “Libraries”.
- Clique no botão "Add JAR/Folder" localizado no lado direito.
- Na janela de seleção de arquivos, navegue até a pasta onde está localizado o arquivo .jar da biblioteca desejada.
     - Exemplo da imagem:
     - C:\Users\Aluno\Downloads\hibernate-release-5.4.33.Final\lib\required\hibernate-core-5.4.33.Final.jar
- Selecione o arquivo e confirme.
- Verifique se a opção "Build Required Projects" está marcada (ela geralmente já vem ativada por padrão).
- Clique em “OK” para aplicar as alterações e fechar a janela.
     - O JAR adicionado aparecerá listado na seção Compile-time Libraries.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/366b774f-6341-4109-94af-e8ba3e004218" />

**Criar persistence.xml**

Crie o arquivo META-INF/persistence.xml e defina a Persistence Unit com o provider do Hibernate JPA.

**Passo 9:**
- No projeto GaleriadeArtee, clique com o botão direito sobre a pasta Configuration Files (ou em outro local desejado, como Source Packages ou Web Pages).
- No menu de contexto, clique em New > Other….
- Na janela "New File", vá até a categoria XML (como na imagem).
- No painel da direita, selecione a opção "XML Document".
- Clique em “Next >” para continuar.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/8567fd92-4a62-4943-b791-f74574aa324d" />

**Passo 10:**
- Na tela de criação do novo arquivo XML, no campo File Name, digite o nome do arquivo:
       persistence
- Confirme se o projeto selecionado está correto:
       GaleriaDeArte
- Verifique a pasta onde o arquivo será salvo (pode deixar o padrão do projeto ou selecionar outra pasta clicando em Browse...).
- Confira o caminho completo onde o arquivo será criado, mostrado abaixo.
- Clique em Next > para avançar para a próxima etapa.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/4cf2030d-ee4e-48f7-86dc-45fa31611bb0" />

**Passo 11:**
- Na tela Select Document Type, escolha a opção:
       Well-formed Document
- Clique no botão Finish para criar o arquivo persistence.xml com essa configuração.
<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/e86a7591-0993-42f8-9cff-9c5c2d857ea5" />

**Passo 12:**
- Dsssa forma você criou o arquivo persistence.xml dentro da pasta Configuration Files, exatamente como na imagem!
<img width="718" height="267" alt="image" src="https://github.com/user-attachments/assets/b76f2290-e88c-4da7-b220-248d4e522dd3" />

Feito com ❤️ por Valéria Alves
