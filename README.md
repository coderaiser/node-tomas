# Tomas

Save data to storage and read from it to speed up computing.

## Install

```
npm i tomas --save
```
## How to use?

```js
const fs = require('fs'),
const tomas = require('tomas'),
const path = './package.json',
const log = (error, data, str) => {
     if (error)
            console.error(error.message);
        else
            console.log(str, data);

    return error;
};

tomas.check(path, (is) => {
    if (is)
        return tomas.read(name, (error, data) => {
           log(error, data, 'tomas read:\n');
        });
    
    fs.readFile(name, 'utf8', (error, data) => {
        if (!log(error))
            tomas.write(name, data, (error) => {
                log(error, data, 'tomas written:\n');
            });
    });
});
```

## License

MIT
