Ukázka jednoduchého node.js projektu v typescriptu. Postup vytvoření projektu je popsán v následujících krocích:

# Inicializace projektu
```node
npm init
```
Vyplní se informace o projektu (název, verze, autor, ...)

# Vytvoření Hello.ts
```ts
let message: string = 'Hello, World!';
console.log(message);
```

# Kompilace
Máme zdrojový soubor, ale ještě je potřeba projekt zkompilovat a následně spustit. Ke kompilaci použijeme typescript
```node
npm install typescript
```
Po instalaci typescriptu je potřeba přidat `tsconfig.json`, který bude obsahovat nastavení pro kompilaci. Lze ho vygenerovat příkazem
```node
tsc --init
```
Teď když máme konfig, můžeme kompilaci ručně spustit příkazem `tsc`. Ten zkompiluje soubor `Hello.js`

Pokud chceme soubor rovnou spustit, můžeme tak udělat příkazem
```node
node Hello.js
```
V konzoli bude vidět text
```node
Hello, World!
```

# Skripty
Teď už chybí jen vytvořit npm skripty pro kompilaci a spuštění. Upravíme soubor `package.json`. Skript pro spuštění se obvykle jmenuje `start`, pro kompilaci obdobně `build` a můžeme přidat i `watch`, což je speciální režim kompilace, kdy `tsc` běží na pozadí a při každé změně ve zdrojovém kódu provede rekompilaci výstupního souboru.
```node
"scripts": {
    "start": "node Hello.js",
    "build": "tsc",
    "watch": "tsc --watch"
  },
```
Skripty pak můžeme spouště pomocí npm příkazů `npm run`. U skriptu `start` je vyjímka, že se dá spustit přímo
```node
npm start
npm run build
```

Skripty lze zřetězit dohromady. Například pro spuštění bychom chtěli, aby napřed proběhla kompilace. `package.json` tedy upravíme takto
