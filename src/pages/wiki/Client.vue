<template>
  <q-page padding>
    <doc-header name="compatibility">Совместимость</doc-header>
    <p>
      На текущий момент поддерживается запуск:
    </p>
    <ul>
      <li>Любой Vanilla версии с 1.7.10 до 1.18.1</li>
      <li>Любой Forge версии с 1.7.10 до 1.16.5</li>
      <li>Любой Fabric версии с 1.13 до 1.18.1</li>
    </ul>
    <doc-header name="downloadclient">Скачивание клиента с зеркала</doc-header>
    <p>Список клиентов, доступных на зеркале можно посмотреть тут: <a href='https://mirror.gravit.pro/clients/'>клиенты</a> и <a href='https://mirror.gravit.pro/assets/'>ассеты</a></p>
    <p>Выполните команду <q-badge>downloadclient ВЕРСИЯ НАЗВАНИЕ</q-badge> для скачки клиента</p>
    <p>Выполните команду <q-badge>downloadasset ВЕРСИЯ НАЗВАНИЕ</q-badge> для скачки ассетов</p>
    <p>Примечания:</p>
    <ul>
      <li>Для скачки клиента с стороннего зеркала вместе с профилем вам нужно использовать такую команду: <q-badge>downloadclient ВЕРСИЯ НАЗВАНИЕ mirror</q-badge></li>
      <li>Название папки ассетов как правило записывается в виде <q-badge>assetВЕРСИЯ</q-badge>, например: <b>asset1.7.10</b>, <b>asset1.17.1</b></li>
      <li>Версии клиента 1.12.2 и ниже включают в себя Forge по умолчанию</li>
    </ul>
    <doc-header name="authlib1">Сборка Authlib (MineCraft до 1.16.4)</doc-header>
    <p>
      Для сборки Authlib следуйте инструкции:
    </p>
    <ul>
      <li>Скопируйте файл <a href='https://github.com/GravitLauncher/Launcher/blob/master/compat/authlib/authlib-clean.jar'>authlib-clean</a> в папку libraries вашего клиента</li>
      <li>Скопируйте из артефактов сборки файл LauncherAuthlib в папку libraries вашего клиента</li>
    </ul>
    <doc-header name="authlib2">Сборка Authlib (MineCraft с 1.16.5-1.17.1)</doc-header>
    <p>
      Для сборки Authlib следуйте инструкции:
    </p>
    <q-tabs v-model='authlib2Select'>
        <q-tab name='rename' label='Переименование' />
        <q-tab name='build' label='Сборка' />
    </q-tabs>
    <q-separator />
    <q-tab-panels v-model='authlib2Select'>
        <q-tab-panel name='rename'>
          <ul>
            <li>Скачайте файл <a href='https://mirror.gravit.pro/compat/authlib/2/LauncherAuthlib2-5.2.0.jar'>LauncherAuthlib</a></li>
            <li>Переименуйте его в "0-launcher-authlib.jar" и скопируйте его в папку "libraries/com/mojang/authlib/ВЕРСИЯ/" вашего клиента</li>
          </ul>
        </q-tab-panel>
        <q-tab-panel name='build'>
          <ul>
            <li>Скачайте файл <a href='https://mirror.gravit.pro/compat/authlib/2/LauncherAuthlib2-5.2.0.jar'>LauncherAuthlib</a></li>
            <li>Откройте его архиватором и распакуйте папку com в отдельную папку</li>
            <li>Откройте вашу authlib по пути "libraries/com/mojang/authlib/ВЕРСИЯ/" архиватором и вставьте с заменой файлы, распакованные на предыдущем этапе</li>
          </ul>
        </q-tab-panel>
    </q-tab-panels>
    <doc-header name="authlib3">Сборка Authlib (MineCraft с 1.18 и выше)</doc-header>
    <p>
      Для сборки Authlib следуйте инструкции:
    </p>
    <q-tabs v-model='authlib3Select'>
        <q-tab name='rename' label='Переименование' />
        <q-tab name='build' label='Сборка' />
    </q-tabs>
    <q-separator />
    <q-tab-panels v-model='authlib3Select'>
        <q-tab-panel name='rename'>
          <ul>
            <li>Скачайте файл <a href='https://mirror.gravit.pro/compat/authlib/3/LauncherAuthlib3.jar'>LauncherAuthlib</a></li>
            <li>Переименуйте его в "0-launcher-authlib.jar" и скопируйте его в папку "libraries/com/mojang/authlib/ВЕРСИЯ/" вашего клиента</li>
          </ul>
        </q-tab-panel>
        <q-tab-panel name='build'>
          <ul>
            <li>Скачайте файл <a href='https://mirror.gravit.pro/compat/authlib/3/LauncherAuthlib3.jar'>LauncherAuthlib</a></li>
            <li>Откройте его архиватором и распакуйте папку com в отдельную папку</li>
            <li>Откройте вашу authlib по пути "libraries/com/mojang/authlib/ВЕРСИЯ/" архиватором и вставьте с заменой файлы, распакованные на предыдущем этапе</li>
          </ul>
        </q-tab-panel>
    </q-tab-panels>
    <doc-header name="profile">Настройка профиля</doc-header>
    <p>
      Список параметров профиля с пояснениями:
    </p>
    <doc-code code='
{
  "title": "Vanilla1.17", // Заголовок профиля
  "uuid": "fa9c1a52-6fa9-4da6-a488-9fc80250095c", // UUID профиля (profileUUID)
  "version": "1.17", // Версия майнкрафта
  "info": "Информация о сервере", // Информация о сервере в окне выбора серверов
  "dir": "Vanilla1.17", // Папка клиента в updates
  "sortIndex": 0, // Порядковый номер в окне выбора серверов
  "assetIndex": "1.17", // Название используемого индекса в ассетах
  "assetDir": "asset1.17", // Папка с ассетами
  "update": [ // Список файлов и папок, которые будут перекачиваться при старте клиента
    "servers.dat"
  ],
  "updateExclusions": [], // Список файлов и папок, которые не надо проверять
  "updateVerify": [ // Список файлов и папок, которые будут перекачиваться при старте клиента и  во время работы
    "libraries",
    "natives",
    "minecraft.jar",
    "forge.jar",
    "liteloader.jar",
    "mods"
  ],
  "updateOptional": [], // Список опциональных модов и дополнительных аргументов
  "jvmArgs": [ // Аргументы JVM
    "-XX:+DisableAttachMechanism",
    "-XX:+UseG1GC",
    "-XX:+UnlockExperimentalVMOptions",
    "-XX:G1NewSizePercent\u003d20",
    "-XX:MaxGCPauseMillis\u003d50",
    "-XX:G1HeapRegionSize\u003d32M",
    "-Djava.library.path\u003dnatives",
    "-Dfml.ignorePatchDiscrepancies\u003dtrue",
    "-Dfml.ignoreInvalidMinecraftCertificates\u003dtrue"
  ],
  "classPath": [ // Список файлов и библиотек, загружаемых при запуске выбранным загрузчиком классов
    "libraries",
    "minecraft.jar",
    "forge.jar",
    "liteloader.jar"
  ],
  "altClassPath": [], // Список файлов и библиотек, загружаемых при запуске системным загрузчиком классов
  "clientArgs": [], // Дополнительные аргументы клиента
  "compatClasses": [], // Список дополнительных MainClass, которые будут запущены перед основным
  "properties": {}, // Кастомная информация о профиле
  "servers": [ // Список серверов
    {
      "name": "Vanilla1.17", // Название (serverName)
      "serverAddress": "localhost", // Адрес сервера
      "serverPort": 25535, // Порт сервера
      "isDefault": true, // По умолчанию
      "socketPing": true // Прямой пинг для получения онлайна
    }
  ],
  "classLoaderConfig": "LAUNCHER", // Тип загрузчика классов (LAUNCHER, AGENT, SYSTEM_ARGS)
  "runtimeInClientConfig": "NONE", // Запуск GUI рантайма при старте клиента (NONE, BASIC, FULL)
  "recommendJavaVersion": 16, // Рекомендуемая версия Java
  "minJavaVersion": 16, // Минимальная версия Java
  "maxJavaVersion": 999, // Максимальная версия Java
  "warnMissJavaVersion": true, // Предупреждение о несоответствии Java требованиям для запуска
  "settings": { // Настройки по умолчанию
    "ram": 0, // Количество ОЗУ (в мегабайтах), 0 - автоматически
    "autoEnter": false, //Авто—вход, может крашиться
    "fullScreen": false // Полноэкранный режим
  },
  "updateFastCheck": true, // Быстрая проверка файлов
  "limited": false, // Ограничен permissions
  "mainClass": "net.minecraft.client.main.Main" // MainClass клиента
}
    ' />
    <p>
      Примечания:
    </p>
    <ul>
      <li><q-badge>limited</q-badge> так-же должен быть <q-badge>true</q-badge>, для работы <q-badge>profileWhitelist</q-badge></li>
    </ul>
    <doc-header name="optionals">Опциональные моды</doc-header>
    <doc-code code='"updateOptional": [
    {
       "actions": [ //Список действий опционального мода
        { //Первое действие
          "files": {
            "mods/1.7.10/NotEnoughItems-1.7.10-1.0.5.118-universal.jar": "", //Простое добавление файла без переименований
            "mods/SuperStrangeMod0.jar": "mods/SuperStrangeMod.jar", //Добавление файла с перемещением. на стороне лаунчсервера файл находится по пути "mods/SuperStrangeMod0.jar", а в клиент он попадет сюда "mods/SuperStrangeMod.jar"
            "mods2/LowStrangeMod.jar": "mods/LowStrangeMod.jar", //Между папками перемещение тоже работает
            "config2/ic2": "config/ic2" //Перемещение папок тоже работает
          },
          "type": "file" //Тип действия - обработка файлов
        }
      ],
       "info": "Мод, показывающий рецепты", //Описание
       "visible": true, //Видимость
       "mark": true, //Включен по умолчанию
       "limited": false, //Ограничен permissions
       "permissions": 0, //Маска привилегий. 0 - мод для всех, 1 - только для админов.
       "name": "NotEnoughItems" //Имя
    },
    {
       "actions": [
        {
          "files": {
            "mods/Waila_1.5.10_1.7.10.jar": ""
          },
          "type": "file"
        }
      ],
       "info": "Мод, показывающий дополнительную информацию при наведении на блок",
       "name": "Walia",
       "permissions": 0,
       "visible": true,
       "dependenciesFile": [{"name":"NotEnoughItems"/* Имя зависимого мода */}],
       "conflictFile": [{"name":"ClientFixer"/* Имя конфликтующего мода */}],
       "subTreeLevel": 2  //Смещение относительно первого мода. Используется для создания визуального отображения дерева зависимостей
    },
    {
       "actions": [
         {
           "args": [
             "--add-modules",
             "jdk.unsupported"
           ],
           "type": "jvmArgs"
         }
       ],
       "triggers": [], //Триггеры, о них ниже
       "info": "Аргументы Java 9+",
       "visible": false,
       "permissions": 0,
       "name": "Java9Args"
    },
    {
       "actions": [
        {
          "files": {
            "mods/1.7.10/OptiFine_1.7.10_HD_U_E7.jar": ""
          },
          "type": "file"
        }
      ],
       "info": "Улучшение производительности",
       "permissions": 0,
       "visible": true,
       "name": "OptiFine HD"
    }
  ],'/>
  <p>Триггеры - возможность включать опциональный мод при выполнении некоторых условий</p>
  <ul>
    <li><doc-code header='Тип os' code='"triggersList": [
{
  "os": "MACOSX", // ОС: LINUX, MUSTDIE (Это Windows), MACOSX
  "required": false,
  "inverted": false,
  "type": "os"
}
],' /></li>
    <li><doc-code header='Тип java' code='"triggersList": [
{
    "type": "java",
    "minVersion": 8, //Минимальная версия Java для срабатывания триггера
    "maxVersion": 11, //Максимальная версия Java для срабатывания триггера
    "required": true, //Показывает, что без этого триггера включение опционального мода не имеет смысла
    "inverted": false //Инвертировать триггер
  }
],' /></li>
  </ul>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
export default defineComponent({
  name: "PageClient",
  data: function () {
    return {
      authlib2Select: "rename",
      authlib3Select: "rename",
    };
  },
});
</script>
