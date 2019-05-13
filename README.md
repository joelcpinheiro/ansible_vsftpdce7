# Instalando/Removendo VSFTPD no CentOS 7 via Ansible

Esta é uma maneira prática(pra não falar ágil, rs) de instalar o VSFTPD no CentOS 7 utilizando Ansible.

## Intruções Iniciais

Acessar o Servidor com Ansible instalado via SSH e entrar no diretório onde está o projeto(`/etc/ansible/vsftpdce7/`).

### Pré-requisitos

É muito tranquilo, basta seguir os passos abaixo :)


Permitir o acesso SSH para que o Ansible consiga efetuar a operação, enviando a chave pública do Host Ansible para Host de destino e inserir o IP ou nome do Host no playbook, os passos são:

1. Executar o comando no Servidor do Ansible `ssh-copy-id root@iphostdestino`;
2. Editar o playbook `install.yml` e no campo hosts inserir o IP ou nome do host de destino;
3. Não esqueça de inserir o IP e o nome do host de destino dentro do arquivo hosts do Ansible, em `/etc/ansible/hosts` para fazer com que o playbook funcione com sucesso.
4. Editar o arquivo presente dentro deste projeto chamado chroot_list e inserir o nome do usuário que será criado posteriormente.

**OBS**: Existe outro playbook para criar um usuário FTP, está no diretório `/etc/ansible/nuser_vsftpdce7`, basta editar o arquivo createuser.yml e ler com calma os comentários.

## Efetuando a instalação

Dentro do diretório inicial do projeto, executar o comando abaixo, logo após basta acompanhar as tarefas sendo executadas.

```sh
$ ansible-playbook install.yml
```


**OBS**: Após instalado você pode utilizar um cliente FTP para validar o acesso ao Servidor via FTP.

## Efetuando a DESinstalação

Dentro do diretório inicial do projeto, executar o comando abaixo, ele irá remover o pacote vsftpd  e o diretório `/etc/vsftpd`.

```sh
$ ansible-playbook uninstall.yml
```

## Versão

2.0.1

## Autor

* **Joel Pinheiro** - *Github* - [joelcpinheiro](https://github.com/joelcpinheiro)


## License

Use onde achar que irá contribuir :)
