<p align="center">
  <span><i><b>The powerful hangul library</i></b></span>
  <br><Br>
  <img alt="GitHub" src="https://img.shields.io/github/license/Lukince/Hangul4deno">
  <img alt="GitHub repo size" src="https://img.shields.io/github/repo-size/Lukince/Hangul4deno">
  <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/Lukince/Hangul4deno">
</p>

  <i>Please check [README.md](https://github.com/Lukince/Hangul4deno/blob/master/README.md) on github if possible. it changes frequently.</i>

# Features

### Assemble, Disassemble Hangul

```ts
import { Assembler } from "https://deno.land/x/hangul@1.0.0/mod.ts"

const hello = Assembler.assemble(['ㅇ', 'ㅏ', 'ㄴ', 'ㄴ', 'ㅕ', 'ㅇ']);

console.log(hello); // log : 안녕

const dishello = Assembler.disassemble("안녕하세요");
```

### Convert English to Korean, Korean to English
**Note : This is not a translation. This'll assemble after converting according to the QWERTY keyboard**

```ts
import { Hangul } from "https://deno.land/x/hangul@1.0.0/mod.ts"

console.log(Hangul.engToKor("dkssud tprP!"));
// log : 안녕 세계!

console.log(Hangul.korToEng("안녕 세계!"));
// log : dkssud tprP!
```

### Build hangul with initial, neutral and final

```ts
import { HangulBuilder } from "https://deno.land/x/hangul@1.0.0/mod.ts"

const builder1 = new HangulBuilder();

builder1.setInitial('ㅇ');
builder1.setNeutral('ㅏ');
builder1.setFinal('ㄴ');

const builder2 = new HangulBuilder('ㄴ', 'ㅕ', 'ㅇ');

console.log([builder1.build(), builder2.build()].join(''));
// log : 안녕
```