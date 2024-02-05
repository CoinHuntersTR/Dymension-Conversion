<h1 align="center"> Dymension Conversion

# Privatekey ile ödül gelen adresine ulaşamayan ve ödülünü oradan yeni cüzdanına transfer etmek için aşağıdaki adımları yapmamız gerekiyor.


## Eski Rollapp Kurulu olmayan ve sadece Private Key'i olanlar.

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

## Ubuntu 20 veya başka sürüm

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

## Her iki UBUNTU sürümü için aşağıdaki adımlar aynı;

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

## Bu adımdan sonrası MAINNET için devam edecek.

* Buradaki değeri kendi ödülünüze göre ayarlayın. Gönderim için içinde biraz gas fee bırakın.
* Önce denemek için 1 adet yollayın her şey yolunda ise kalanı gönderirsiniz.
* Tam sayıdan sonra 18 tane 0 var.
```
1 DYM = 1000000000000000000adym
```
* Ulaşabildiğiniz bir DYM adresi edinin. İster Keplrda yeni bir adres açın, yada rollape için kullandığınız adresi verin. Size kalmış.
* Tırnakların içine dym adresinizi ekleyin.
```
NEW_ADDRESS="dym1.....123acb123abc123abc123abc"
```
### Coin Transferi

* Bu transfer 1 DYM için hazırlanmış.
* Deneme sonrası başarılı oldu ise, kendi ödül miktarınıza göre yeniden miktarı yazın.
```
dymd tx bank send wallet $NEW_ADDRESS 1000000000000000000adym --keyring-backend test --node https://rpc-dymension.mzonder.com:443 --chain-id dymension_1100-1 --gas-prices 20000000000adym --gas 200000
```


# NOT: Halihazırda ilk rollapp'i kurulu olan ve hala çalışanlar "Conventor Yüklüyoruz" adımından itibaren yapabilirler. Kendi Ubuntu versiyonunuza göre devam edersiniz. 

Dokümanın orjinaline [BURADAN](https://mzonder.notion.site/DYMENSION-Rollapp-wallet-conversion-e8919a9e70ba4379ac196e166f9bb83a) ulaşabilirsiniz. 
