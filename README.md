# ex-js-objects-snack-2
# Tipi di riferimento (oggetti)
const albero = {
    tipo: "melo", 
    quantitaDiFrutti: 14
};
const copiaAlbero = albero;
copiaAlbero.tipo = "pesco";

console.log("albero", albero);
console.log("copiaAlbero", copiaAlbero);

# Copia superficiale
const albero1 = {
    tipo: "melo",
    quantitàDiFrutti: 14,
    proprietario: {nome: "Mario", età: 30}
};

const secondoAlbero = {...albero1, proprietario:{...albero.proprietario}};
secondoAlbero.tipo = "pesco";
secondoAlbero.proprietario.nome = "Hyur";

console.log("albero", albero1);
console.log("copiaAlbero", secondoAlbero);

//? 2 Alberi ma un solo proprietario, ma aggiungendo una spread al valore della proprietà proprietario.

# Copia profonda
const albero2 = {
    tipo: "melo",
    quantitàDiFrutti: 14,
    proprietario: {
        nome: "Mario", 
        età: 30, 
        smartphone: {
            marca: "Samsung", 
            DataDiProduzione: new Date(2024, 4, 16)
        }
    }
};

const copiaAlbero2 = JSON.parse(JSON.stringify(albero2)); //? Serializza e deserializza un oggetto
// const copiaAlbero2 = structuredClone(albero2); //? Funziona con oggetti complessi

copiaAlbero2.proprietario.smartphone.marca = "iPhone";

console.log("albero", albero2);
console.log("copiaAlbero", copiaAlbero2);