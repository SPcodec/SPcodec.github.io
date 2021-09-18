## Welcome to GitHub Pages

What am I doing?

### Markdown

This is a C# code I wrote to simulate the Event cards drawn in a board game called "Settlers of Catan.
There are 36 numbered cards and 1 New Year card in the deck.
The New Year card is always placed on top of 5 face down event cards. The remaining 31 event cards are placed on top of the New Year card.
At the beginning of a player's turn, they draw an Event card.
When the New Year card is drawn, all event cards are shuffled back into the deck with the New Year card on top of the 5 face down event cards and the game continues with the new deck.

```markdown
'using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;

namespace ConsoleUI
{
    class Program
    {
        static void Main(string[] args)
        {
            //List of cards
            string[] cardNum = {"2\nPlentiful Year\nEach player may take 1 resource of his choice.",
                "12\nCalm Seas\nThe player(s) with the most harbors receives 1 resource card of his choice.",
                "3\nConflict\nThe player with the \"Largest Army\" card (if not claimed, each player with the most soldier cards) takes 1 resource card at random from any one player.",
                "3","11",
                "11\nNeighborly Assistance\nThe player(s) with the most victory points give(s) each player with fewer victory points 1 resource card of his choice. If you don't have enough resources to give each eligible player 1 resource, you give no resources.",
                "4\nRobber Flees!\nThe robber returns to the desert. Do not draw a card from any player.",
                "4\nRobber Flees!\nThe robber returns to the desert. Do not draw a card from any player.",
                "4", "10", "10",
                "10\nNeighborly Assistance\nThe player(s) with the most victory points give(s) each player with fewer victory points 1 resource card of his choice. If you don't have enough resources to give each eligible player 1 resource, you give no resources.",
                "5\nTrade Advantage\nThe player with the \"Longest Road\" card (if not claimed, the player with more roads than any other player) may take one resource card from any player. You may not take a development card.",
                "5\nTournament\nThe player(s) with the most soldier cards revealed takes 1 resource of his choice from the bank.", 
                "5", "5", "9", "9", "9",
                "9\nCalm Seas\nThe player(s) with the most harbors receives 1 resource card of his choice.",
                "6\nGood Neighbours\nEach player gives the player to their left 1 resource of the giver's choice (if they have one).",
                "6\nEarthquake\nEach player turns 1 (maximum) of their roads sideways.\nYou may not build roads until your turned road is repaired. The repairs cost 1 lumber and 1 brick.\nRoads turned sideways are still counted towards the \"Longest Road\".",
                "6\nEpidemic\nEach player receives only 1 resource for each of his cities that produces this turn.", 
                "6", "6", "8", "8", "8", "8",
                "8\nEpidemic\nEach player receives only 1 resource for each of his cities that produces this turn.",
                "7\nRobber Attacks!\n1. Each player with more than 7 cards must discard half (rounded down).\n2. Move the robber. Draw a random resource card from any 1 player with a settlement and/ore city next to the robber's new hex.",
                "7\nRobber Attacks!\n1. Each player with more than 7 cards must discard half (rounded down).\n2. Move the robber. Draw a random resource card from any 1 player with a settlement and/ore city next to the robber's new hex.",
                "7\nRobber Attacks!\n1. Each player with more than 7 cards must discard half (rounded down).\n2. Move the robber. Draw a random resource card from any 1 player with a settlement and/ore city next to the robber's new hex.",
                "7\nRobber Attacks!\n1. Each player with more than 7 cards must discard half (rounded down).\n2. Move the robber. Draw a random resource card from any 1 player with a settlement and/ore city next to the robber's new hex.",
                "7\nRobber Attacks!\n1. Each player with more than 7 cards must discard half (rounded down).\n2. Move the robber. Draw a random resource card from any 1 player with a settlement and/ore city next to the robber's new hex.",
                "7\nRobber Attacks!\n1. Each player with more than 7 cards must discard half (rounded down).\n2. Move the robber. Draw a random resource card from any 1 player with a settlement and/ore city next to the robber's new hex." };

            Random rnd = new Random();
            string[] cardNumRandom = cardNum.OrderBy(x => rnd.Next()).ToArray();

            Console.WriteLine("Event cards have been shuffled.\n" +
                        "5 event cards have been placed face down with the New Year card on top.\n" +
                        "Remaining 31 cards have been placed face down on top of the New Year card to form a new draw pile.\n" +
                        "The top card will be drawn to begin the turn.\n\n" +
                        "Press Enter to draw a card.");
            Console.ReadLine();

            for (int i = 0; i < 37; i++)
            {
                if (i == 30)
                {
                    Console.WriteLine("New Year\n" +
                        "Event cards have been shuffled.\n" +
                        "5 event cards have been placed face down with the New Year card on top.\n" +
                        "Remaining 31 cards have been placed face down on top of the New Year card to form a new draw pile.\n" +
                        "The top card will be drawn to begin the turn.\n");

                    i = 0;
                    cardNumRandom = cardNum.OrderBy(x => rnd.Next()).ToArray();
                }
                Console.WriteLine(cardNumRandom[i]);
                Console.WriteLine($"There are {36-i-1} cards left in the deck.");
                Console.ReadLine();
            }
        }
    }
}'

```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/SPcodec/SPcodec.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
