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
#### Ремендовано - установка ItemsAdderAdditions 
00000000000000000000000000000000000000000000000000000000000000

{% step %}
#### (optional) Add official ItemsAdder custom content

![](../.gitbook/assets/items_showcase_gif.apng)

**ItemsAdder** comes with a lot of custom content already created for you.\
It's not automatically included in the downloaded plugin because some people might not want every item/feature automatically added into their server.

{% embed url="https://github.com/ItemsAdder/DefaultPack/releases" %}

<div align="left"><figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure></div>

* Extract the content into the `ItemsAdder` folder and overwrite the files if asked.
* Run the `/iazip` command.
* Follow your [hosting method](plugin-configuration/resourcepack-hosting) if you're not using **self-host**.
{% endstep %}

{% step %}
#### (optional) Add other ItemsAdder custom content

**Download the Other Packs here:**

{% embed url="https://github.com/ItemsAdder/OtherPacks/releases/latest" %}

<div align="left"><img src="../.gitbook/assets/image (94).png" alt=""></div>
{% endstep %}
{% endstepper %}
