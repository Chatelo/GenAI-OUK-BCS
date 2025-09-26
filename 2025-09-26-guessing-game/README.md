# Step 5 : Guess Game — Fix notes

Fixed a hint inversion where the "Too high" and "Too low" responses were swapped; messages now match the comparison logic. Also relocated misplaced comments into the relevant actors in `guess_game.jac` and `guess_game.impl.jac`. #codebase


#Step6

## Setup Instructions
4. Got a Gemini API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
5. Added your API key to `.env`: `GEMINI_API_KEY=api-key-here`
6. Run the game: `jac run guess_game6.jac`

The game uses MTP (Meaning-Typed Programming) from the paper, where the `by llm` operator automatically generates prompts based on function signatures and types, integrating LLM calls seamlessly without manual prompt engineering.
