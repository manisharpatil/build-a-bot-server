# build-a-bot-server
A server used by the build a robot project

## Getting started
- Clone the repository
```
git clone  https://github.com/manisharpatil/build-a-robot-server.git
```
- Install dependencies
```
cd build-a-robot-server
npm install
```

### Compiles and hot-reloads for development with port no. 8081
```
npm run start
```
## Testing
The tests are  written in Mocha and the assertions done using Chai

```
"mocha": "3.4.2",
"chai": "4.1.2",
"chai-http": "3.0.0",

```

### Example application.spec.ts
```
import chaiHttp = require("chai-http")
import * as chai from "chai"
import app from './application'

const expect = chai.expect;
chai.use(chaiHttp);


describe('App', () => {
  it('works', (done:Function): void => {
  chai.request(app)
      .get('/api/hello?greeting=world')
      .send({})
      .end((err:Error, res: any): void => {
          
          expect(res.statusCode).to.be.equal(200);
          expect(res.body.msg).to.be.equal("hello world");
          done();
      });
  
    });
});
```
### Running tests using NPM Scripts
````
npm run test

````
Test files are created under test folder.