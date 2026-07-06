# Gerencia_EC2_AWS
**Este repositório foi criado como um projeto de gerenciamento de instâncias AWS EC2 para um bootcamp de fundamentos de cloud com AWS na DIO.**

O objetivo deste repositório é documentar e compartilhar os conhecimentos, por mim absorvidos, durante as duas aulas apresentadas até o momento em que o projeto foi proposto. Porém, pretendo continuar alimentando o mesmo com atualizações até o final do bootcamp para que sirva como maneira de revisitar o conteúdo que estudei e como fonte de pesquisa para aqueles que possuam interesse no tema.

##**Módulo 1 - Introdução à AWS e conceitos básicos**

Nesta coletânea de 5 cursos e uma live de apresentação do bootcamp, fomos introduzidos, principalmente, a conceitos introdutórios e passamos por uma apresentação da plataforma web da AWS. Ambiente onde a maior parte nos será apresentado.

Acredito que os pontos mais importantes que foram abordados nessas aulas foram os seguintes:
- Amazon AWS se trata de um IaaS (*Infrastructure as a Service*);
- Seu modelo de negócios é o OPEX (Operational Expenditure), onde cobranças são emitidas de acordo com o uso dos recursos contratados;
- Sua estrutura se baseia em *Availability Zones* (Conjunto de 2-3 *data centers*) e *Regions* (Áreas geográficas onde se localizam as *Availability Zones*);
- Nem todos os serviços estão disponíveis em todas as *Regions*, e um mesmo serviço pode ter custos diferentes em *Regions* diferentes;
- A escolha dos recursos sempre deve levar em conta a relação Custo/Latência;
- Importância da segurança e autenticação de vários fatores (MFA);
- Definição e importância de uma conta *Root*;
- Criação e gerenciamento de usuário utilizando o **IAM** (*Identity Access Manager*);
- Aplicação de políticas e permissões aos usuários e grupos de usuários;
- Definição de alertas para gestão dos gastos;
- Formas de acesso e suas profundidades (AWS Console -> Cloud Shell -> CLI);
- Por fim, durante a live, fomos apresentados à GLT (Patrocinadora do *bootcamp*) e tivemos um prospecto da carreira de *Solutions Architect*.

##**Módulo 2 - Computação na Nuvem com EC2**

No segundo módulo, fomos apresentados às instâncias EC2 (*Elastic Cloud Compute*), máquinas virtuais que podem atuar como servidores Windows ou Linux.

Existem diversas modalidades de máquinas, as quais podemos escolher de acordo com nossas necessidades, custo e escalabilidade.

![Famílias de Instâncias](<img width="906" height="447" alt="Captura de tela 2026-07-02 170632" src="https://github.com/user-attachments/assets/02636c63-c1a3-4d20-91df-ba7f4f162336" />)

![Tipos de Instâncias](<img width="881" height="413" alt="Captura de tela 2026-07-02 170853" src="https://github.com/user-attachments/assets/e7e6aaaf-8f19-4ef5-95b6-93b6503a629d" />)

Outro ponto importante são maneiras de economizar fundos e otimizar recursos, o que pode ser feito desligando instâncias não utilziadas e removendo recursos ociosos.

Vale também pontuar dois tipos de escalamento aos quais somos apresentados, o escalamento horizontal (quantidade) e o escalamento vertical (qualidade)

Depois, fomos apresentados aos conceitos de EBS (*Elastic Block Store*) e S3 (Simple Storage Service):
- EBS = Unidade de armazenamento altamente confiável que pode ser anexada a qualquer instância EC2 (funcionando como um HD externo virtual)
- S3 = Unidade de armazenamento de objetos em nuvem escalável com diferentes níveis de armazenamento com base em frequência de acesso (funciona como um *Google Drive* escalável)

![alt text](<img width="1157" height="473" alt="Captura de tela 2026-07-02 172349" src="https://github.com/user-attachments/assets/ca89d334-6cef-4e1a-b016-a46cd7ee77b2" />)

Posteriormente visitamos o tópico das AMIs, o que são, como criá-las e personalizá-las. Uma AMI (*Amazon Machine Image*) é uma imagem de máquina virtual pré-configurada, que inclui as informações necessárias para iniciar uma instância, como o sistema operativo, o servidor de aplicações e as aplicações.

Em sequência, aprendemos o conceito de Snapshots EBS. EBS é um serviço de backup nativo do AWS que faz backup dos volumes do EBS em um determinado momento, e é possível configurar a frequência com que os snapshots são tirados. Para fins de recuperação de desastres (DR), os instantâneos do EBS podem ser armazenados em uma região remota. Snapshots do amazon EBS são cópias em pontos no tempo de um volume armazenado no S3. Podem ser utilizados para criar um volume do amazon EBS, aumentar a durabilidade de dados e fornecer um mecanismo de backup e restauração para volumes do EBS.

Por fim, chgamos ao desafio que originou este repositório. Nos foi apresentado o software [Draw.IO](https://www.drawio.com/), que deveria ser utilizado para representarmos nossa arquitetura C~l~o~u~d. Segue minha representação de uma estrutura que utiliza instâncias EC2, EBS e AMI:

![Estrutura_Cloud](<img width="716" height="748" alt="Captura de tela 2026-06-30 172011" src="https://github.com/user-attachments/assets/dada11c2-ce88-4525-8b02-0a678dc8ecc2" />)

Continuarei o desenvolvimento deste repositório conforme avançar em meus estudos.
---

#Após realizar a entrega do projeto darei continuidade com a alimentação deste repositório de maneira mais direta e objetiva

##Módulo 3 - Criando Recursos na AWS: 3 cursos

###Curso 1 - Criando sua Primeira Instância Amazon EC2

Todo o processo de contratação de uma EC2 é altamente intuitivo. Durante o procedimento a própria plataforma nos ajuda a selecionar o tipo de instância mais adequada para cada objetivo com a opção de *"Obter conselhos"*.

Moba é uma ferramenta gratuita que serve como um terminal SSH que nos permite conectar as instâncias EC2. 

O principal conselho que recebemos é o de explorar a plataforma. Como o próprio instrutor do curso não se aprofunda muito nos detalhes, explorar e pesquisar por conta própria realmente é a melhor opção para nos aprofundarmoos em todas as funcionalidades da plataforma AWS.

**VPC (*Virtual Private Cloud*)** = É um recurso de network da AWS que permite o acesso às instâncias.

![alt text](<img width="807" height="514" alt="Captura de tela 2026-07-03 102433" src="https://github.com/user-attachments/assets/48da9245-2d81-4733-8baf-e44563c9ed76" />
)
- Para acessar instâncias Linux usamos o protocolo SSH
- Para acessar instâncias Windows usamos o protocolo RDP

###Curso 2 - Criando seu Primeiro Bucket no Amazon S3

Amazon S3 é uma ferramenta muito utilizada para o processamento de arquivos em grande escala.

Buckets são o contêiner fundamental de armazenamento do serviço S3. Funcionam como uma pasta raiz na nuvem e servem para armazenar, mover e versionar qualquer tipo de arquivo.

Durante esta parte do curso iremos editar uma página pré existente de HTML como forma de blog pessoal e iremos subí-la em um S3. É essencialmente a criação de um portfólio.

###Curso 3 - Criando sua Primeira Função com Amazon Lambda

S~e~r~v~e~r~l~e~s~s - É um novo paradigma onde os desenvolvedores não precisam gerenciar servidores. Este conceito nos ajuda a se preocupar somente com nosso código, não precisando gerenciar instâncias.

Diferenças entre EC2 e Lambda Functions:
EC2:
- Servidor virtualizado
- Limitado por RAM e CPU
- Servidor ligado 24 horas
- Escalonamento manual / gerenciado

Lambda:
- Sem servidor para gerenciar
- Limite de tempo - máximo 15 min por requisição
- Execução somente quando requisitado
- Escalonamento automático

A Lambda Function é essencialmente uma função, da mesma maneira que em um bloco de código. Definimos um "trigger", algo que vai ativar a função e então a mesma é executada utilizando nosso código. A aula em si foi mais demonstrativa, mas deu para entender bem o poder de se utilizar as functions.

---

This repository was created as an AWS EC2 instances managing project for a cloud fundamentals with AWS bootcamp on DIO.

The purpose of this repository is to document and share the knowledge I have acquired during the first two classes presented up to the moment this project was proposed. However, I intend to continue updating it until the end of the bootcamp so that it serves as a way to revisit the content I have studied and as a reference source for anyone interested in the subject.

##**Module 1 - Introduction to AWS and Basic Concepts**

In this collection of five courses and a bootcamp introduction live session, we were introduced mainly to AWS fundamentals and given an overview of the AWS web platform, which is the environment where most of our learning will take place.

I believe the most important topics covered during these lessons were:

- Amazon AWS is an IaaS (Infrastructure as a Service);
- Its business model follows OPEX (Operational Expenditure), where charges are based on the actual usage of contracted resources;
- Its infrastructure is organized into Availability Zones (groups of 2–3 data centers) and Regions (geographical areas that contain multiple - Availability Zones);
- Not all services are available in every Region, and the same service may have different costs depending on the Region;
- Resource selection should always consider the Cost/Latency trade-off;
- The importance of security and Multi-Factor Authentication (MFA);
- Definition and importance of the Root account;
- Creating and managing users with IAM (Identity and Access Management);
- Applying policies and permissions to users and user groups;
- Setting up billing alerts for cost management;
- AWS access methods and their different levels of control (AWS Console → CloudShell → CLI);
- Finally, during the live session, we were introduced to GLT (the bootcamp sponsor) and given an overview of the Solutions Architect career path.

##**Module 2 - Cloud Computing with EC2**

In the second module, we were introduced to EC2 (Elastic Compute Cloud) instances, virtual machines that can function as either Windows or Linux servers.

There are several instance families available, allowing us to choose according to our requirements, budget, and scalability needs.

![Instânce Families](<img width="906" height="447" alt="Captura de tela 2026-07-02 170632" src="https://github.com/user-attachments/assets/02636c63-c1a3-4d20-91df-ba7f4f162336" />)

![Instance Types](<img width="881" height="413" alt="Captura de tela 2026-07-02 170853" src="https://github.com/user-attachments/assets/e7e6aaaf-8f19-4ef5-95b6-93b6503a629d" />)

Another important topic is how to reduce costs and optimize resources, which can be achieved by shutting down unused instances and removing idle resources.

It is also worth mentioning the two scaling strategies introduced during the course: horizontal scaling (increasing quantity) and vertical scaling (increasing capacity).

Next, we were introduced to the concepts of EBS (Elastic Block Store) and S3 (Simple Storage Service):

- EBS = A highly reliable block storage service that can be attached to any EC2 instance (working like a virtual external hard drive);
- S3 = A scalable cloud object storage service with multiple storage classes based on access frequency (similar to a scalable Google Drive).

![alt text](<img width="1157" height="473" alt="Captura de tela 2026-07-02 172349" src="https://github.com/user-attachments/assets/ca89d334-6cef-4e1a-b016-a46cd7ee77b2" />)


Later, we explored the concept of AMIs, what they are, and how to create and customize them. An AMI (Amazon Machine Image) is a pre-configured virtual machine image that contains all the information required to launch an instance, including the operating system, application server, and installed applications.

Next, we learned about EBS Snapshots. EBS Snapshots are AWS's native backup service, allowing point-in-time backups of EBS volumes. It is possible to configure how frequently snapshots are taken. For Disaster Recovery (DR) purposes, snapshots can also be stored in a different AWS Region. Amazon EBS Snapshots are point-in-time copies of a volume stored in Amazon S3. They can be used to create new Amazon EBS volumes, improve data durability, and provide backup and restore capabilities for EBS volumes.

Finally, we reached the challenge that originated this repository. We were introduced to the software Draw.IO, which we used to represent our Cloud architecture. Below is my representation of a structure using EC2 instances, EBS, and AMIs:

![Estrutura_Cloud](<img width="716" height="748" alt="Captura de tela 2026-06-30 172011" src="https://github.com/user-attachments/assets/dada11c2-ce88-4525-8b02-0a678dc8ecc2" />)

I will continue updating this repository as I progress through my studies.

#After submitting this project, I will continue updating this repository in a more direct and objective manner.

##Module 3 - Creating Resources in AWS: 3 Courses

###Course 1 - Creating Your First Amazon EC2 Instance

The entire EC2 provisioning process is highly intuitive. Throughout the setup process, the AWS platform itself helps us choose the most appropriate instance type for each use case through the *"Get Advice"* option.

MobaXterm is a free tool that functions as an SSH terminal, allowing us to connect to EC2 instances.

The main advice we received was to explore the platform. Since the course instructor does not go into great detail about every feature, exploring the platform and conducting independent research is truly the best way to gain a deeper understanding of AWS's capabilities.

**VPC (*Virtual Private Cloud*)** = An AWS networking service that enables access to EC2 instances.

![alt text](<img width="807" height="514" alt="Captura de tela 2026-07-03 102433" src="https://github.com/user-attachments/assets/48da9245-2d81-4733-8baf-e44563c9ed76" /> )

- Linux instances are accessed using the SSH protocol;
- Windows instances are accessed using the RDP protocol.
