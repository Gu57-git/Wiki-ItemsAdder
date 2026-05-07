---
icon: cube
---

# Блоки

## Настройки блока

```yaml
behaviours:
  block:
    placed_model:
      type: REAL_NOTE
      break_particles: BLOCK
      rotx: 0
      roty: 0
    drop_when_mined: true
    light_level: 12 # make block emit light
    # tools you can't use to break block (accepts partial name of material/customitem)
    break_tools_blacklist:
    - WOODEN_PICKAXE
    - STONE_PICKAXE
    - IRON_PICKAXE
    # tools you can use to break block (accepts partial name of material/customitem)
    break_tools_whitelist:
    - DIAMOND_PICKAXE
    - PICKAXE
    - pickaxe
    hardness: 2
    blast_resistance: 1 # explosion resistance (by default is hardness * 3)
    no_explosion: false # totally immune from explosions, ignoring blast_resistance
    sound: # customizable sounds of the block
      break:
        name: BLOCK_WOOD_BREAK
        volume: 1
        pitch: 0.9
      place:
        name: BLOCK_WOOD_PLACE
        volume: 1
        pitch: 0.9
```

## `placed_model`

### `type`

Данная настройка может иметь следующие значения:

* `REAL_NOTE`
  * Использует настоящий полный блок (нотный блок), без нагрузки, без сущностей, 100% настоящий блок.
  * Минусы:
    * **не** поддерживают **прозрачность**.
    * **Лимит** в **750 блоков** в сумме.
* `REAL`
  * Использует настоящий полный блок (блоки грибов), без нагрузки, без сущностей, 100% настоящий блок. (рекомендуется использовать `REAL_NOTE` вместо данного типа по причине стабильности).
  * Минусы:
    * **Лимит** в **191 блок** в сумме.
* `REAL_TRANSPARENT`
  * Использует настоящий неполный блок (стебли хоруса), без нагрузки, без сущностей, 100% настоящий блок, но с поддержкой прозрачности.
  * Минусы:
    * **Лимит** в **63 блока** в сумме.
* `REAL_WIRE`
  * Использует настоящий сквозной (можно проходить сквозь) блок (блок нити), без нагрузки, без сущностей, 100% настоящий блок, поддерживает прозрачность.
  * Минусы:
    * **Лимит** в **127 блоков** в сумме.
* `TILE`
  * Использует **тайловый** блок (модифицированный **спавнер** с текстурой). Это **не сущность**, но имеет свои минусы. Из плюсов - можно создавать **неограниченное количество**, лимит, как у блоков **REAL** - отсутствует.
  * Минусы:
    * Не 100% настроящий блок, это спавнер с текстурой.
    * Текстура/модель внутри спавнера пропадает при большом отдалении от блока, блок отображается как обычный спавнер.
    * В больших количествах способен вызвать понижение FPS у игрока, но в основном на дешевом железе.
* `FIRE`
  * Это **специфичный** тип **блоков**, использующий состояния блоков **огня** для создания нового типа самого огня.
  * Минусы:
    * **Лимит** в всего лишь **14** блоков своего **огня**, убедитесь, что создаете нужный Вам.

{% hint style="warning" %}
- **`REAL`** и **`REAL_NOTE`** предназначены для полных декоративных блоков и для руды.
- **`TILE`** предназначены для редкого использования или для использования как инструмент администратора, чтобы экономить слоты **`REAL`** и **`REAL_NOTE`**.\
  Вы должны НЕ использовать **`TILE`** блоки для руды, потому что _**они могут**_ вызывать понижение производительности при прогрузке и создании чанков. Также мы не рекомендуем использовать их в [деревьях и их популяции](../world-generation/trees-populators.md) или в [популяции в пещерах](../world-generation/cave-decorators.md).
{% endhint %}

### `rotx` и `roty`

Данная функция позволяет задать поворот модели блока. В основном используется продвинутыми пользователями.\
Заданный поворот СТАТИЧЕН, он не является динамическим. Эта функция используется в случае, если Вы хотите создать вариации блока, не создавая отдельную модель вручную.

### `placeable_on_water`

Функция, позволяющая размещать блок прямо на поверхности **воды**.

### **`placeable_on_lava`**

Функция, позволяющая размещать блок прямо на поверхности **лавы**.

### `placeable_on_other_real_wire`

Задайте, если хотите, чтобы блок `REAL_WIRE` мог быть размещен на другом блоке `REAL_WIRE`.

### `shift_up`

Функция, позволяющая размещать блок на 1 блок выше. Используется для блоков `REAL_WIRE`, чтобы создать высокие растения.

### `custom_variants`

{% content-ref url="variants.md" %}
[variants.md](variants.md)
{% endcontent-ref %}

### `drop_when_mined`

{% hint style="warning" %}
Доступно с версии ItemsAdder 4.0.9.

Старые версии используют параметр `cancel_drop` с инвертированными значениями `true/false`.
{% endhint %}

Контралирует выпадение самого блока при его разрушении. Используется для создания блоков, из которых выпадают иные предметы или минералы, а не сам блок (регулируется параметрами Добычи ("loots")).

### `drop_on_shears`

{% hint style="warning" %}
Доступно с версии ItemsAdder 4.0.9.
{% endhint %}

Контралирует выпадение блока при разрушении ножницами.

### `drop_on_silk_touch`

{% hint style="warning" %}
Доступно с версии ItemsAdder 4.0.9.
{% endhint %}

Контралирует выпадение блока при разрушении инструментами с зачарованием "Шелковое касание".

{% hint style="info" %}
Важно, если Вы используете инструмент с зачарованием "шелковое касание" при разрушении блока - Вы получите блок, но опции, заданные в параметрах Добычи ("loots"), будут проигнорированы.
{% endhint %}

## Tools blacklist and whitelist

Позволяет запретить или разрешить разрушение блока указанными инструментами.
Вы можете указать "\_PICKAXE", тогда каждый предмет, имеющий суффикс кирки будет добавлен в список, то же самое актуально для "\_AXE" (топора) и иных инструментов, плагин проверит наименования самостоятельно.\
Это так же работает и для ID предметов ItemsAdder, например, если Вы указали "ruby\_", то все инструменты из рубинов (которые имеют префикс "ruby\_") будет учитываться - (ruby\_pickaxe, ruby\_axe...)

### `break_tools_blacklist`

Запрещает использовать предмет(ы) для разрушения данного блока.

### `break_tools_whitelist`

Разрешает использовать предмет(ы) для разрушения данного блока.

### `events_tools_blacklist`

Запрещает запуск событий предмета для данного блока [ (`placed_block.interact`)](../items/item-properties/events/events-list.md)

### `events_tools_whitelist`

Разрешает запуск событий предмета для данного блока [(`placed_block.interact`)](../items/item-properties/events/events-list.md)

## Прочие параметры

### `hardness`

Hardness - параметр блока, отвечающий за его скорость разрушения.\
Важно, значение задается НЕ в тиках (в основном используется диапозон от 1 до 10), ориентируйтесь на **примеры** в официальном пакете ItemsAdder (файлы **blocks.yml**).

Вы можете задать в параметр `hardness` значение `-1`, чтобы блок ломался мгновенно.

### `blast_resistance`

Сопротивление взрывам (По умолчанию значение просчитывается по формуле: `hardness * 3`).

### `no_explosion`

Абсолютный иммунитет к взрывам, игнорирует опцию `blast_resistance`, даже если та установлена.

### `sounds`

Вы можете задавать наименования [своих звуков](../adding-sounds.md), вместо использования ванильных.\
Вы можете использовать значения обоих форматов, как [формат Spigot](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Sound.html) так и [формат Minecraft](https://www.digminecraft.com/lists/sound_list_pc.php).

{% hint style="info" %}
Если значения не заданы, по умолчанию будут заданы значения блока **камня**.
{% endhint %}

#### Пример использования ванильный звуков

```yaml
    behaviours:
      block:
        placed_model:
          type: REAL_NOTE
          break_particles_material: PRISMARINE_BRICKS
        break_tools_whitelist:
          - PICKAXE
          - pickaxe
        sound:
          break:
            name: minecraft:block.amethyst_block.break
          place:
            name: minecraft:block.amethyst_block.place
          hit:
            name: minecraft:block.amethyst_block.hit
          step:
            name: minecraft:block.amethyst_block.step
          fall:
            name: minecraft:block.amethyst_block.fall

```

#### Пример использования своих звуков

```yaml
    sound:
      break:
        name: my_sounds:sound_1
      place:
        name: my_sounds:sound_2
      hit:
        name: my_sounds:sound_3
      step:
        name: my_sounds:sound_4
      fall:
        name: my_sounds:sound_5
```

{% hint style="info" %}
Чтобы добавить свои звуки - [следуйте данной инструкции](../adding-sounds.md).
{% endhint %}

### `permission_suffix`

Позволяет задать права на установку и разрушение данного блока.\
По умолчанию блок не имеет заданных прав, потому игрок свободно может ломать и ставить блок.\
Игроку нужно будет выдать права на разрушение и установку блока, если Вы зададите следующие параметры:

* `ia.user.block.break.iasurvival.ruby_ore`
* `ia.user.block.place.iasurvival.ruby_ore`

```yaml
info:
  namespace: iasurvival
items:
  ruby_ore:
    enabled: true
    display_name: display-name-ruby_ore
    permission: iasurvival.items.ruby_ore
    resource:
      material: PAPER
      generate: true
      textures:
        - block/ores/ruby_ore
    behaviours:
      block:
        permission_suffix:
          break: iasurvival.ruby_ore
          place: iasurvival.ruby_ore
        hardness: 4
        placed_model:
          type: REAL_NOTE
          break_particles_material: REDSTONE_ORE
        cancel_drop: true
        break_tools_blacklist:
          - WOODEN_PICKAXE
          - STONE_PICKAXE
        break_tools_whitelist:
          - PICKAXE
          - pickaxe
          - _hammer
```

### Use the official files editor to read all the properties

{% content-ref url="../beginners/files-editor.md" %}
[files-editor.md](../../plugin-usage/beginners/files-editor.md)
{% endcontent-ref %}

## Drop experience from block

{% hint style="info" %}
**There are 2 ways to drop** experience **from your custom blocks.**
{% endhint %}

### 1. Add the experience drop directly in the custom block creation

This has a downside, you can only set the experience drop to custom blocks, not to vanilla blocks.

```yaml
  ruby_block:
    display_name: display-name-ruby_block
    permission: ruby_block
    resource:
      material: PAPER
      generate: true
      textures:
      - block/ruby_block.png
    behaviours:
      block:
        placed_model:
          type: REAL_NOTE
          break_particles_material: REDSTONE_BLOCK
        break_tools_whitelist:
        - PICKAXE
        - pickaxe
    events:
      placed_block:
        break:
          drop_exp:
            chance: 100
            min_amount: 0
            max_amount: 3
```

### 2. Add the exp drop to loots

This is the best way because you can also apply this to vanilla blocks types and you can add as many as exp settings you want. This allows you to add more randomness and dynamicity to your drops.

```yaml
loots:
  blocks:
    ruby_ore:
      type: iasurvival:ruby_ore
      items:
        ruby:
          item: iasurvival:ruby
          min_amount: 1
          max_amount: 2
          chance: 100
      exp:
        exp_1:
          min_amount: 0
          max_amount: 3
          chance: 100
```
