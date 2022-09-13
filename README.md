# Subspace-docker

максимальный размер под плот ограничили в 100гб, можно меньше, но не больше

```sh
SUBSPACE_WALLET_ADDRESS="адрес кошелька Polkadot для ревардов"
SUBSPACE_NODE_NAME="имя ноды"
SUBSPACE_PLOT_SIZE="100G"
```
Сохраняем переменные

```sh
echo 'export SUBSPACE_WALLET_ADDRESS='$SUBSPACE_WALLET_ADDRESS >> $HOME/.bash_profile
echo 'export SUBSPACE_NODE_NAME="'${SUBSPACE_NODE_NAME}'"' >> $HOME/.bash_profile
echo 'export SUBSPACE_PLOT_SIZE='$SUBSPACE_PLOT_SIZE >> $HOME/.bash_profile
source $HOME/.bash_profile
```
загружаем конфиг на сервер с докером

```sh
mkdir subspace && cd subspace
wget -qO - https://github.com/starnodes/Subspace-docker/raw/main/docker-compose.yml | envsubst > docker-compose.yml
```

запуск: docker-compose up -d

остановка: docker-compose down

удаление:

```sh
cd $HOME/subspace
docker-compose down -v
cd $HOME && rm -rf $HOME/subspace/
```
