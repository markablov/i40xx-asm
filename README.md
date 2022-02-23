# i40xx-asm

[![npm version](https://img.shields.io/npm/v/i40xx-asm)](https://www.npmjs.com/package/i40xx-asm)

Assembly for Intel 4004/4040 architecture

## Installation

Install globally:

```sh
npm install -g i40xx-asm
```

## Usage

Compiles `program.i4004` into ROM image and store it into `program.bin`

```sh
i40xx-asm program.i4004 program.bin 
```

You can omit output file name, in that case assembler would replace extension of input file name to `.bin`

## Module/Programmatic Usage

npm-check-updates can be required as a module:

```js
const parse = require('i40xx-asm');

const { errors, data } = parse('nop');
if (Array.isArray(errors) && errors.length) {
  console.log(errors);
  process.exit(1);
}

console.log(`First byte of ROM is ${data[0]}`);
```
