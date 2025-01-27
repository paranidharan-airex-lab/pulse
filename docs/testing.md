# Testing Guide

This guide provides comprehensive information about testing the PULSE library, including unit tests, integration tests, and validation procedures.

## Testing Overview

PULSE uses pytest as its primary testing framework and includes several types of tests:

- Unit tests for individual components
- Integration tests for system-wide functionality
- Performance tests for optimization
- Validation tests for accuracy

## Running Tests

### Basic Test Execution

To run the complete test suite:

```bash
pytest tests/
```

For specific test categories:

```bash
# Run only unit tests
pytest tests/test_models.py

# Run integration tests
pytest tests/test_integration.py

# Run with verbose output
pytest -v tests/
```

### Test Configuration

#### Using test fixtures

Tests use fixtures defined in `tests/conftest.py`:

```python
@pytest.fixture
def basic_scenario():
    return {
        'start_time': 0,
        'end_time': 10,
        'time_step': 0.1
    }

@pytest.fixture
def basic_radar():
    return {
        'name': 'TestRadar',
        'position': [0, 0],
        'rotation_type': 'constant'
    }
```

#### Custom test configurations

Create custom test configurations in `tests/fixtures/test_config.yaml`:

```yaml
test_scenario:
  duration: 100
  sample_rate: 1000

test_parameters:
  noise_level: 0.1
  error_threshold: 0.01
```

## Test Categories

### 1. Unit Tests

Unit tests cover individual components:

- Core classes (Scenario, Radar, Sensor)
- Utility functions
- Error models
- Data generators

### 2. Integration Tests

Integration tests verify system-wide functionality:

- End-to-end simulation workflows
- Data pipeline integration
- Configuration management
- Error handling

### 3. Performance Tests

Performance tests evaluate:

- Computation speed
- Memory usage
- Scalability
- Resource optimization

### 4. Validation Tests

Validation tests ensure:

- Physical accuracy of simulations
- Statistical validity of generated data
- Proper error modeling
- Configuration handling

## Writing Tests

### Test Structure

Follow this structure for new tests:

```python
def test_component_function():
    # Setup
    input_data = prepare_test_data()
    
    # Exercise
    result = component_function(input_data)
    
    # Verify
    assert result.property == expected_value
    assert validate_output(result)
    
    # Cleanup (if needed)
    cleanup_test_data()
```

### Test Guidelines

1. **Isolation**: Each test should be independent
2. **Clarity**: Use descriptive test names
3. **Coverage**: Aim for comprehensive coverage
4. **Performance**: Keep tests efficient
5. **Maintenance**: Keep tests up to date

## Continuous Integration

### GitHub Actions Workflow

Tests are automatically run on:

- Pull requests
- Main branch commits
- Release tags

### CI Configuration

```yaml
name: PULSE Tests
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Set up Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.12'
      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt
      - name: Run tests
        run: |
          pytest tests/
```

## Test Coverage

### Generating Coverage Reports

```bash
pytest --cov=pulse tests/
```

### Coverage Requirements

- Minimum coverage: 80%
- Critical components: 95%
- New features: 100%

## Troubleshooting Tests

### Common Issues

1. **Failed Tests**
   - Check test dependencies
   - Verify test data
   - Review error messages

2. **Slow Tests**
   - Profile test execution
   - Optimize test data
   - Review test isolation

3. **Flaky Tests**
   - Check for race conditions
   - Verify test independence
   - Review timing assumptions

## Best Practices

1. **Test Data Management**
   - Use fixtures for common data
   - Clean up test artifacts
   - Version control test data

2. **Test Organization**
   - Group related tests
   - Use meaningful names
   - Document test purposes

3. **Test Maintenance**
   - Regular updates
   - Remove obsolete tests
   - Keep documentation current

## Contributing Tests

When contributing new tests:

1. Follow existing patterns
2. Include documentation
3. Verify coverage
4. Test edge cases
5. Review performance impact