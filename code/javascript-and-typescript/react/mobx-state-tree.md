# mobx-state-tree

## Actions vs. Views

Nodes can only be modified via actions (any self modification should be done through these), volatile state can also be stored in actions, actions also can have middleware and actionlisteners. Views are pretty much `get property()` substitutes and should be used only as such (unless you need a computed view).

## Model.toJSON();

use this instead of `getSnapshot()` for debugging purposes

## Handling circular dependencies/ self-referencing errors

Typically arises with typescript and using the `getRoot()` function:

```typescript
const root: types.maybe(types.late((): IAnyModelType => RootStoreType));
```

## Type composition inheritance

```typescript
const Square = types.model("Square", ...);
const Box = Square.named("Box")
    .views(self => {
        const superView = self.view;
        return {
            view() {
                const modifier = ...;
                return superView() * modifier;
            }
            unImplementedView() {
                return self.view * self.other;
            }
        }
    });
const Shape = types.union(Box, Square);
```

## Using \`this\` instead of \`self\` in views and actions

You can use `this.prop` to refer to properties that are defined in that current action view for that model e.g:

```typescript
const Example = types.model("Example", { prop: types.string })
    .views(self => ({
        get upperProp(): string {
            return self.prop.toUpperCase();
        }
        get twiceUpperProp(): string {
            // using self.upperProp will give a 'not yet defined' error
            return this.upperProp + this.upperProp;
        }
    }));
```
