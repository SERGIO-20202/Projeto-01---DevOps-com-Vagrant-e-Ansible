# Projeto 01 - DevOps com Vagrant e Ansible

**Aluno**: Sérgio Henrique da Silva  
**Matrícula**: 20202380045  
**Disciplina**: Administração de Sistemas Abertos  
**Professor**: Leonidas Lima  
**Período**: 2025.1

## Objetivo
Provisionar uma infraestrutura DevOps com 4 VMs utilizando Vagrant e Ansible, configurando serviços como NFS, DHCP, Apache, MariaDB, LVM e SSH seguro.

## Estrutura do Projeto
- `Vagrantfile`: criação das VMs
- `ansible/`: automação da configuração
  - `hosts`: inventário
  - `playbook.yml`: playbook principal
  - `roles/`: configurações por função

## Como usar
```bash
# Iniciar as VMs
vagrant up

# Rodar o playbook
cd ansible
ansible-playbook -i hosts playbook.yml
```
