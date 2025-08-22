```
    Create repository called "deploy-container-ecr" in you git hub 

```

```
Clone the repository 

 git clone https://github.com/drraoailab/deploy-container-ecr.git

```

```
Under project folder 

create "Dockerfile"

```

```

FROM node:14

WORKDIR /usr/src/app

COPY package.json .
RUN npm install 
COPY . .

EXPOSE 3000

CMD ["node", "index.js"]

```


```
Create index.js
```

```
const http = require('http');

const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.end('<h1>Hello, this is an H1 tag from Node.js!</h1>');
});

const PORT = 3000;
server.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
}
);


```



```
Create package.json
```

```

{
    "name": "docker_nodejs_demo",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
    },
    "keywords": [],
    "author": "",
    "license": "ISC",
    "dependencies": {
      "config": "^3.3.6",
      "express": "^4.17.1"
    }
  }



```


