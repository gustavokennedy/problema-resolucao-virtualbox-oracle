# Problema de resolução no VirtualBox Oracle com Ubuntu Server
Resolução do problema de resolução com VirtualBox em Ubuntu Server 22.04.2.

Quando criamos ou restauramos uma nova máquina no VirtualBox e instalamos um sistema operacional, o VirtualBox define uma resolução de tela padrão. No entanto, ao trabalhar em uma máquina virtual, geralmente precisamos ter uma resolução de tela de nossa escolha, até mesmo para identificar o IP e conectar por SSH futuramente, as vezes nem mesmo isso é possível por causa da resolução da tela.

## Alterando resolução VirtualBox no Ubuntu Server 22.04.2

Passos:

### 1. Instalar alguns pacotes necessários para a instalação do Guest Addition Image:

```shell
sudo apt install build-essential dkms linux-headers-$ ( uname -r )
```

### 2. Clique em “Dispositivos” na barra de menu da máquina virtual e selecione “Inserir imagem de CD de adição de convidado” no menu “Dispositivos”:

![image](https://user-images.githubusercontent.com/98914036/231027669-62bd90c4-57a6-4c33-b3f8-37c8814b3e34.png)

A instalação será concluída em alguns instantes.

Depois de concluído, ele solicitará a reinicialização do sistema.

### 3. Inserir imagem de CD de adição de convidado manualmente:

```shell
sudo mkdir -p /mnt/cdrom
sudo mount/dev/cdrom /mnt/cdrom
cd /mnt/cdrom
sudo sh./VBoxLinuxAdditions.run --nox11
```

![image](https://user-images.githubusercontent.com/98914036/231027956-f436cef9-13f3-4275-8b6b-a041ca4ebab6.png)

### 4. Reinicie e teste:

```shell
sudo shutdown -r now
```
