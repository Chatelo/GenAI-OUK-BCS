[![jac](https://img.shields.io/badge/Jaclang-0.8+-yellow.svg)](https://www.jac-lang.org/)
[![UV](https://img.shields.io/badge/UV-0.8+-violet.svg)](https://docs.astral.sh/uv/getting-started/)
[![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)](https://python.org)

# 🎮 Guessing Game with AI Hints

A fun number-guessing game built with Jaclang, featuring AI-powered hints using OpenAI's GPT-4o model.

## 📋 Table of Contents

- [Step 5: Bug Fixes](#step-5-bug-fixes)
- [Step 6: AI Integration](#step-6-ai-integration)
- [Screenshots](#screenshots)

## 🐛 Step 5: Bug Fixes

### Changes Made
- Corrected hint inversion: "Too high" and "Too low" messages now align with comparison logic.
- Moved misplaced comments to appropriate actors in `guess_game5.jac` and `guess_game5.impl.jac`.

### Testing
Run the fixed version:
```bash
cd /home/chatelo/GenAI-AI-Work/submit
uv run jac run 2025-09-26-guessing-game/guess_game5.jac
```

**Expected Behavior:**
- Guess < correct number: "Too low!"
- Guess > correct number: "Too high!"
- Guess = correct number: "Congratulations! You guessed correctly."

## 🤖 Step 6: AI Integration

Enhances the game with AI-generated hints using Jaclang's `by llm` operator and OpenAI's API.

### Setup
1. Obtain an OpenAI API key from [OpenAI Platform](https://platform.openai.com/api-keys).
   - Uses GPT-4o model.
   - Note: Gemini provides free keys, but this project requires OpenAI.

2. Configure your API key:
   - Add to `.env`:
     ```
     OPENAI_API_KEY=your_actual_api_key_here
     ```
   - Or export in terminal:
     ```bash
     export OPENAI_API_KEY=your_actual_api_key_here
     ```

3. Launch the game:
   ```bash
   # Run locally
   cd /home/chatelo/GenAI-AI-Work/submit
   uv run jac run 2025-09-26-guessing-game/guess_game6.jac
   ```

   ```bash
   # Serve as API
   uv run jac serve 2025-09-26-guessing-game/guess_game6.jac
   ```

### How It Works

Leverages **Meaning-Typed Programming (MTP)** with the `by llm` operator for seamless LLM integration:
- Automatically generates prompts from function signatures.
- Eliminates manual prompt engineering.
- Delivers dynamic, creative hints.

#### Core Code
```jac
glob llm = Model(model_name="gpt-4o", verbose=False);

"""Provide a fun hint if guess is incorrect"""
def give_hint(guess: int, correct_number: int) -> str by llm();
```

The `give_hint` function:
- Takes guess and correct number as inputs.
- Produces engaging, context-aware hints.
- Outputs strings for display.

## 📸 Screenshots

### Terminal Output
![Terminal output when serving the guessing game](images/terminal-serve.png)

### Browser Interface
![Browser interface showing the guessing game walker APIs](images/browser-walker-apis.png)

