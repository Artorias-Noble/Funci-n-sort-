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

