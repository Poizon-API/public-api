### Как интегрировать сервис poizon-api к себе в приложение ?


## Шаг 1: Создание аккаунта и получение API ключа

1. **Создайте аккаунт на сайте Poizon-API:**
   - Перейдите на [Poizon-API](https://poizon-api.com/) и зарегистрируйтесь.
   
2. **Сгенерируйте API ключ:**
   - Войдите в свой аккаунт и сгенерируйте API ключ, который будет использоваться для аутентификации в API запросах.

## Шаг 2: Установка Node.js

Если у вас еще не установлена Node.js, выполните следующие шаги:

1. Перейдите на [официальную страницу Node.js](https://nodejs.org/) и скачайте последнюю LTS версию для вашей ОС.
2. Установите Node.js, следуя инструкциям инсталлятора.

Проверьте установку, выполнив команду:
sh
node -v
npm -v
## Шаг 3: Настройка проекта

1. **Выберите нужный генератор в файле openapitools.json:**

Замените "generatorName": "php" на тот язык, который вам нужен. Список доступных языков генерации можете найти на [официальной странице генераторов](https://openapi-generator.tech/docs/generators/).

## Шаг 4: Установка зависимостей

1. **Установите нужные зависимости:**

sh
npm install
2. **Сгенерируйте клиент для API:**

sh
npm run generate:openapi
Этот шаг создаст директорию generated-client, содержащую сгенерированный клиентский код для вышеуказанного языка.

## Шаг 5: Использование сгенерированного кода

1. **Импортируйте сгенерированный код в ваш проект.**

   *Пример для Node.js:*

js
const PoizonApi = require('./generated-client');
2. **Используйте клиент для отправки запросов.**

### Пример использования API-клиента
```js
const {ProductsApi} = import('./openapi');

const PRODUCT_CONFIGURATION = new Configuration({
  apiKey: "Ваш апи ключ",
});

const productApi = new ProductsApi(PRODUCT_CONFIGURATION),

productApi.someApiCall(params)
    .then((data) => {
        console.log('API response:', data);
    })
    .catch((error) => {
        console.error('API call error:', error);
    });
   ``` 
## Ошибки и Отладка

1. **Проверьте консоль на наличие ошибок.**
   - Убедитесь, что ваш API ключ действителен и правильный.
   - Проверьте URL запросов и параметры.

2. **Справка по методу:**
   - Смотрите документацию на [Poizon-API](https://poizon-api.com/lk/api-docs) для детальной информации о каждом методе и параметрах.
