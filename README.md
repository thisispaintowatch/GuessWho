using System;
using System.IO;

namespace GuessWho
{
    class Program
    {
        public static bool Debug = true;

        static void Main(string[] args)
        {
            // Create a CSV file to store the results
            using (var writer = File.CreateText("result.csv"))
            {
                // Loop for 1000 games
                for (int i = 0; i < 1000; i++)
                {
                    // Create a new game instance
                    var game = new Game();

                    // Play the game
                    game.PlayGame();

                    // Write the number of rounds played to the CSV file
                    writer.WriteLine(game.Rounds);
                }
            }

            Console.WriteLine("All games completed. Results saved to result.csv");
            Console.ReadLine();
        }
    }
}
