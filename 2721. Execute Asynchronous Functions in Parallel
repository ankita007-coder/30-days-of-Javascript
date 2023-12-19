/**
 * @param {Array<Function>} functions
 * @return {Promise<any>}
 */
var promiseAll = function(functions) {
    return new Promise((resolve,reject)=>{
        let results = []
        let pending = functions.length;
        functions.forEach((fn,i)=>{
            fn().then((value)=>{
                results[i]=value
                pending--;

                if(pending===0){
                    resolve(results)
                }
            }).catch(err=>{
                reject(err);
            })
        })
    })
};

/**
 * const promise = promiseAll([() => new Promise(res => res(42))])
 * promise.then(console.log); // [42]
 */
