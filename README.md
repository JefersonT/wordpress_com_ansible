# Criando serviço Wordpress com Ansible
<p>Este projeto foi desenvolvido com o objetivo de por em prática os conhecimentos adquiridos nos Curso de Ansible: sua infraestrutura como código disponível na plataforma da Alura. Este projeto teve seu foco em criar e configurar um serviço de Wordpress com integração a banco de dados MySQL utilizando Vagrant para virtualização das máquinas e Ansible para automação das configurações dos serviços. Aqui pode ser observado uma estruturação básica dos diretórios e arquivos para uma boa prática na estruturação e organização de projetos com ansible.</p>

# Pre-requisitos para Compreensão:
 - Linux (Terminal) - Básico;
 - Vagrant - Básico;
 - Ansible - Básico;


## Passo-a-passo para executar e testar o projeto(Linux).
### Instalação dos pacotes necessário:
 1. Atualizar os Pacotes
  ```
    $ sudo apt-get update
  ```

 2. Instalar o Python
  ```
    $ sudo apt-get install python3
  ```

 3. Instalar o Ansible
  ```
    $ sudo apt-get install ansible
  ```

 4. Instalar o Vagrant
  ```
    $ curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
    $ sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
    $ sudo apt-get update && sudo apt-get install vagrant
  ```

 5. Instalar o VirtualBox
    >Acesse o site da [VirtualBox](https://www.virtualbox.org/), faça o download para seu sistema operacional e instale seguindo as suas instruções.

 6. Instalar um IDE ou editor de texto de sua Preferência;


### Para executar o projeto:
 1. Baixe ou clone o repositório;
 2. Acesse a pasta do projeto baixado;
 3. Abra o arquivo ***Vagrantfile*** e verifique se os IPs utilizados nas VMs do *wordpress* e *mysql* são compatíveis com o range de IPs disponíveis no VirtualBox;
    - Caso necessário altere-os conforme o disponível;
    - Também será necessário altera-los nos arquivos ***database.yml*** e ***wordpress.yml*** no diretório __group_vars__ e no arquivo ***hosts*** no diretório raiz do projeto;
 4. No diretório raiz execute o comando a seguir para subir as duas VMs:
  ```
   $ vagrant up
  ```
 5. Ainda no diretório raiz execute o seguinte comando para provisionar (configurar) as VMs através do ansible:
  ```
    $ ansible-playboock -i hosts provisioning.yml
  ```
 6. Ao finalizar o provisionamento acesso ao IP da VM *wordpress* em um navegador a partir da máquina host;
