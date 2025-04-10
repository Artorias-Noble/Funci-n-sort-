# Funci-n-sort-
Función que ordena un array de menor a mayor o viceversa.

/*
UNA FUNCIÓN QUE ORDENA UN ARRAY DE MENOR A MAYOR O VICEVERSA DEPENDIENDO DE LA 
INDICACIÓN.
La función recibe dos orgumentos, el primero es el objecto array y el segundo
es la manera en la que quieres que sean ordenados los números, tienes dos 
opciones:
1ra - Menor: ordena del numero más pequeño al mas grande.
2da - Mayor: ordena del numero más grande al mas pequeño.
Dicho argumento debe ser ingresado como un string.

*/
const sortFunction = (array, order) => {
    const clonarArray = (array) => {
        let newArray = [];
        for(let i = 0; i < array.length; i++){
            newArray.push(array[i]);
        };
        return newArray;
    };
    let arr = clonarArray(array);
    let sortArray = [];
    let numberI;
    let arrayLength = arr.length;
    for(let i = 0; i < arrayLength; i++){
        numberI = arr[0];
        for(let j = 0; j < arrayLength; j++){
            if(order !== undefined){
                if(order.toLowerCase().trim() === 'mayor') if(numberI < arr[j]) numberI = arr[j];
                if(order.toLowerCase().trim() === 'menor') if(numberI > arr[j]) numberI = arr[j];
            }else{
                if(numberI > arr[j]) numberI = arr[j];
            };
        };
        sortArray.push(arr.splice(arr.indexOf(numberI),1)[0]);
    };
    return sortArray;
};
