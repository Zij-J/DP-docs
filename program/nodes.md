# Nodes
### Get Child Node
Get child node like a pro: https://www.youtube.com/watch?v=fb68YXIBinc
  
`$NodePath`: Shorthand for `get_node("NodePath")`

If the current node calls `get_node("Sword")`, it will get `./Sword`, i.e., the child named `Sword` 

> `@export` for pre-exist children, `@onready` otherwises.

P.S. [Variable initialization order](https://docs.godotengine.org/zh-cn/4.x/tutorials/scripting/gdscript/gdscript_basics.html#initialization-order)
1. default value
2. gdscript top to bottom
3. Constructor then `_init()`
4. `@export` from editor
    - but
      ```gdscript
      @export var sprite: sprite2D;
      @export_range(0, 1) var disco_range: float = 1:
        set(value):
          print(sprite)
          disco_range = value
      ```
      the print will be `<null>`, but
      - setter will be called in `@export` ([not in `@onready`, direct default value initialize and set inside setter](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html#when-setter-getter-is-not-called))
      - `@export` others then `@export Nodes` will be initialized from top to down 
    - and
      ```
      func _ready() -> void:
        print(sprite);
      ```
      will be `<null>` too
    - so maybe in Godot 4.X:
      ```
      @export var sprite: sprite2D;
      ```
      is just the short hand for
      ```
      @export var hidden_node_path: NodePath;
      func _ready():
        # ...
        # at the end of _ready
        sprite = get_node(hidden_node_path);
      ```
5. (Only for Node-derived classes) [`@onready`](https://docs.godotengine.org/zh-tw/4.x/tutorials/scripting/gdscript/gdscript_basics.html#onready-annotation)
    - so it overwrite `@export`
6. (Only for Node-derived classes) `_ready()`

