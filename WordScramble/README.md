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
        -List<string> presentedWords
        +Game()
        +ShowMenu() void
        -StartGame() void
        -ShowGameStats() void
        -ShowBreakdownChart() void
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

    Program *-- Game : creates
    Game *-- WordProvider : has
    Game o-- GameResult : contains
