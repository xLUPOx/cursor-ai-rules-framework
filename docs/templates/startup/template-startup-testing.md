# Quick Testing

**Project:** [Project Name]
**Updated:** `YYYY-MM-DD`

## Testing Strategy
**Goal:** Fast, reliable tests that don't slow down development

## Test Types

### Unit Tests (80%)
**What:** Test individual functions/components
**Tool:** [Jest | Pytest | Vitest]
**Target:** 80% coverage

```javascript
// Example: UserService.test.js
test('should create user', () => {
  const user = createUser({ name: 'John', email: 'john@example.com' });
  expect(user.name).toBe('John');
  expect(user.email).toBe('john@example.com');
});
```

### Integration Tests (15%)
**What:** Test API endpoints and database
**Tool:** [Supertest | FastAPI TestClient]
**Target:** Critical paths only

```javascript
// Example: API test
test('POST /users should create user', async () => {
  const response = await request(app)
    .post('/users')
    .send({ name: 'John', email: 'john@example.com' });
  expect(response.status).toBe(201);
});
```

### E2E Tests (5%)
**What:** Test complete user flows
**Tool:** [Playwright | Cypress]
**Target:** Critical user journeys only

## Quick Commands
```bash
# Run all tests
npm test

# Run specific test
npm test -- --testNamePattern="user creation"

# Run with coverage
npm test -- --coverage

# Watch mode
npm test -- --watch
```

## Test Data
```javascript
// test-data.js
export const testUser = {
  name: 'Test User',
  email: 'test@example.com',
  password: 'password123'
};
```

## CI/CD
```yaml
# .github/workflows/test.yml
name: Tests
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
      - run: npm install
      - run: npm test
```

## Best Practices
1. **Write tests first** (TDD)
2. **Keep tests simple**
3. **Test behavior, not implementation**
4. **Use descriptive test names**
5. **Mock external dependencies**

---

**Testing Owner:** [Your name]
