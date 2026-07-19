# Gerencia_EC2_AWS
**Este repositório foi criado como um projeto de gerenciamento de instâncias AWS EC2 para um bootcamp de fundamentos de cloud com AWS na DIO.**

O objetivo deste repositório é documentar e compartilhar os conhecimentos, por mim absorvidos, durante as duas aulas apresentadas até o momento em que o projeto foi proposto. Porém, pretendo continuar alimentando o mesmo com atualizações até o final do bootcamp para que sirva como maneira de revisitar o conteúdo que estudei e como fonte de pesquisa para aqueles que possuam interesse no tema.

## **Módulo 1 - Introdução à AWS e conceitos básicos**

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

## **Módulo 2 - Computação na Nuvem com EC2**

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

## **Módulo 3 - Criando Recursos na AWS: 3 cursos**

### Curso 1 - Criando sua Primeira Instância Amazon EC2

Todo o processo de contratação de uma EC2 é altamente intuitivo. Durante o procedimento a própria plataforma nos ajuda a selecionar o tipo de instância mais adequada para cada objetivo com a opção de *"Obter conselhos"*.

Moba é uma ferramenta gratuita que serve como um terminal SSH que nos permite conectar as instâncias EC2. 

O principal conselho que recebemos é o de explorar a plataforma. Como o próprio instrutor do curso não se aprofunda muito nos detalhes, explorar e pesquisar por conta própria realmente é a melhor opção para nos aprofundarmoos em todas as funcionalidades da plataforma AWS.

**VPC (*Virtual Private Cloud*)** = É um recurso de network da AWS que permite o acesso às instâncias.

![alt text](<img width="807" height="514" alt="Captura de tela 2026-07-03 102433" src="https://github.com/user-attachments/assets/48da9245-2d81-4733-8baf-e44563c9ed76" />
)
- Para acessar instâncias Linux usamos o protocolo SSH
- Para acessar instâncias Windows usamos o protocolo RDP

### Curso 2 - Criando seu Primeiro Bucket no Amazon S3

Amazon S3 é uma ferramenta muito utilizada para o processamento de arquivos em grande escala.

Buckets são o contêiner fundamental de armazenamento do serviço S3. Funcionam como uma pasta raiz na nuvem e servem para armazenar, mover e versionar qualquer tipo de arquivo.

Durante esta parte do curso iremos editar uma página pré existente de HTML como forma de blog pessoal e iremos subí-la em um S3. É essencialmente a criação de um portfólio.

### Curso 3 - Criando sua Primeira Função com Amazon Lambda

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

## **Módulo 4 - Redes na AWS**

### Curso 1 - Introdução à Amazon VPC

VPC (*Virtual Private Cloud*) = Bairro
*SubNet* = Ruas privadas ou públicas
*Amazon Security Group* = Guardinha
*Amazon Route 53* = Faz a transferência do DNS para o IP
*Amazon CloudFront* = Content Network Delivery. Entrega o conteúdo sem latência
Amazon EBL (*Elastic Load Balancer*) = Transfere a carga de serviço entre servidores para balanceamento

Amazon VPC permite utilizar recursos AWS em uma rede lógica isolada. 
Características:
- É como um datacenter flexível e escalável;
- Isolamento de rede;
- Controle de tráfego;
- Suporte a subredes
- Controle de endereçamento IP;
- Conectividade

### Curso 2 - Entendendo o que é uma subnet na Amazon VPC

O que é?
- Uma subnet é uma gama de endereços IP que compoem uma sub-rede dentro de uma VPC.

É dentro de subets que são criados os grupos de segurança e é onde protocolos e IPs podem acessar os nossos recursos.

VPC é como o prédio
Subnet é como o andar
IP é como o apartamento

### Curso 3 -Introdução ao Security Group na AWS

Serviço onde definimos as regras de acesso à rede e permissões de acesso às instâncias

Está taxado ao nível da placa de rede da instância

### Curso 4 - Explorando os Fundamentos do Route 53 na AWS

Route 53 é um serviço que faz a conversão do DNS (*Domain Name Service*) para endereços IP. Além disso, faz a resolução de nomes DNS para o nosso IP interno na AWS e a resolução de tráfego.

### Curso 5 - Introdução à Distribuição de Conteúdo com Amazon CloudFront

É um serviço que permite a entrega de conteúdo de forma global. Ou seja, o cliente consegue acessar conteúdos sem latência em escala global.

Faz a distribuição do conteúdo com base em Edge Location.

Edge Location é um servidor de cache. Esse tipo de servidor está espalhado pelo mundo e é usado para reduzir a latência de acesso. Funciona enviando e recebendo fragmentos do conteúdo para aliviar o tráfego de dados.

### Curso 6 - Entendendo o que é o Elastic Load Balancer

É um serviço que trabalha com a distribuição de carga de forma eficiente e automática para um grupo de servidores. Faz o balancemaneto de carga para aumentar velocidade e desempenho.

Existem 4 tipos de balanceadores:
1. Application Load Balancer:
   - Gerencia o tráfego de aplicações HTTP/HTTPS
   - Ideal para balancear o tráfego de aplicativos web que precisam de roteamento avançado
  
2. Network Load Balancer:
   - Gerencia o tráfego TCP/UDP a nível de rede
   - Ideal para balancear o tráfego de aplicativos que exigem alta performance e baixa latência
  
3. Gateway Load Balancer:
   - Combina Load Balancing com segurança de rede
   - ideal para distribuir tráfego e adicionar funcionalidades de segurança a aplicativos
  
4. Classic Load Balancer:
   - Legado. Distribui tráfego HTTP/HTTPS e TCP entre duas instâncias EC2
   - Ideal para aplicativos que foram desenvolvidos antes do surgimento de ALBs e NLBs
  
## **Módulo 5 - Banco de dados na AWS**

### Curso 1 - Entendendo o que é o Amazon RDS

RDS funciona com 6 tipos de bancos de dados:
- Maria DB
- Amazon Aurora
- Oracle
- Microsoft SQL Server
- Postgre SQL
- MySQL

### Curso 2 - Introdução ao Amazon DynamoDB

Amazon DynamoDB é ideal para aplicativos que exigem desempenho, felxibilidade e escalabilidade de um banco de dados NoSQL totalmente gerenciado

### Curso 3 - Explorando Estratégias de Backup e Recuperação de Dados na AWS

1. Identificar dados Críticos, definir RPO e RTO;
2. Selecionar qual serviço AWS será utilizado para armazenar o backup;
3. Implementar estratégia de backup (bkps regulares, cópias em multiplas regiões, automação e monitoramento, rds automated e snapshots, dynamo db on-demand bkp);
4. Recuperação e teste;
5. Segurança e conformidade (criptografar dados, controle de acesso, registros e auditorias);
6. Custo e otimização (gestão de custos);

## **Módulo 6 - Serviços de Armazenamento e CDN**

### Curso 1 - Introdução ao Amazon S3

*Buckets são os containers do S3

Características:
- Escalável;
- Durável;
- Seguro

### Curso 2 - Conhecendo o Amazon Glacier

90 dias é o mínimo para o Glacier

180 dias é o mínimo para o *Glacier Deep Archive*

Snow Family:
- Snowball: Migração de dados em larga escala (petaBytes)
- Snowball Edge (transporta dados em velocidade maior que a internet)
- Snowmobile

### Curso 3 - Entendendo a Distribuição de Conteúdo com Amazon CloudFront

ClooudFront é uma solução de CDN (*Content Distribution Network*) que faz cache dos assets armazenando cópias dos recursos estáticos (imagens, vídeos, arquivos CSS, etc.) em locais estratégicos (pontos de presença, ou POPs) próximos aos clientes finais. Isso faz com que a latência para acesso ao conteúdo pelo cliente seja reduzida, já que, quando ocorre uma requisição os recursos são entregues rapidamente a partir do cache mais próximo, e não do servidor.

### Desafio de Código - Aplicações Industriais com JavaScript e AWS

Acabou sendo um desafio simples que solicitava uma verificação de status com uma resposta diferente para cada caso. Minha maior dificuldade dessa vez foi utilizar uma linguagem que nunca utilizei para programar antes, nesse caso, JavaScript:

// Lê o status enviado pela máquina
const status = gets();

// Estrutura condicional para verificar o status
if (status === "ok") {
    print("Operacao normal");
} else if (status === "warning") {
    print("Manutencao preventiva");
} else if (status === "critical") {
    print("Parada imediata");
} else {
    print("Status desconhecido");
}

## Módulo 7 - Serviços Intermediários e Avançados

### Curso 1 - Entendendo como Funciona o AWS Lambda

EKS = Kubernets dentro da AWS
Kubernets é um serviço de orquestração de containers

SNS = serviço de notificações dentro da AWS

SQS = serviço de filas de mensagem dentro da AWS

AWS step functions = serviço de orquestração de funções lambda

**AWS Lambda é um serviço que executa seu código em resposa a eventos e gerencia automaticamente recursos de computação** e é um serviço serverless

Sempre que realizar uma ação no código é preciso fazer um deploy

### Curso 2 - Entendendo o que são Amazon ECS e EKS na Orquestração de Containers

Microserviços são a quebra de uma aplicação em diferentes blocos, assim, a manutenção de um microserviço não interfere no funcionamento dos outros.

Um serviço monolítico é quando todas as instâncias de uma aplicação ocorrem no mesmo bloco, de forma que, não é possível realizar a manutenção em um único serviço separado.

Amazon ECS (*Elastic Container Service*) = Serviço de orquestração de contêineres. Permite executar, interromper e gerenciar facilmente conteiners em um cluster -> Permite executar aplicações em contêineres em uma estrutura de microserviços.

Características:
- Simples gerenciamento
- Escalabilidade
- Fácil integração
- Segurança

Cada componente de um aplicativo é empacotado em um contêiner Docker -> Definimos uma tarefa para cada contêiner e configuramos os serviços no ECS para manter a disponibilidade deles

Escalabilidade automática, monitoramento e logging.

ECR Registry = Repositório de Contêiners

EKS (*Elastic Kubernetes Service*) = Integra o Kubernetes na AWS, para que possa usá-lo para gerenciar contêineres sem ter que baixar o cluster Kubernetes.

ECS VS. EKS = vai de gosto. ECS é mais automatizado e simples, já o EKS é mais manual porém mais complexo

### Curso 3 - Entendendo como Funcionam o Amazon SNS e SQS na Comunicação Assíncrona

Amazon SNS (*Simple Notification Service*) = Serviço de mensagens assícronas para notificação de mensagens entre aplicativos distribuídos e microserviços -> Permite o envio de notificações para dispositivos com outros serviços da AWS.

É dividido em Publishers, tópicos e subscribers.

Tópicos são pontos de acesso entre o Publisher e o Subscriber

Tópicos podem ser divididos em 2 tipos: FIFO ou Padrão:
-FIFO (First In/First Out): obedece a ordem de entrada e de saída
Padrão: Mais utilizado, mais flexível e menos rigoroso. Não obedece ordem de chegada e não garante a ordem exata das mensagens, podendo ser entregues mais de uma vez

SQS (*Simple Queue Service*) = Também entrega mensagens, porém, sem notificação. Trabalha com padrão de mensagens em filas.

Suaviza o tráfego e garante processamento consistente.

### Desafio de projeto 2 - Explorando Workflows Automatizados com AWS Step Functions

Step Functions = Construtor visual para criar fluxos de trabalho

Neste desafio ele fez a apresentação do step functions, que é basicamente um figma ou qualquer outra aplicação de white board com o diferencial de ser integrada diretamente na AWS. O desafio é somente enviar um repositório que contenha um resumo da aula, e como eu apenas continuei o repositório do primeiro desafio irei enviá-lo novamente.

Além de uma explicação sobre o serviço e seus conceitos, o instrutor também mostrou na prática como criar um workflow utilizando a ferramenta e como desfrutar de seu uso da melhor maneira.

## Módulo 8 - Gerenciamento e Governança na AW

### Curso 1 - Entendendo o que é o AWS CloudWatch

É um serviço que nos permite monitorar e criar alarmes que enviam notificações ou fazem alterações automaticamente nos recursos que estão sendo monitorados.

### Curso 2 - Fundamentos do AWS CloudTrail para Auditoria e Segurança na AWS

É um serviço da AWS que ajuda na auditoria operacional e de risco, a governança e a conformidade da sua conta da AWS. É um log de todas as ações dos usuários dentro da AWS. Os registros são salvos em um bucket do Amazon S3

### Desafio de projeto 3 - Implementando sua Primeira Stack com AWS CloudFormation

CloudFormation é um processo que auxilia na automação de criação de recursos na AWS por meio de templates que podem ser versionados. A partir deles podemos criar recursos simples como um EC2 ou até uma arquitetura mais completa.

Novamente, o desafio se baseia na entrega de um repositório README.md que contenha um resumo do conteúdo apresentado.

### Curso 3 - Gerenciando Usuários e Permissões na AWS com Identity and Access Management (IAM)

Este recurso já foi apresentado anteriormente.

### Curso 4 - Entendendo e Gerenciando Polices e Roels na AWS

