# bemmet

Simple Emmet-like tool to expand shorcuts into [BEMJSON](https://en.bem.info/technology/bemjson/).

## Usage
```js
var bemmet = require('bemmet');
var bemjson = bemmet('b1>__e1*2>b3_theme_islands+_state_active');

console.log(bemjson);
// {
//     block: 'b1',
//     content: [
//         {
//             block: 'b1',
//             elem: 'e1',
//             content: [
//                 {
//                     block: 'b3',
//                     mods: { theme: 'islands' },
//                     content: {}
//                 },
//                 {
//                     block: 'b1',
//                     mods: { state: 'active' },
//                     content: {}
//                 }
//             ]
//         },
//         {
//             block: 'b1',
//             elem: 'e1',
//             content: [
//                 {
//                     block: 'b3',
//                     mods: { theme: 'islands' },
//                     content: {}
//                 },
//                 {
//                     block: 'b1',
//                     mods: { state: 'active' },
//                     content: {}
//                 }
//             ]
//         }
//     ]
// }
```

### Custom naming scheme
```js
var bemmet = require('bemmet');
var shortcut = 'b1>__e1*2>b3--islands+--active';
var bemjson = bemmet(shortcut, {
    naming: {
        elem: '__',
        mod: '--'
    }
});

console.log(bemjson);
// {
//     block: 'b1',
//     content: [
//         {
//             block: 'b1',
//             elem: 'e1',
//             content: [
//                 {
//                     block: 'b3',
//                     mods: { islands: true },
//                     content: {}
//                 },
//                 {
//                     block: 'b1',
//                     mods: { active: true },
//                     content: {}
//                 }
//             ]
//         },
//         {
//             block: 'b1',
//             elem: 'e1',
//             content: [
//                 {
//                     block: 'b3',
//                     mods: { islands: true },
//                     content: {}
//                 },
//                 {
//                     block: 'b1',
//                     mods: { active: true },
//                     content: {}
//                 }
//             ]
//         }
//     ]
// }
```
