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

This repository was created as an AWS EC2 instances managing project for a cloud fundamentals with AWS bootcamp on DIO.

