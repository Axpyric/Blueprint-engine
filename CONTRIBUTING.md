# Contributing to Blueprint Engine

Thank you for your interest in contributing! We welcome all types of contributions.

## How to Contribute

### 1. Fork and Clone

```bash
# Fork the repository on GitHub
# Clone your fork
git clone https://github.com/YOUR_USERNAME/blueprint-engine.git
cd blueprint-engine

# Add upstream remote
git remote add upstream https://github.com/Axpyric/blueprint-engine.git
```

### 2. Create a Branch

```bash
# Create a feature branch
git checkout -b feature/your-feature-name

# Or for bug fixes
git checkout -b fix/bug-description
```

### 3. Make Changes

- Write clean, readable code
- Follow the project's coding standards
- Add tests for new functionality
- Update documentation as needed

### 4. Commit Changes

```bash
# Stage your changes
git add .

# Commit with descriptive message
git commit -m "Add feature: brief description"
```

### 5. Push and Create PR

```bash
# Push to your fork
git push origin feature/your-feature-name

# Create a Pull Request on GitHub
```

## Contribution Guidelines

### Code Quality

- Follow existing code style
- Write meaningful variable and function names
- Add comments for complex logic
- Keep functions focused and small
- Use type hints where applicable

### Commit Messages

Format: `type: description`

Types:
- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation changes
- `style:` Code formatting
- `refactor:` Code restructuring
- `test:` Test additions/changes
- `chore:` Maintenance tasks

Example:
```
feat: add markdown export format support
fix: resolve validator schema validation issue
docs: update README with API examples
```

### Pull Request Process

1. **Before Submitting:**
   - Run tests: `npm test`
   - Check linting: `npm run lint`
   - Ensure all tests pass

2. **PR Description:**
   - Clearly describe what you changed
   - Reference any related issues
   - Include steps to test if applicable

3. **Review Process:**
   - Maintainers will review your code
   - Be responsive to feedback
   - Make requested changes
   - Your PR will be merged when approved

## Types of Contributions

### Code Contributions
- New features
- Bug fixes
- Performance improvements
- Refactoring

### Documentation
- README improvements
- API documentation
- Examples
- Tutorials

### Testing
- Unit tests
- Integration tests
- Bug reports (with reproducible examples)

### Community
- Discussions and ideas
- Answering questions
- Sharing experiences
- Reporting issues

## Development Setup

### Install Dependencies

```bash
npm install
```

### Run Development Server

```bash
npm run dev
```

### Run Tests

```bash
npm test
```

### Run Linter

```bash
npm run lint
```

### Build Project

```bash
npm run build
```

## Project Structure for Developers

```
blueprint-engine/
├── src/                    # Source code
│   ├── core/              # Core engine logic
│   ├── validator/         # Validation modules
│   ├── exporter/          # Export handlers
│   └── index.js           # Entry point
├── tests/                 # Test files
├── schemas/               # JSON schemas
├── templates/             # Blueprint templates
├── docs/                  # Documentation
└── examples/              # Example blueprints
```

## Testing Guidelines

### Write Tests For:
- New features
- Bug fixes
- Edge cases
- Error handling

### Test File Naming:
- `*.test.js` or `*.spec.js`
- Mirror source structure in tests directory

### Example Test:

```javascript
const BlueprintValidator = require('../src/validator/validator');

describe('BlueprintValidator', () => {
  test('validates correct blueprint structure', () => {
    const blueprint = { /* valid blueprint */ };
    const validator = new BlueprintValidator();
    const result = validator.validate(blueprint);
    
    expect(result.valid).toBe(true);
  });

  test('rejects blueprint with missing required fields', () => {
    const blueprint = { /* incomplete */ };
    const validator = new BlueprintValidator();
    const result = validator.validate(blueprint);
    
    expect(result.valid).toBe(false);
    expect(result.errors.length).toBeGreaterThan(0);
  });
});
```

## Documentation Standards

### Code Comments

```javascript
/**
 * Creates a new blueprint from input parameters.
 * 
 * @param {Object} input - The blueprint input
 * @param {string} input.title - Blueprint title
 * @param {string} input.category - Blueprint category
 * @returns {Promise<Object>} Created blueprint
 * @throws {Error} If validation fails
 */
async function createBlueprint(input) {
  // Implementation
}
```

### README Sections
- Title and description
- Key features
- Installation
- Usage examples
- Configuration
- Contributing
- License

## Code Review Checklist

Before submitting, ensure:
- [ ] Code follows project style guide
- [ ] Tests are added/updated
- [ ] Documentation is updated
- [ ] Commit messages are clear
- [ ] No console.log statements left
- [ ] All tests pass
- [ ] No breaking changes (or documented)

## Getting Help

- **Questions**: Open a GitHub Discussion
- **Bug Reports**: Open an Issue with reproduction steps
- **Ideas**: Start a Discussion or Issue
- **Code Review**: Ask in PR comments

## Code of Conduct

Please see [CODE_OF_CONDUCT.md](../CODE_OF_CONDUCT.md) for community guidelines.

## License

By contributing, you agree that your contributions will be licensed under the Apache-2.0 License.

## Recognition

Contributors are recognized in:
- GitHub contributors page
- CONTRIBUTORS.md file (coming soon)
- Release notes

## Questions?

- Open a Discussion on GitHub
- Check existing issues and PRs
- Review documentation

Thank you for contributing to Blueprint Engine! 🚀
