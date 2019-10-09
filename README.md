# Hyperledger-study-28

하이퍼레져 앱 만들기 실습 28일차 - node.js 공부

출처 : https://opentutorials.org/course/3332/21031

1. main.js 생성

        var http = require('http');
        var fs = require('fs');
        var app = http.createServer(function(request,response){
            var url = request.url;
            if(request.url == '/'){
              url = '/index.html';
            }
            if(request.url == '/favicon.ico'){
                response.writeHead(404);
                response.end();
                return;
            }
            response.writeHead(200);
            console.log(__dirname + url);
            response.end(fs.readFileSync(__dirname + url));

        });
        app.listen(3000);

2. 예제 실행

         node main.js
