---
title: 'Infer.NET-App zum Erstellen einer Spielerrangliste: probabilistische Programmierung'
description: Finden Sie heraus, wie Sie die probabilistische Programmierung mit Infer.NET verwenden können, um eine App für eine Spielerrangliste anhand der Auswertung von Spielpartien zu erstellen, die auf einer vereinfachten Version von TrueSkill basiert.
ms.date: 01/30/2020
ms.custom: mvc,how-to
ms.openlocfilehash: 8e489d61c5e6cca53ba12b13fddd0b73c7f85ef9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092602"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a>Erstellen einer App für eine Spielerrangliste anhand der Auswertung von Spielpartien mit Infer.NET und probabilistischer Programmierung

In dieser Schrittanleitung erfahren Sie mehr zur probabilistischen Programmierung mithilfe von Infer.NET. Die probabilistische Programmierung ist ein Ansatz des maschinellen Lernens, bei dem benutzerdefinierte Modelle als Computerprogramme ausgedrückt werden. Dieser Ansatz ermöglicht es, Wissen auf einem bestimmten Fachgebiet in die Modelle zu integrieren, und sorgt dafür, dass sich das System für maschinelles Lernen besser interpretieren lässt. Der Ansatz unterstützt auch direkte Rückschlüsse – also den Prozess des Lernens beim Eintreffen neuer Daten. Infer.NET wird in verschiedenen Microsoft-Produkten in Azure, Xbox und Bing eingesetzt.

## <a name="what-is-probabilistic-programming"></a>Was ist die probabilistische Programmierung?

Mit der probabilistischen Programmierung können wir statistische Modelle aus Prozessen der realen Welt erstellen.

## <a name="prerequisites"></a>Voraussetzungen

- Einrichten der lokalen Entwicklungsumgebung

  Für diese Schrittanleitung wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können. Im .NET-Tutorial [Hallo Welt in zehn Minuten](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) finden Sie eine Anleitung zum Einrichten Ihrer lokalen Entwicklungsumgebung unter macOS, Windows oder Linux.

## <a name="create-your-app"></a>Erstellen der App

1. Öffnen Sie eine neue Eingabeaufforderung, und führen Sie die folgenden Befehle aus:

```dotnetcli
dotnet new console -o myApp
cd myApp
```

Der `dotnet`-Befehl erstellt eine `new`-Anwendung des Typs `console`. Der `-o`-Parameter erstellt ein Verzeichnis namens `myApp`, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf. Mit dem `cd myApp`-Befehl wechseln Sie in das neu erstellte App-Verzeichnis.

## <a name="install-infernet-package"></a>Installieren des Infer.NET-Pakets

Um Infer.NET verwenden zu können, müssen Sie das `Microsoft.ML.Probabilistic.Compiler`-Paket installieren. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:

```dotnetcli
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a>Entwerfen des Modells

Das Beispiel verwendet Tischtennis- oder Fußballspiele, die im Büro ausgetragen wurden. Sie kennen die Teilnehmer und das Ergebnis jedes Spiels.  Aus diesen Daten möchten Sie die Fähigkeiten jedes Spielers ableiten. Wir nehmen an, dass die latenten Fähigkeiten jedes Spielers normal verteilt sind und dass die Leistung in einem bestimmten Spiel eine abweichende Version dieser Fähigkeiten darstellt. Die Daten legen nahe, dass die Leistung des Gewinners besser ist als die Leistung des Verlierers. Dies ist eine vereinfachte Version des beliebten [TrueSkill](https://www.microsoft.com/research/project/trueskill-ranking-system/)-Modells, das auch Teams, Unentschieden und andere Erweiterungen unterstützt. Eine [erweiterte Version](https://www.microsoft.com/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) dieses Modells wird für die Spielergebnisse in den sehr erfolgreichen Spielen „Halo“ und „Gears of War“ verwendet.

Sie müssen die abgeleiteten Fähigkeiten jedes Spielers sowie die Varianz auflisten – das Maß für Ungewissheit in Bezug auf die Fähigkeiten.

*Beispieldaten für Spielergebnisse*

Spiel |Gewinner | Verlierer
---------|----------|---------
 1 | Spieler 0 | Spieler 1
 2 | Spieler 0 | Spieler 3
 3 | Spieler 0 | Spieler 4
 4 | Spieler 1 | Spieler 2
 5 | Spieler 3 | Spieler 1
 6 | Spieler 4 | Spieler 2

Wenn Sie sich die Beispieldaten genau ansehen, werden Sie feststellen, dass die Spieler 3 und 4 jeweils einen Sieg und eine Niederlage zu verzeichnen haben. Sehen wir uns jetzt mithilfe der probabilistischen Programmierung an, wie die Rangfolgen aussehen. Beachten Sie, dass es auch einen Spieler 0 (null) gibt, weil sogar Ranglisten für Bürospiele für uns Entwickler nullbasiert sind.

## <a name="write-some-code"></a>Schreiben von Code

Nachdem wir das Modell konzipiert haben, ist es jetzt an der Zeit, es mithilfe der Modellierungs-API von Infer.NET als probabilistisches Programm auszudrücken. Öffnen Sie `Program.cs` in Ihrem bevorzugten Text-Editor, und ersetzen Sie den gesamten Inhalt durch folgenden Code:

```csharp
namespace myApp

{
    using System;
    using System.Linq;
    using Microsoft.ML.Probabilistic;
    using Microsoft.ML.Probabilistic.Distributions;
    using Microsoft.ML.Probabilistic.Models;

    class Program
    {

        static void Main(string[] args)
        {
            // The winner and loser in each of 6 samples games
            var winnerData = new[] { 0, 0, 0, 1, 3, 4 };
            var loserData = new[] { 1, 3, 4, 2, 1, 2 };

            // Define the statistical model as a probabilistic program
            var game = new Range(winnerData.Length);
            var player = new Range(winnerData.Concat(loserData).Max() + 1);
            var playerSkills = Variable.Array<double>(player);
            playerSkills[player] = Variable.GaussianFromMeanAndVariance(6, 9).ForEach(player);

            var winners = Variable.Array<int>(game);
            var losers = Variable.Array<int>(game);

            using (Variable.ForEach(game))
            {
                // The player performance is a noisy version of their skill
                var winnerPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[winners[game]], 1.0);
                var loserPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[losers[game]], 1.0);

                // The winner performed better in this game
                Variable.ConstrainTrue(winnerPerformance > loserPerformance);
            }

            // Attach the data to the model
            winners.ObservedValue = winnerData;
            losers.ObservedValue = loserData;

            // Run inference
            var inferenceEngine = new InferenceEngine();
            var inferredSkills = inferenceEngine.Infer<Gaussian[]>(playerSkills);

            // The inferred skills are uncertain, which is captured in their variance
            var orderedPlayerSkills = inferredSkills
               .Select((s, i) => new { Player = i, Skill = s })
               .OrderByDescending(ps => ps.Skill.GetMean());

            foreach (var playerSkill in orderedPlayerSkills)
            {
                Console.WriteLine($"Player {playerSkill.Player} skill: {playerSkill.Skill}");
            }
        }
    }
}
```

## <a name="run-your-app"></a>Ausführen der App

Führen Sie an der Eingabeaufforderung folgenden Befehl aus:

```dotnetcli
dotnet run
```

## <a name="results"></a>Ergebnisse

Die Ergebnisse sollten den hier dargestellten ähneln:

```console
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

Beachten Sie bei den Ergebnissen, dass Spieler 3 gemäß unserem Modell etwas höher rangiert als Spieler 4. Das liegt daran, dass der Sieg von Spieler 3 über Spieler 1 signifikanter ist als der Sieg von Spieler 4 über Spieler 2 – beachten Sie, dass Spieler 1 gegen Spieler 2 gewonnen hat. Spieler 0 ist der Gesamtsieger!

## <a name="keep-learning"></a>Weiterlernen

Das Konzipieren von statistischen Modellen ist eine Kunst für sich. Das Microsoft Research Cambridge-Team hat ein [kostenloses Onlinebuch](http://mbmlbook.com/) herausgebracht, das eine behutsame Einführung zum Thema bietet. In Kapitel 3 wird das TrueSkill-Modell ausführlicher behandelt. Wenn Sie ein Modell entwickelt haben, können Sie es mithilfe der [umfangreichen Dokumentation](https://dotnet.github.io/infer/) auf der Website von Infer.NET in Code transformieren.

## <a name="next-steps"></a>Nächste Schritte

Im GitHub-Repository zu Infer.NET können Sie mit dem Lernen fortfahren und weitere Beispiele finden.
> [!div class="nextstepaction"]
> [GitHub-Repository zu dotnet/infer](https://github.com/dotnet/infer)
