# Narrative MCP System

A Multi-MCP Architecture for Novel Writing with AI-optimized tokenization and consistency management.

## Overview

The Narrative MCP System provides a framework for managing narrative elements as structured, swappable data. It breaks down complex storytelling into manageable components that can be programmatically manipulated while maintaining narrative integrity.

## Features

- **Character Management**: Consistent personality, voice patterns, and progression tracking
- **Relationship Dynamics**: State machines for character interactions and evolution
- **Consistency Validation**: Automated checking for narrative coherence
- **Scene Generation**: Pattern-based scene creation and expansion
- **AI Integration**: Optimized tokenization for LLM collaboration
- **Version Control**: Track character and story evolution

## Quick Start

### 1. Setup Environment

```bash
# Clone or create project directory
mkdir narrative-mcp-system
cd narrative-mcp-system

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate     # Windows

# Install dependencies
pip install -r requirements.txt
pip install -r requirements-dev.txt
```

### 2. Verify Installation

```bash
# Run basic tests
pytest tests/test_basic_setup.py -v

# Test imports
python -c "from narrative_mcp.shared.schemas import CharacterState; print('✓ Imports working')"
```

### 3. Create Your First Character

```python
from narrative_mcp.shared.schemas import CharacterState, VoiceSignature, ProgressionLocks

# Define character voice
voice = VoiceSignature(
    internal_monologue="bitter_humor + metaphor_heavy",
    external_dialogue="resistant + sharp_edged",
    signature_phrases=["cosmic justice", "PhD in ironic justice"],
    emotional_range={"cynicism": 0.9, "vulnerability": 0.3}
)

# Define progression constraints
locks = ProgressionLocks(
    locked_patterns=["CS_ACCEPT", "DLG_GRATEFUL"],
    available_patterns=["CS_RESIST", "CS_PANIC", "DLG_BITTER_MONOLOGUE"],
    unlock_conditions=["trust_building_event", "reality_acceptance"]
)

# Create character
rick = CharacterState(
    character_id="rick_v1.0.0",
    name="Rick Bender",
    core_essence="cynical_former_authority_size_vulnerable",
    current_stage="denial_anger",
    voice_signature=voice,
    progression_locks=locks,
    context_modifiers={
        "size_inches": 5,
        "dependency_level": 9,
        "past_karma_weight": 10
    }
)

print(f"Created character: {rick.name} ({rick.character_id})")
```

## Development Phases

### Phase 1: Foundation (Current)
- [x] Project structure and schemas
- [x] Basic data validation
- [ ] Character-MCP implementation
- [ ] CLI interface

### Phase 2: Core MCPs
- [ ] Dynamics-MCP
- [ ] Consistency-MCP  
- [ ] Inter-MCP communication

### Phase 3: Content Generation
- [ ] Scene-MCP
- [ ] Analytics-MCP
- [ ] API endpoints

### Phase 4: Advanced Features
- [ ] World-MCP
- [ ] Web interface
- [ ] Production deployment

## Project Structure

```
narrative-mcp-system/
├── narrative_mcp/           # Main package
│   ├── mcps/               # MCP implementations
│   ├── shared/             # Shared schemas and protocols
│   ├── storage/            # Data storage
│   └── tools/              # CLI and API tools
├── tests/                  # Test suites
├── config/                 # Configuration files
├── examples/               # Usage examples
└── docs/                   # Documentation
```

## Configuration

Copy `config/default.yaml` and customize:

```yaml
# Enable/disable MCPs
mcps:
  character:
    enabled: true
    voice_analysis_model: "basic"
  consistency:
    validation_strictness: "medium"

# AI integration (optional)
ai:
  openai:
    api_key: ${OPENAI_API_KEY}
```

## Testing

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=narrative_mcp

# Run specific test
pytest tests/test_basic_setup.py::test_character_state_creation -v
```

## CLI Usage (When Implemented)

```bash
# Character operations
narrative-mcp character create --name "Rick" --essence "cynical_former_authority"
narrative-mcp character analyze --id "rick_v1.0.0" --voice-patterns

# Scene generation  
narrative-mcp scene generate --pattern "PWR_REV_KARMA" --characters "rick,candice"

# Project management
narrative-mcp project create --name "my_novel" --config ./config.json
```

## Contributing

1. Create feature branch: `git checkout -b feature/character-mcp`
2. Implement changes with tests
3. Run quality checks: `black narrative_mcp/ && mypy narrative_mcp/`
4. Submit pull request

## Development Commands

```bash
# Code formatting
black narrative_mcp/

# Type checking  
mypy narrative_mcp/

# Linting
flake8 narrative_mcp/

# Install pre-commit hooks
pre-commit install
```

## License

MIT License - see LICENSE file for details.

## Architecture Overview

The system uses a **Multi-MCP Architecture** where specialized MCPs handle different aspects of narrative management:

- **Character-MCP**: Manages personality templates and voice consistency
- **Dynamics-MCP**: Handles relationship state machines and interactions
- **Consistency-MCP**: Central coordinator ensuring narrative coherence
- **Scene-MCP**: Generates scenes from compressed pattern tokens
- **World-MCP**: Manages setting templates and world-building rules
- **Analytics-MCP**: Provides story optimization and analysis

Each MCP communicates through a standardized protocol, enabling modular development and testing.

## Next Steps

1. **Run the setup commands** to create your environment
2. **Run the tests** to verify everything works
3. **Study the schemas** in `narrative_mcp/shared/schemas.py`
4. **Implement Character-MCP** as the first functional component

For detailed implementation guidance, see the development plan in the project documentation.