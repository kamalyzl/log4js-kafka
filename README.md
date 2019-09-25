# log4js-kafka

Kafka appender for [log4js](https://github.com/log4js-node/log4js-node).

## Installation

```bash
npm i log4js-kafka
```

## Setup

### TOML
```toml
[log4js.appenders.kafka1]
type = "log4js-kafka"
clientId = "demo"
brokers = [ "localhost:9092",]
topic = "topic1"
ssl = false

[log4js.categories.local]
appenders = [ "kafka1",]
level = "debug"
```

### JSON
```json
{
  "log4js": {
    "appenders": {
      "kafka1": {
        "type": "log4js-kafka",
        "clientId": "demo",
        "brokers": [
          "localhost:9092"
        ],
        "topic": "topic1",
        "ssl": false
      }
    },
    "categories": {
      "local": {
        "appenders": [
          "kafka1"
        ],
        "level": "debug"
      }
    }
  }
}
```

## Usage

### JS
```javascript
const log4js = require('log4js');
const logger = log4js.getLogger('local');

logger.debug('Hola mundo');
```

## Options
* type: log4js-kafka
* clientId: project ID
* brokers: kafka instances
* topic: the topic to send
* ssl: active
* DL4K=0: (environment variable) disable the fakfa appender and use the console instead
  * DL4K=0 node server.js

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
