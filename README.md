# 0g Chain Testnet

**0g Chain Testnet** - это скрипт для автоматического прогона транзакций в тестовой сети проекта _0G Network_

## Основные возможности
- Отправка транзакций на заранее подготовленные случайные адреса
- Полная настраиваемая рандомизация всех параметров и действий
- Вывод ссылки на транзакцию в обозревателе блоков
- Вывод логов для отслеживания работы скрипта

---

## Конфигурация
Для работы программы используется конфигурационный файл (`config.ts`) со следующими параметрами:

### Параметры:
- **`sleepBetweenAccs`**: Настройки задержки между обработкой аккаунтов
    - `isSleep`: Указывает, включена ли задержка — true | false
    - `sleepDelay`: Массив из двух чисел, задающий диапазон задержки в секундах — [от, до]

- **`sleepBetweenTransfers`**: Настройки задержки между транзакциями
    - `isSleep`: Указывает, включена ли задержка — true | false
    - `sleepDelay`: Массив из двух чисел, задающий диапазон задержки в секундах — [от, до]

- **`sleepBetweenCycle`**: Настройки задержки между циклами выполнения
    - `isSleep`: Указывает, включена ли задержка — true | false
    - `sleepDelay`: Число, задающее задержку в секундах — n секунд

- **`txCount`**: Диапазон количества транзакций, выполняемых для конкретного адреса
Значение задается массивом из двух чисел — [от, до]

- **`valueToSend`**: Диапазон суммы средств для перевода в одной транзакции
Значение задается массивом из двух чисел — [от, до]

- **`rpc`**: RPC-эндпоинт для взаимодействия с сетью

- **`scan`**: URL обозревателя блоков

---

## Установка (Docker)
### Шаг 1: Установка Git
Установите Git по официальному гайду — https://git-scm.com/downloads
```bash
git --version
```
### Шаг 2: Установка Docker
Установите Docker по официальному гайду — https://docs.docker.com/desktop/
```bash
docker --version
```

### Шаг 3: Клонирование репозитория
```bash
https://github.com/N0tAbuzer/0G-Chain-Testnet.git
cd 0G-Chain-Testnet
```

### Шаг 4: Настройка конфигурации
- Отредактируйте файл `config.ts` указав параметры, как показано выше
- Добавьте приватные ключи в файл `data/privateKeys.txt`. **ОБЯЗАТЕЛЬНО!!!**

### Шаг 5: Клейм тестовых токенов
Перейти на сайт https://faucet.0g.ai/ (Используйте VPN)

### Шаг 6: Создание Docker-образ
```bash
docker build -t 0g-chain-testnet .
```

### Шаг 7: Запуск Docker-контейнера
```bash
docker run -it --name --restart always 0g-chain-testnet n0tabuzer/0g-chain-testnet:Main
```
