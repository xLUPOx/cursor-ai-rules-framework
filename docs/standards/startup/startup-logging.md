# Quick Logging

**Project:** [Project Name]
**Updated:** `YYYY-MM-DD`

## Logging Strategy
**Goal:** Simple, effective logging for debugging and monitoring

## Log Levels
- **ERROR:** Something went wrong
- **WARN:** Something might be wrong
- **INFO:** Important business events
- **DEBUG:** Development debugging

## Quick Setup

### Node.js
```javascript
// logger.js
const winston = require('winston');

const logger = winston.createLogger({
  level: process.env.LOG_LEVEL || 'info',
  format: winston.format.combine(
    winston.format.timestamp(),
    winston.format.json()
  ),
  transports: [
    new winston.transports.Console(),
    new winston.transports.File({ filename: 'app.log' })
  ]
});

module.exports = logger;
```

### Python
```python
# logger.py
import logging
import os

logging.basicConfig(
    level=os.getenv('LOG_LEVEL', 'INFO'),
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    handlers=[
        logging.StreamHandler(),
        logging.FileHandler('app.log')
    ]
)

logger = logging.getLogger(__name__)
```

## Usage Examples

### Node.js
```javascript
const logger = require('./logger');

// Business events
logger.info('User created', { userId: '123', email: 'user@example.com' });

// Errors
logger.error('Database connection failed', { error: error.message });

// Debug
logger.debug('Processing request', { requestId: 'req-123' });
```

### Python
```python
import logging

logger = logging.getLogger(__name__)

# Business events
logger.info('User created', extra={'userId': '123', 'email': 'user@example.com'})

# Errors
logger.error('Database connection failed', exc_info=True)

# Debug
logger.debug('Processing request', extra={'requestId': 'req-123'})
```

## Environment Variables
```bash
# .env
LOG_LEVEL=info
LOG_FILE=app.log
```

## Production Setup
```javascript
// Production logging
const logger = winston.createLogger({
  level: 'warn',
  format: winston.format.json(),
  transports: [
    new winston.transports.Console(),
    new winston.transports.File({ filename: 'error.log', level: 'error' })
  ]
});
```

## Best Practices
1. **Log important business events**
2. **Include context (user ID, request ID)**
3. **Don't log sensitive data**
4. **Use appropriate log levels**
5. **Keep logs structured (JSON)**

## Monitoring
```javascript
// Health check logging
logger.info('Health check', {
  status: 'healthy',
  timestamp: new Date().toISOString(),
  uptime: process.uptime()
});
```

---

**Logging Owner:** [Your name]
