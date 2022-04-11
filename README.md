# Criando serviço Wordpress com Ansible
<p>Este projeto foi desenvolvido com o objetivo de por em prática os conhecimentos adquiridos nos Curso de Ansible: sua infraestrutura como código disponível na plataforma da Alura. Este projeto teve seu foco em criar e configurar um serviço de Wordpress com integração a banco de dados MySQL utilizando Vagrant para virtualização das máquinas e Ansible para automação das configurações dos serviços. Aqui pode ser observado uma estruturação básica dos diretórios e arquivos para uma boa prática na estruturação e organização de projetos com ansible.</p>

# Pre-requisitos para Compreensão:
 - Linux (Terminal) - Básico;
 - Vagrant - Básico;
 - Ansible - Básico;


## Passo-a-passo para executar e testar o projeto.
### Pre-requisitos:
 - Instalar o <i>Python</i>;
 - Instalar o <i>Ansible</i>;
 - Instalar o <i>Vagrant</i>;
 - Instalar o <i>VirtualBox</i>;
 - Instalar um IDE ou editor de texto de sua Preferência;
 - Clonar o projeto em uma pasta local;

### Para executar o projeto:
 - Acesse a pasta do projeto;
 - Abra o arquivo <i>Vagrantfile</i> e verifique se os ips utilizados nas VMs do wordpress e mysql são compatíveis com o range de Ips disponíveis no VirtualBox;
   - Caso necessário altere-os conforme o disponível;
   - Caso tenha sido necessário alterar os ips, deve altera-los nos arquivos <i>database.yml</i> e <i>wordpress.yml</i> no diretório <strong>group_vars</strong> e no arquivo <i>hosts</i> na raiz do projeto;
 - No diretório raiz execute o comando a seguir para subir as duas VMs:
   - <code>vagrant up</code>
 - Ainda no diretório raiz execute o seguinte comando para provisionar (configurar) as VMs através do ansible:
   - <code>ansible-playboock -i hosts provisioning.yml</code>
 - Ao finalizar o provisionamento acesso ao Ip da vm do wordpress a partir da máquina hosts;
