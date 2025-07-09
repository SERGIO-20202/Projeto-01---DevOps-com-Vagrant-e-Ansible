# Projeto 01 - DevOps com Vagrant e Ansible

**Aluno**: Sérgio Henrique da Silva  
**Matrícula**: 20202380045  
**Disciplina**: Administração de Sistemas Abertos  
**Período**: 2025.1

## Estrutura do Projeto
- `Vagrantfile`: Criação das 4 VMs (arq, db, app, cli)
- `ansible/`: Automação com Ansible
  - `hosts`: inventário
  - `playbook.yml`: playbook principal
  - `chaves_publicas/`: pasta onde a chave sergio1 será gerada automaticamente
  - `roles/`: configuração das funções

## Roles e suas funções
- **common**: Atualização do sistema, timezone, criação de usuários, SSH seguro, geração automática de chave pública
- **arq**: DHCP, LVM, NFS
- **db**: MariaDB, autofs
- **app**: Apache, autofs
- **cli**: Firefox, X11, autofs

## Como executar
1. Subir as VMs:
```
vagrant up --provider=virtualbox
```
2. Acessar a pasta Ansible:
```
cd ansible
```
3. Executar o playbook (a chave será criada automaticamente se não existir):
```
ansible-playbook -i hosts playbook.yml
```

## Como acessar via SSH sem senha
Após a execução, use:
```
ssh -i ansible/chaves_publicas/sergio1 sergio1@<ip_da_vm>
```
