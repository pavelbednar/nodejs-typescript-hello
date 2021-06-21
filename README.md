# nodejs-typescript-hello

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
