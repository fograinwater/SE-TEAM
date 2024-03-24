# #个人介绍

## 自我简介

姓名：刘昱娴

邮箱：2780197685@qq.com

学校：华中师范大学

学院：计算机学院


## 专业技能
1. 熟悉掌握计算机基础知识，如常见的数据结构、算法、计算机网络以及操作系统等领域的知识。
2. 熟悉前端三件套，ES6+语法，React、Vue3等框架


## 代码示例

```javascript
function WrappedPromiseAll(iteratorThing) {
    return new Promise((resolve, reject) => {
        let results = [];
        let mes = Array.from(iteratorThing);
        let completedCount = 0;

        if(mes.length === 0) {
            resolve(results);
            return;
        }

        mes.forEach((element, index) => {
            Promise.resolve(element)
                .then(res => {
                    results[index] = res;
                    completedCount++;
                    if(completedCount == mes.length) resolve(results);
                })
                .catch(error => reject(error));

        });
    })
}

//利用promise，实现隔1s输出1，隔2s输出2....直到10s输出10
function fn_sleep(delay) {
    return new Promise(resolve => {
        let timer = setTimeout(() => {
            console.log(delay);
            clearTimeout(timer);
            resolve();
        }, delay*1000);
    })
}

async function fn_log_wait(count) {
    for(let i = 1; i <= count; i++) await fn_sleep(i);
}
fn_log_wait(10);
```

