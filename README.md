# postgres
Ansible playbooks para gerenciar e alterar bancos de dados postgres

## setup_integracao
Cria usuário, banco de dados, schema, oracle_fdw, foreign server e user mapping no postgres para que seja possível conectar à um banco de dados oracle

### Variáveis
- oracle_host
- oracle_porta
- oracle_service_name
- oracle_usuario
- oracle_senha
- postgres_usuario
- postgres_senha

### Utilização

Chame o playbook passando as variáveis pelo argumento `--extra-vars` como no exemplo abaixo:

```console
root@ansible:~$ ansible-playbook setup_integracao.yaml --extra-vars "oracle_host=10.10.10.10 oracle_porta=1521 oracle_service_name=teste oracle_usuario=usuario_integracao oracle_senha=blablabla postgres_usuario=teste_ansible postgres_senha=senha_usuario_postgres"
```

Ou crie um arquivo `vars.yaml` com as variáveis e passe o arquivo no argumento `--extra-vars` como no exemplo abaixo:

```yaml
---
oracle_host: 10.10.10.10
oracle_porta: 1521
oracle_service_name: teste
oracle_usuario: usuario_integracao
oracle_senha: blablabla
postgres_usuario: teste_ansible
postgres_senha: senha_usuario_postgres
```

```console
root@ansible:~$ ansible-playbook setup_integracao.yaml --extra-vars @vars.yaml
```
