# 实体组件

**实体组件**是用来规定实体的功能。将不同的实体组件组合在一起可以实现多种复杂的功能。通过实体组件，你可以做到让猪爆炸或者飞起来。

实体组件可以指定到**components**中，以使得实体在所有情况下都使用相关功能；也可以指定到实体组件组**component_groups**中，使得实体在使用特定事件时使用特定的功能。

## 实体组件列表

### minecraft:rideable

定义该实体为可被骑乘的实体

### minecraft:addrider

注意：此组件要求格式版本至少为**1.8.0**，但是推荐使用格式版本**1.21.130**。

注意：需要`minecraft:rideable`组件才能正常工作，且受到`minecraft:rideable`组件的`seat_count`限制。

注意：从 1.21.130 版本开始，该组件可通过 riders 字段接受骑乘者数组（每个骑乘者包含必填的 entity_type 和可选的 spawn_event）。传统的单一 entity_type / spawn_event 形式仍然保留，以保持向后兼容。

为实体添加一个骑乘者（rider），即定义“马”上的实体可以是谁。如：

```json

"minecraft:addrider": {
  "riders": [
    { "entity_type": "minecraft:bogged" }
  ]
}

```

或者：

```json

"minecraft:addrider": {
  "riders": [
    {
      "entity_type": "minecraft:zombie_pigman",
      "spawn_event": "minecraft:spawn_as_strider_jockey"
    }
  ]
}

```
其中：

| 名称 | 默认值 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| **entity_type** | 未设置 | 字符串 | 骑乘此实体的实体类型 |
| **spawn_event** | 未设置 | 字符串 | 创建骑乘实体时将使用的生成事件 |
