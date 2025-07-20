# Projeto 01 - DevOps com Vagrant e Ansible Automático

**Aluno**: Sérgio Henrique da Silva  
**Disciplina**: Administração de Sistemas Abertos 
**Professor**: Leônidas Lima
**Período**: 2025.1

## Como executar
1. Subir todas as VMs e provisionar automaticamente:
```
vagrant up --provider=virtualbox
```

## Roles aplicadas

- **common**: Atualiza o sistema, cria usuário, gera chave SSH
- **arq**: DHCP, LVM, NFS
- **db**: MariaDB, autofs
- **app**: Apache, autofs
- **cli**: Firefox, autofs

## Acesso SSH
```
ssh -i ansible/chaves_publicas/sergio1 sergio1@192.168.56.245
```
