# Step 5 : Guess Game — Fix notes

Fixed a hint inversion where the "Too high" and "Too low" responses were swapped; messages now match the comparison logic. Also relocated misplaced comments into the relevant actors in `guess_game.jac` and `guess_game.impl.jac`. #codebase


#Step6

## Setup Instructions
1. Got a Gemini API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Added your API key to `.env`: `GEMINI_API_KEY=api-key-here` or run in your terminal:
`GEMINI_API_KEY=api-key-here`

3. Run the game: `jac run guess_game6.jac` or in my case(in root repo of this project):
`jac serve ./2025-09-26-guessing-game/guess_game6.jac`
you should see results like this:


The game uses MTP (Meaning-Typed Programming) from the paper, where the `by llm` operator automatically generates prompts based on function signatures and types, integrating LLM calls seamlessly without manual prompt engineering.
