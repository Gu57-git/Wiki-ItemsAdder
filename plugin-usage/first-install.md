---
description: Инструкция о том, как установить плагин
icon: circle-info
---

# Первая установка

{% hint style="danger" %}
**Убедитесь**, что ядро Вашего сервера и установленные плагины обновлены!\
**Всегда обращайте внимание** на то, какую версию ItemsAdder Вы загружаете!

* <mark style="color:red;">**v3 совместима только с версией 1.20.4 и ниже**</mark>
* <mark style="color:red;">**v4 совместима только с версией 1.20.6 и выше**</mark>
{% endhint %}

{% stepper %}
{% step %}
#### Шаг 1 - Установка плагина и библиотек

<details>

<summary>Если Вы устанавливаете плагин версии v3 - используйте эту инструкцию</summary>

* Остановите Ваш сервер.

- Положите JAR-файл **ProtocolLib** в папку `plugins` Вашего сервера
  * Загрузить для 1.21.4 и выше [можно тут](https://github.com/dmulloy2/ProtocolLib/releases/)

* Положите JAR-файл [**LoneLibs**](https://www.spigotmc.org/resources/lonelibs.75974/) в папку `plugins` Вашего сервера (для версии 4.0.9 и выше необязательно)

- Положите JAR-файл **ItemsAdder** в папку `plugins` Вашего сервера

* Запустите Ваш сервер

- Дайте время **ItemsAdder** на загрузку **ресурсов**

</details>

* Остановите Ваш сервер
* Положите JAR-файл `ProtocolLib` в папку `plugins` Вашего сервера (Загрузить можно [тут](https://github.com/dmulloy2/ProtocolLib/releases/download/dev-build/ProtocolLib.jar) )
* Положите JAR-файл `ItemsAdder.jar` в папку `plugins` Вашего сервера
* Запустите Ваш сервер
* Дайте время **ItemsAdder** на загрузку **ресурсов**
{% endstep %}

{% step %}
#### Шаг 2 - настройка пакета ресурсов

{% hint style="warning" %}
**Важно!**

Без выполнения данного шага контент <mark style="color:red;">**НЕ БУДЕТ ОТОБРАЖАТЬСЯ КОРРЕКТНО**</mark>, Вы обязаны выполнить данный шаг!
{% endhint %}

Перед тем, как начать использовать плагин - Вам нужно определиться с медотом размещения пакета ресурсов для его последующей загрузки пользователями.\
Прочтите [данную статью](plugin-configuration/resourcepack-hosting), чтобы выбрать подходящий Вам метод.\
Лучшим методом является `self-host`.
{% endstep %}

{% step %}
#### (рекомендуется) Установка дополнения ItemsAdderAdditions

**ItemsAdderAdditions** - плагин, добавляющий дополнительный функционал, поведение предметов и их действия.
Загрузить - [Modrinth](https://modrinth.com/plugin/itemsadderadditions) | [SpigotMC](https://www.spigotmc.org/resources/itemsadderadditions.133918/)

{% endstep %}

{% step %}
#### (необязательно) Официальный пакет ItemsAdder

![](../.gitbook/assets/items_showcase_gif.apng)

Инструмент **ItemsAdder** предоставляет уже готовый пакет ресурсов с обширным количеством контента для Вас.\
Пакет не устанавливается автоматически по причине, что большинство пользователей предпочитает использовать ItemsAdder только для своего контента на своем сервере.
**Рекомендуем** ознакомиться с данным пакетом, даже если Вы не планируете его устанавливать, так как он содержит большое количество готовых примеров настройки.

{% embed url="https://github.com/ItemsAdder/DefaultPack/releases" %}

<div align="left"><figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure></div>

* Распакуйте архив в папку  `ItemsAdder` с заменой.
* Используйте команду `/iazip`.
* Следуйте инструкции своего [метода размещения](plugin-configuration/resourcepack-hosting) пакета ресурсов, если Вы решили не использовать **self-host**.
{% endstep %}

{% step %}
#### (необязательно) Дополнение к официальному пакету ItemsAdder

**Загрузить:**

{% embed url="https://github.com/ItemsAdder/OtherPacks/releases/latest" %}

<div align="left"><img src="../.gitbook/assets/image (94).png" alt=""></div>
{% endstep %}
{% endstepper %}

<div align="left"><img src="../.gitbook/assets/image (94).png" alt=""></div>
{% endstep %}
{% endstepper %}
