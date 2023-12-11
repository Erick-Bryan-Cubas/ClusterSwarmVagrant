# ClusterSwarmVagrant

Este projeto é parte de uma formação em Docker e consiste na criação de um cluster Swarm utilizando Vagrant para provisionar quatro máquinas virtuais: uma máquina master e três nodes (node01, node02 e node03). Cada máquina virtual possui um endereço IP fixo e todas estão equipadas com o Docker pré-instalado. A máquina master assume o papel de nó manager no cluster, enquanto as demais máquinas se juntam ao cluster como workers.

## Pré-requisitos

- [Vagrant](https://www.vagrantup.com/downloads) instalado
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) instalado (ou outro provedor de VMs suportado por Vagrant)

## Configuração

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/ClusterSwarmVagrant.git
cd ClusterSwarmVagrant
```

2. Execute o comando `vagrant up` para criar e provisionar as máquinas virtuais:

```bash
vagrant up
```

Este comando utilizará o Vagrantfile fornecido para criar as máquinas virtuais de acordo com as configurações especificadas.

3. Após a conclusão, você terá um cluster Swarm funcional.

## Detalhes de Configuração

- **Máquinas Virtuais:**
  - **master:** 
    - Memory: 1024 MB
    - CPU: 1
    - IP: 10.10.10.100
    - Imagem: bento/ubuntu-22.04
  - **node01:** 
    - Memory: 1024 MB
    - CPU: 1
    - IP: 10.10.10.101
    - Imagem: bento/ubuntu-22.04
  - **node02:** 
    - Memory: 1024 MB
    - CPU: 1
    - IP: 10.10.10.102
    - Imagem: bento/ubuntu-22.04

- **Provisionamento:**
  - O script `docker.sh` é executado em todas as máquinas para instalar o Docker e o Docker Compose.
  - O script `master.sh` é executado apenas na máquina master, iniciando o Swarm e gerando o token de join para workers.
  - O script `worker.sh` é executado nas máquinas node01, node02 e node03, juntando-as ao cluster Swarm como workers.

## Notas Adicionais

- Certifique-se de que os pré-requisitos estão instalados antes de executar o Vagrant.
- O arquivo `Vagrantfile` contém as definições de configuração das máquinas virtuais.
- Os scripts de provisionamento estão localizados no diretório `src`.

Aproveite o seu cluster Swarm! 🐳