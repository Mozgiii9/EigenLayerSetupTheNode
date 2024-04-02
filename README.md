![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/8ae1bf29-8954-402a-bef7-790f49064302)


## Дата создания файла: 02.04.2024

## Разбор проекта:

*Рестейкинг* — новейший и стремительно развивающийся тренд в децентрализованных финансах. **В основе этой индустрии объемом $8 млрд лежит проект EigenLayer.** Как результат, появились десятки проектов и новых категорий, таких как ликвидный рестейкинг и LRTfi. Сейчас же, в самый разгар сезона аирдропов, EigenLayer и входящие в его экосистему проекты имеют все шансы стать крупнейшими и самыми важными аирдропами в 2024 году!

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/a960910a-4121-4bfc-94fb-a3325ae36d4f)

Рестейкинг очень быстро занял свое место в десятке лучших DeFi категорий. И хотя он по-прежнему составляет небольшую долю от TVL Ethereum, почти одна пятая часть TVL ликвидного стейкинга в сети Ethereum приходится именно на этот протокол. Весьма солидно, не так ли?

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/8431d2a2-564f-4efb-8051-aac025a38406)

## Инвестиции в проект:

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/0d3aaf50-c5a2-4539-92e3-633d664f36a0)


![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/6dc7fcdf-87ab-47cc-bf74-36c71242a67d)

**Проект оценивается в 500 млн. долларов. Интересные инвесторы у проекта, интересная технология. Проект поддерживает сам Виталик Бутерин!**

## Социальные сети EigenLayer:

- [Веб-сайт](https://www.eigenlayer.xyz/)
- [Whitepaper](https://docs.eigenlayer.xyz/eigenlayer/overview/whitepaper)
- [Docs](https://docs.eigenlayer.xyz/eigenlayer/overview)
- [Twitter](https://twitter.com/eigenlayer)
- [Discord](https://discord.com/invite/eigenlayer)

## Как поставить ноду?

Первое, самое основное - **аренда сервера.** EigenLayer разделили ноды на два типа - **Operator и AVS.** Мы будем ставить ноду типа **Operator**, поскольку для ноды типа AVS нужны вложения в районе 10.000$ + это нода валидатор.

Требования к ноде (Рекомендуемые лично мной, такая нода будет работать корректно): **6 CPU cores 16 GB RAM 500GB SSD 25MBps Internet Ubuntu 20.04.**

Вы можете также взять в аренду сервер с минимальными характеристиками, но такая нода будет иметь меньший приоритет. Ознакомиться с требованиями к серверу на картинке ниже:

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/e35f0061-f118-4003-98e4-728c3c2f099a)

**DYOR!**

### Перейдем к настройке сервера:

**1. Обновим содержимое сервера, для этого выполним команду:**

```
sudo apt update && sudo apt upgrade -y
```

**2. Установим нужный софт:**

```
apt install curl iptables build-essential git wget jq make gcc nano tmux htop nvme-cli pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev -y
```

**3. Установим Docker:**

```
sudo apt install docker.io
```

**4. Проверим установку Docker'а и узнаем его версию:**

```
docker --version
```

**5. Продолжим установку. Теперь установим Docker Compose. Выполните команды:**

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```
sudo chmod +x /usr/local/bin/docker-compose
```

```
docker-compose --version
```

**6. У Вас должен был установиться Docker Compose. Теперь перейдем к установке языка программирования Go (Golang). Выполните команды последовательно:**

```
wget https://golang.org/dl/go1.21.4.linux-amd64.tar.gz
```

```
tar -C /usr/local -xzf go1.21.4.linux-amd64.tar.gz
```

```
export PATH=$PATH:/usr/local/go/bin
```

```
go version
```

**7. На данный момент весь необходимый софт для работы с нодой EigenLayer установлен. Давайте перейдем к установке клиента самой ноды. Выполните команды:**

```
git clone https://github.com/Layr-Labs/eigenlayer-cli.git
```

```
cd eigenlayer-cli
```

```
mkdir -p build
```

```
go build -o build/eigenlayer cmd/eigenlayer/main.go
```

```
cp ./build/eigenlayer /usr/local/bin/
```

```
eigenlayer
```

**Если Вы все выполнили верно, то у Вас должна отобразиться такая картина:**

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/bc357cf9-39aa-4652-bf79-a0886ab3a382)

Вы можете генерировать закрытые ключи с шифрованием ECDSA и BLS с помощью интерфейса командной строки (CLI). ECDSA и BLS - два широко используемых алгоритма в протоколах безопасности и в блокчейне для обеспечения целостности и конфиденциальности данных.

**8. Оба ключа понадобятся для регистрации оператора и других операций на цепочке. Замените <YOUR_NAME> на имя, которое вы хотите присвоить своим ключам:**

```
eigenlayer operator keys create --key-type ecdsa <YOUR_NAME>
```

**Придумайте пароль. Сохраните данные в надежное место, которые получили. Чтобы выйти из данного меню нажмите комбинацию клавиш CTRL+C.**

```
eigenlayer operator keys create --key-type bls <YOUR_NAME>
```

**Так же придумайте пароль. Сохраните данные в надежное место, которые получили. тобы выйти из данного меню нажмите комбинацию клавиш CTRL+C.**

После создания пароля для вашего ключа вы увидите приватный ключ и адрес вашего кошелька. **Храните свой приватный ключ в надежном месте, так как в дальнейшем вы не сможете получить к нему доступ.**

**9. Если вам нужно получить свои открытые ключи и адрес кошелька выполните команду:**

```
eigenlayer operator keys list
```

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/49b0a888-9743-4086-bb76-492bbbbad201)

### Супер, перейдем к регистрации ноды. 

**10. Создадим конфиг ноды командой:**

```
eigenlayer operator config create
```

### ВНИМАТЕЛЬНО!!! ДАЛЕЕ НАЖИМАЕМ N (NO)! ЕСЛИ ВЫ СТАВИЛИ НОДУ ВМЕСТЕ СО МНОЙ НА ЭФИРЕ И НАЖИМАЛИ НА ДАННОМ ЭТАПЕ Y (YES) - НИЧЕГО СТРАШНОГО! СЕЙЧАС Я ПРОСТО РАСПИСЫВАЮ ИНОЙ ПУТЬ УСТАНОВКИ, КОТОРЫЙ ТОЖЕ ПРОБОВАЛ!

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/37ab15e6-abc9-4968-bab2-4d74fcb79888)

### Сейчас перейдем к отдельному этапу, который посвящен созданию и редактированию файла "metadata.json". Для этого нам понадобится профиль Github. В данный момент Вы можете скрыть окно со своей нодой, чуть позже мы к нему вернемся.

**11. Итак, заходим в свой профиль Github. Далее нам необходимо создать новый репозиторий. Сделать это можно нажав на кнопку "+" в правом верхнем углу, после чего нажав на кнопку "New repository".**

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/7d21bf8f-230f-476e-af52-4612c0a50ee7)

**12. Отлично, теперь нужно задать имя репозиторию. Я назвал свой репозиторий "metadata.json", Вы же можете использовать любое другое имя. Это не играет никакой роли при установке ноды. Пример названия репозитория также есть на скрине:**
![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/7571c808-9417-43e2-9684-7839ee92731c)

Оставляем репозиторий публичным, файл README.md добавлять не стоит. Укажите настройки как на скрине выше. После того, как указали имя репозитория и сверили его параметры, нажмите на кнопку **"Create repository".**

**13. Перейдем к следующему шагу, а именно к созданию файла "metadata.json". Для этого нажмите на кнопку "creating new file".**
![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/aa8fba69-9dbd-4777-b40c-900f18378aa2)

**Назовите Ваш файл "metadata.json". Далее, вставьте в него текст:**

```
{
  "name": "<YOUR_OPERATOR_NAME>",
  "website": "<YOUR_WEBSITE>",
  "description": "<RANDOM_DESCRIPTION>",
  "logo": "<URL_OF_YOUR_LOGO>",
  "twitter": "<YOUR_TWITTER>"
}
```

### Пожалуйста, отнеситесь к данному этапу внимательно и ответственно, от этого зависит судьба Вашей ноды. Давайте подробно пройдемся по пункту из файла "metadata.json":

- "name" : Имя Вашей ноды. Ставьте его по своему усмотрению, главное, чтобы имя ноды содержало исключительно английские символы. Не используйте нестандартных решений.
- "website" : В качестве веб-сайта Вы можете использовать ссылку на свой Github профиль.
- "description" : Задайте описание Вашей ноды. Так же не используйте нестандартных решений.
- "logo" : Серьезный пункт. В данное поле сохраните ссылку **ИСКЛЮЧИТЕЛЬНО** на .png  картинку. Другие форматы изображений ПО EigenLayer не поддерживает и Ваша нода не запустится! Что в данном пункте вставил я? Я добавил в свой репозиторий на .png изображение, после чего прикрепил в данном поле RAW ссылку на него. Пример своего файла "metadata.json" я прикреплю ниже.
- "twitter" : Добавьте ссылку на свой Twitter профиль.

### Как выглядит мой файл "metadata.json":

```
{
  "name": "M0zgiiiNode",
  "website": "https://github.com/Mozgiii9",
  "description": "Hello it is M0zgiii and there is my EigenLayer Node. Nice 2 meet u!",
  "logo": "https://raw.githubusercontent.com/Mozgiii9/metadata.json/main/d5fe81c42b515cdc.png",
  "twitter": "https://twitter.com/m0zgiii"
}
```

**Обратите внимание на кавычки!**

**14. После того, как Вы корректно добавили собственные данные, нажмите кнопку "Commit changes..." в правом углу:**

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/bb2274e5-b789-4102-989c-e45f3b53ef54)

**15. Вернемся к нашему серверу. Отредактируем файл "metadata.json", который находится на сервере. Для этого введите команду:**

```
nano metadata.json
```

И заполните файл "metadata.json" данными, которые Вы вводили в Github. 

**16. Прекрасно, теперь перейдем к редактированию файла operator.yaml. Так же внимательно и ответственно отнеситесь к редактированию данного файла. Выполните команду:**

```
nano operator.yaml
```

**У Вас откроется файл:**

```
operator:
    address: <ECDSA_ADRESS>
    earnings_receiver_address: <ECDSA_ADRESS>
    delegation_approver_address: "0x0000000000000000000000000000000000000000"
    staker_opt_out_window_blocks: 0
    metadata_url: <RAW_URL>
el_delegation_manager_address: 0x1b7b8F6b258f95Cf9596EabB9aa18B62940Eb0a8
eth_rpc_url: https://rpc.ankr.com/eth_goerli
private_key_store_path: /root/.eigenlayer/operator_keys/<KEY_NAME>.ecdsa.key.json
signer_type: local_keystore
chain_id: 5
```

**Давйте пройдемся по полям:**
- address : Замените на Ваш ECDSA адрес.
- earnings_reciever_address : Замените на Ваш ECDSA адрес.
- delegation_approver_address : Оставьте по умолчанию.
- staker_opt_out_window_blocks : Оставьте по умолчанию.
- metadata_url : Вставьте RAW ссылку на Ваш файл "metadata.json", который хранится в Вашем репозитории на Github. Для того, чтобы вставить RAW ссылку, нажмите на кнопку "RAW". На скрине ниже все подробно показано.
- el_delegation_manager_address : Вставьте значение 0x1b7b8F6b258f95Cf9596EabB9aa18B62940Eb0a8
- eth_rpc_url : Вставьте значение https://rpc.ankr.com/eth_goerli
- private_key_store_path : Укажите имя Вашего ключа вместо <KEY_NAME>.
- signer_type : Оставьте local_keystore.
- chain_id : 17000.

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/0cd82b8d-cff7-4735-be24-f8430f5c50ee)

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/eb53258a-11f9-4470-84e0-e8d9d0d21fae)

**После того, как Вы отредактировали файл "operator.yaml", нажмите комбинацию клавиш CTRL+X, затем Y и Enter для сохранения файла.**

**Прежде чем продолжить, нам необходимо пополнить кошелек тестовыми токенами Holesky. Это необходимо для обеспечения работы ноды.**

**17. Чтобы это сделать, перейдите в [данный кран](https://stakely.io/en/faucet/ethereum-holesky-testnet-eth), вставьте Ваш ECDSA адрес и получите токены. Вам понадобится сделать ретвит, чтобы получить свой 1 ETH Holesky.**

*Вы можете использовать любой другой кран для получения Ethereum Holesky. DYOR.*
![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/f6dadc0f-3eb1-45f2-a8f0-cdf17d881366)

**18. Проверить транзакцию Вы можете при помощи [эксплорера Holesky](https://holesky.etherscan.io/) вбив в поисковой строке ECDSA адрес кошелька Вашей ноды EigenLayer.**

### Финишная прямая. Вводим команду регистрации ноды:

```
eigenlayer operator register operator.yaml
```

**Подтверждаем регистрацию паролем. Если все прошло без ошибок - я Вас поздравляю, Вы успешно зарегистрировали ноду EigenLayer!**

**19. Теперь давайте проверим статус ноды. Выполним команду:**

```
eigenlayer operator status operator.yaml
```

**Вы должны получить вот такой вывод:**

![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/366b41ee-7f68-4149-a395-cbb2e5051050)

Проверьте свою ноду в [эксплорере EigenLayer](holesky.eigenlayer.xyz):
![image](https://github.com/Mozgiii9/EigenLayerSetupTheNode/assets/74683169/a075e9ed-61c6-4da5-9646-8dfd6e475bde)

### У МЕНЯ ВОЗНИКЛА ОШИБКА ПРИ УСТАНОВКЕ, ЧТО МНЕ ДЕЛАТЬ???

Первое и самое основное - не паниковать. Внимательно перепроверьте данные конфига ноды, перепроверьте файл "metadata.json". Внимательно перепроверьте каждый пункт и каждый символ, вполне возможно, что где-то Вы забыли добавить кавычку или наоборот поставили лишнюю.

Второе. Вы не нашли ошибку, а Ваша нода все равно не работает. В данном случае стоит подождать пару часов и попробовать установить ноду еще раз. С вероятностью 80% у Вас получится ее установить.

Третье. Использовать открытые ресурсы, такие как Google, Яндекс и ChatGPT. Последний из этого списка станет Вашим верным товарищем в освоении серверной стихии.

Четвертое. Написать в общий чат NodeRunner. Там Вам 100% помогут.

### Помните, не бывает нерешаемых проблем. С первого взгляда ноды это что-то чоень сложное и за гранью фантастики, но это только на первый взгляд. Здесь нет ничего сложного.

## Давайте подведем выводы по проекту EigenLayer:

- Интересная задумка. которая привлекает средства;
- Мощный инвест, фонды и поддержка от Бутерина;
- Официально токен не подтвержден, но вспомните сколько проектов "без токена" раздали людям деньги.
- Поддержка сообщества;
- Большая экосистема.

### Обязательно проведите собственный ресерч проектов перед тем как ставить ноду. Сообщество NodeRunner не несет ответственность за Ваши действия и средства. Помните, проводя свой ресёрч, Вы учитесь и развиваетесь.

### Связь со мной: [Telegram(@M0zgiii)](https://t.me/m0zgiii)

### Мои соц. сети: [Twitter](https://twitter.com/m0zgiii) 


















