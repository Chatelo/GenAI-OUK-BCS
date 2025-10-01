# Step 5 : Guess Game — Fix notes

Fixed a hint inversion where the "Too high" and "Too low" responses were swapped; messages now match the comparison logic. Also relocated misplaced comments into the relevant actors in `guess_game.jac` and `guess_game.impl.jac`. #codebase


# Step6: Adding AI support using `byllm` and openAI API.

## Setup Instructions
1. Got an OpenAI API key from [OpenAI Platform](https://platform.openai.com/api-keys) (Note: Gemini offers free keys for testing, but this project uses OpenAI)
2. Added your API key to `.env`: `OPENAI_API_KEY=api-key-here` or run in your terminal:
`OPENAI_API_KEY=api-key-here`

3. Run the game: `jac run guess_game6.jac` or in my case(in root repo of this project):
`jac serve ./2025-09-26-guessing-game/guess_game6.jac`
you should see results like this:

**Terminal Output:**

![Terminal output when serving the guessing game](images/terminal-serve.png)

**Browser Interface:**

![Browser interface showing the guessing game walker APIs](images/browser-walker-apis.png)

The game uses MTP (Meaning-Typed Programming) from the paper, where the `by llm` operator automatically generates prompts based on function signatures and types, integrating LLM calls seamlessly without manual prompt engineering.
