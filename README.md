# localStorage
关于localStorage赋值，并不是一个指向这个获取到的键值的指针

    var storage = window.localStorage,
        defense = storage.getItem("defense");
    
    defense.setItem("defense", "true");
    
    console.log(defense); // true
    
    if(defense){
        storage.removeItem("defense");
        
        console.lgo(defense); // true
        console.lgo(storage.getItem("defense")); // null
    }
