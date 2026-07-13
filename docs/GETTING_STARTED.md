# Getting Started with Blueprint Engine

## Installation

### Prerequisites
- Node.js 14+
- npm or yarn

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/Axpyric/blueprint-engine.git
   cd blueprint-engine
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Verify installation**
   ```bash
   npm run dev
   ```

## Basic Usage

### Creating a Blueprint

```javascript
const BlueprintEngineApp = require('./src/index');

const app = new BlueprintEngineApp();

const input = {
  title: 'My First Blueprint',
  category: 'Development',
  purpose: 'Create a blueprint for my project',
  goal: 'Build a scalable system',
  style: 'Modern',
  constraints: ['Budget-conscious', 'Quick delivery'],
  tags: ['web', 'development']
};

const blueprint = await app.createBlueprint(input);
console.log(blueprint);
```

### Exporting Blueprints

```javascript
// Export as JSON
const jsonExport = app.exportBlueprint(blueprint.id, 'json');

// Export as Markdown
const mdExport = app.exportBlueprint(blueprint.id, 'markdown');

// Export as YAML
const yamlExport = app.exportBlueprint(blueprint.id, 'yaml');

// Export as plain text
const txtExport = app.exportBlueprint(blueprint.id, 'txt');
```

### Listing Blueprints

```javascript
const allBlueprints = app.listBlueprints();
console.log(allBlueprints);
```

## Project Structure

```
blueprint-engine/
├── src/
│   ├── core/
│   │   └── engine.js              # Main blueprint engine
│   ├── validator/
│   │   └── validator.js            # Blueprint validator
│   ├── exporter/
│   │   └── exporter.js             # Export handler
│   └── index.js                    # Main application
├── schemas/
│   └── blueprint.schema.json       # JSON schema
├── examples/
│   └── example-blueprint.json      # Example blueprint
├── docs/
│   ├── ARCHITECTURE.md
│   └── GETTING_STARTED.md
└── tests/
    └── (test files)
```

## Common Tasks

### Create a Blueprint Programmatically

```javascript
const BlueprintEngineApp = require('./src/index');
const app = new BlueprintEngineApp();

const blueprint = await app.createBlueprint({
  title: 'REST API Design',
  category: 'Backend',
  purpose: 'Design guidelines for REST APIs',
  goal: 'Define REST API standards',
  style: 'RESTful',
  constraints: ['JSON responses', 'Stateless'],
  notes: ['Use proper HTTP status codes']
});
```

### Save Blueprint to File

```javascript
const BlueprintExporter = require('./src/exporter/exporter');
const exporter = new BlueprintExporter();

await exporter.saveToFile(blueprint, './output/blueprint.json', 'json');
await exporter.saveToFile(blueprint, './output/blueprint.md', 'markdown');
```

### Validate a Blueprint

```javascript
const BlueprintValidator = require('./src/validator/validator');
const validator = new BlueprintValidator();

const validation = validator.validateBlueprint(blueprint);
console.log('Valid:', validation.valid);
console.log('Errors:', validation.errors);
console.log('Warnings:', validation.warnings);
```

## Configuration

### Environment Variables

Create a `.env` file in the project root:

```env
NODE_ENV=development
DEBUG=true
EXPORT_PATH=./exports
```

### Schema Customization

Modify `schemas/blueprint.schema.json` to customize validation rules.

## Running Tests

```bash
npm test
```

Tests cover:
- Engine functionality
- Validation logic
- Export formats
- Error handling

## Troubleshooting

### Issue: Module not found
**Solution**: Run `npm install` to ensure all dependencies are installed.

### Issue: Validation failures
**Solution**: Check the blueprint structure against `schemas/blueprint.schema.json`.

### Issue: Export errors
**Solution**: Ensure the export format is supported: json, markdown, yaml, txt.

## Next Steps

1. **Read the Architecture Guide**: `docs/ARCHITECTURE.md`
2. **Explore Examples**: Check `examples/` directory
3. **Run the Demo**: `npm run dev`
4. **Contribute**: See CONTRIBUTING.md

## API Reference

### BlueprintEngineApp

#### `createBlueprint(input)`
Creates and validates a new blueprint.
- **Input**: Object with blueprint parameters
- **Returns**: Promise<Object> - Created blueprint
- **Throws**: Error if validation fails

#### `exportBlueprint(blueprintId, format)`
Exports a blueprint to specified format.
- **Input**: blueprintId (string), format (json|markdown|yaml|txt)
- **Returns**: String - Exported content
- **Throws**: Error if blueprint not found or format unsupported

#### `listBlueprints()`
Lists all blueprints.
- **Returns**: Array<Object> - All blueprints

## Support

For issues, questions, or contributions:
- Create an issue on GitHub
- Submit a pull request
- Contact: [Your email]

## License

MIT License - See LICENSE file for details
