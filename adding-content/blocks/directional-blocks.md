---
icon: arrow-rotate-left
---

# Блоки с направлением

{% hint style="info" %}
#### Необходима версия ItemsAdder 4.0.10 или выше
{% endhint %}

{% hint style="warning" %}
#### Внимание!

Создание одного блока подобного типа будет занимать сразу 4 или 6 слотов блоков выбранного типа (`real`, `real_note` и так далее).\
Причина, по которой это происходит - каждое направление блока фактически является отдельным блоком.

К сожалению, на данный момент нет никаких путей это обойти. Этот лимит навязан самой игрой, любые плагины для создания контента в ванильной игре будут иметь точно такую же проблему.\
Мы не рекомендуем частое использование данной функции, так как она может очень быстро исчерпать лимит новых блоков. 
{% endhint %}

{% hint style="info" %}
`FURNACE` и `DROPPER` не будут работать как ванильные печь и выбрасыватель. Это просто имена, чтобы Вам было проще понять тип поворота блоков.
{% endhint %}

### Режимы поворота

### Режим `ALL`

Поведение поворота как у ванильных брёвен и у выбрасывателя одновременно.

![](https://github.com/user-attachments/assets/db9c84da-c30c-40c4-a53d-7850ebd3ad8b)

```yaml
  directional_block_all:
    name: directional_block_all
    resource:
      material: PAPER
      generate: true
      textures:
      - block/furnace/directional_block_test_down.png
      - block/furnace/directional_block_test_east.png
      - block/furnace/directional_block_test_north.png
      - block/furnace/directional_block_test_south.png
      - block/furnace/directional_block_test_up.png
      - block/furnace/directional_block_test_west.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
          directional_mode: ALL
```

### Режим `FURNACE`

Поведение поворота как у ванильной печки.

![](https://github.com/user-attachments/assets/c4c6c501-a1fa-4cd1-a2de-67c3ad5d626a)

```yaml
  directional_block_furnace:
    name: directional_block_furnace
    resource:
      material: PAPER
      generate: true
      textures:
      - block/furnace/directional_block_test_down.png
      - block/furnace/directional_block_test_east.png
      - block/furnace/directional_block_test_north.png
      - block/furnace/directional_block_test_south.png
      - block/furnace/directional_block_test_up.png
      - block/furnace/directional_block_test_west.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
          directional_mode: FURNACE
```

### Режим `LOG`

Поведение поворота как у брёвен.

![](https://github.com/user-attachments/assets/db9c84da-c30c-40c4-a53d-7850ebd3ad8b)

```yaml
  directional_block_log:
    name: directional_block_log
    resource:
      material: PAPER
      generate: true
      textures:
      - block/log/directional_block_test_down.png
      - block/log/directional_block_test_east.png
      - block/log/directional_block_test_north.png
      - block/log/directional_block_test_south.png
      - block/log/directional_block_test_up.png
      - block/log/directional_block_test_west.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
          directional_mode: LOG
```

### Режим `DROPPER`

Поведение поворота как у выбрасывателя.

![](https://github.com/user-attachments/assets/c097ac52-80ba-4daf-865b-7726ad3e8b87)

В данном случае я решил перезаписать автоматическую генерацию двух направлений направленного блока, создав конфигурацию для состояний `верх` и `низ` отдельно, чтобы изменить внешний вид блока в данном конкретном случае, установив этим другую текстуру для `северной` стороны (передней).\
На данном скриншоте Вы можете заметить, что текстура передней стороны отличается.

```yaml
  directional_block_dropper:
    name: directional_block_dropper
    resource:
      material: PAPER
      generate: true
      textures:
      - block/dropper/directional_block_test_down.png
      - block/dropper/directional_block_test_east.png
      - block/dropper/directional_block_test_north.png
      - block/dropper/directional_block_test_south.png
      - block/dropper/directional_block_test_up.png
      - block/dropper/directional_block_test_west.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
          directional_mode: DROPPER

  directional_block_dropper_up:
    name: directional_block_dropper_up
    resource:
      material: PAPER
      generate: true
      textures:
      - block/dropper/directional_block_test_down.png
      - block/dropper/directional_block_test_east.png
      - block/dropper/directional_block_test_north_variant.png         #   <--  тут
      - block/dropper/directional_block_test_south.png
      - block/dropper/directional_block_test_up.png
      - block/dropper/directional_block_test_west.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
  directional_block_dropper_down:
    name: directional_block_dropper_down
    resource:
      material: PAPER
      generate: true
      textures:
      - block/dropper/directional_block_test_down.png
      - block/dropper/directional_block_test_east.png
      - block/dropper/directional_block_test_north_variant.png         #   <--  и тут
      - block/dropper/directional_block_test_south.png
      - block/dropper/directional_block_test_up.png
      - block/dropper/directional_block_test_west.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
```

## Создание моделей вручную

ItemsAdder автоматически повернет модель Вашего блока, но Вы можете использовать свои варианты для каждого направления.

В моем случае, в примере с `DROPPER` выше, я сделал отдельные конфигурации для направлений `верха` и `низа`.

Чтобы провернуть подобное - Вам нужно создать отдельную конфигурацию блока для этого направления и задать ему суффикс `_<направление>` в ID.

Возможные направления:

* `north`
* `east`
* `south`
* `west`
* `up`
* `down`

В моем примере я использовал `directional_block_dropper_up` (`_up`) и `directional_block_dropper_down` (`_down`) для блока `directional_block_dropper`.
