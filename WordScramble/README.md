# WordScramble Game

## Class Diagram

```mermaid
classDiagram
    class Program {
        +Main(string[] args) void$
    }

    class Game {
        -WordProvider wordProvider
        -GameResult[] gameStats
        +Game()
        +ShowMenu() void
        -StartGame() void
        -ShowGameStats() void
    }

    class WordProvider {
        -List<string> words
        -Random random
        +WordProvider()
        +GetRandomWord() string
        +GetScrambledWord(string word) string
    }

    class GameResult {
        +string Word
        +double TimeTaken
        +GameResult(string word, double timeTaken)
    }

    Program --> Game : uses
    Game --> WordProvider : has
    Game --> GameResult : contains
