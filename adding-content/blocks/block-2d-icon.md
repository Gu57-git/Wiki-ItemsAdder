---
icon: file-png
---

# 2D-иконка блока

{% hint style="warning" %}
Данная функция доступна с версии игры 1.21.2.\
В Minecraft 1.21.2 введена поддержка 2D-иконок напрямую.

Refer to the [modern tutorial here](../items/item-properties/2d-icon.md).
{% endhint %}

{% embed url="https://youtu.be/FOLoAAjV_oI" %}

### Шаг 1

Создание самой 2D-иконки для блока.

{% hint style="info" %}
Замените `myitems` своей [папкой](../../plugin-usage/beginners/configs-and-resourcepack.md#what-is-a-namespace)!
{% endhint %}

```yaml
info:
  namespace: myitems
items:
  rocks:
    display_name: Rocks
    permission: blocks.rocks
    lore:
     - 'lore-decorative-item'
    resource:
      material: PAPER
      generate: true
      textures:
      - item/rocks
    events:
      interact:
        right:
          set_block:
            block: rocks_placed
            target: RELATIVE
            decrement_amount: true
        right_shift:
          set_block:
            block: rocks_placed
            target: RELATIVE
            decrement_amount: true
```

Теперь создайте текстуру `rocks.png` внутри папки `contents\myitems\resourcepack\myitems\textures\item`.

### Шаг 2

Создание самого блока, который будет размещаться предыдущим (который был создан в **шаге 1**).

```yaml
info:
  namespace: myitems
items:
  rocks_placed:
    display_name: ""
    permission: admin.blocks.rocks_placed
    resource:
      material: PAPER
      generate: false
      model_path: block/rocks_placed
    specific_properties:
      block:
        placed_model:
          type: REAL_WIRE
        cancel_drop: true
        sound:
          place:
            name: block.stone.place
    events:
      placed_block:
        break:
          drop_item:
            item: rocks

  rocks:                                #    <--- шаг 1
    display_name: Rocks
    permission: blocks.rocks
    lore:
     - 'lore-decorative-item'
    resource:
      material: PAPER
      generate: true
      textures:
      - item/rocks
    events:
      interact:
        right:
          set_block:
            block: rocks_placed
            target: RELATIVE
            decrement_amount: true
        right_shift:
          set_block:
            block: rocks_placed
            target: RELATIVE
            decrement_amount: true
```

Теперь создайте 3D-модель `placed_rocks.json` и поместите ее в `contents\myitems\resourcepack\myitems\models\block\`.

### Готово!

Теперь попробуйте разместить предмет `rocks`, он разместит модель предмета `rocks_placed`.
