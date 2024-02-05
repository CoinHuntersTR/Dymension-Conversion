<h1 align="center"> Dymension Private Key Farklı olanlar
  


# Eski Rollapp Kurulu olmayan ve sadece Private Key'i olanlar.

## Aşağıdaki kurulumlardan birini tercih edebilirsiniz.

## UBUNTU 22
```
sudo apt-get update -y && sudo apt-get upgrade -y
```
### Gerekli Kütüphaneleri ekliyoruz.

```
sudo apt install curl tar wget clang pkg-config libssl-dev jq build-essential bsdmainutils git make ncdu gcc git jq chrony liblz4-tool -y
```

```
curl -L https://dymensionxyz.github.io/roller/install.sh | bash
```
### Converter Yüklüyoruz

```
cd $HOME
```
```
git clone https://github.com/alphab-ai/pk_convert
```

#### Ubuntu 20 veya başka sürüm

```
sudo apt-get update -y && sudo apt-get upgrade -y
```
### Gerekli Kütüphaneleri ekliyoruz.

```
sudo apt install curl tar wget clang pkg-config libssl-dev jq build-essential bsdmainutils git make ncdu gcc git jq chrony liblz4-tool -y
```

```
curl -L https://dymensionxyz.github.io/roller/install.sh | bash
```
### Converter Yüklüyoruz

```
cd $HOME
ver="1.21.3"
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz"
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz"
rm "go$ver.linux-amd64.tar.gz"
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile
source $HOME/.bash_profile
```
```
cd $HOME
```
```
git clone https://github.com/alphab-ai/pk_convert
```
```
cd pk_convert
```
```
go build -o pk_convert ./main.go
```
### Privatekey'imizi Convert ediyoruz.
* Tırnak içine elimizde olan privekeyimizi giriyoruz.

```
HUB_SEQUENCER_PK="your_privatekey"
```

* Tırnakların içine herhangi bir şifre girebilirsiniz.
```
PASSWORD="12345678" 
```
### Json dosyası oluşturulım

*Aşağıdaki komutu girdiğinizde sizden şifre isteyecek. Yukarıda verdiğiniz şifreyi girmeniz gerekiyor.

```
dymd keys import wallet $HOME/new_pk.json --keyring-backend test
```
* Dikkat aşağıdaki komutu girdiğinizde ödül gelen ve private key ile ulaşamadığınız cüzdanı size vermiş olması gerekiyor.
```
dymd keys list --keyring-backend test
```



