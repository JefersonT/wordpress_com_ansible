# Criando serviço Wordpress com Ansible
<p>Este projeto foi desenvolvido com o objetivo de por em prática os conhecimentos adquiridos nos Curso de Ansible: sua infraestrutura como código disponível na plataforma da Alura. Este projeto teve seu foco em criar e configurar um serviço de Wordpress com integração a banco de dados MySQL utilizando Vagrant para virtualização das máquinas e Ansible para automação das configurações dos serviços. Aqui pode ser observado uma estruturação básica dos diretórios e arquivos para uma boa prática na estruturação e organização de projetos com ansible.</p>

# Pre-requisitos para Compreensão:
 - Linux (Terminal) - Básico;
 - Vagrant - Básico;
 - Ansible - Básico;


## Passo-a-passo para executar e testar o projeto(Linux).
### Instalação dos pacotes necessário:
 1. Atualizar os Pacotes
 ```$ sudo apt-get update
 ```

 2. Instalar o Python
 ```$ sudo apt-get install python3
 ```

 3. Instalar o Ansible
 ```$ sudo apt-get install ansible
 ```

 4. Instalar o Vagrant
 ```
 $ curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
 $ sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
 $ sudo apt-get update && sudo apt-get install vagrant
 ```

 5. Instalar o VirtualBox
  >Acesse o site [VirtualBox](https://www.virtualbox.org/), faça o download para seu sistema operacional e instale seguindo as suas instruções.

 6. Instalar um IDE ou editor de texto de sua Preferência;


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
