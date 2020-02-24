---
title: Stimmungsanalyse über die ML.NET-Befehlszeilenschnittstelle
description: Automatisches Generieren eines ML-Modells und des zugehörigen C#-Codes aus einem Beispieldataset
author: cesardl
ms.author: cesardl
ms.date: 12/23/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: 38ca93f62a066bade988a89b704fca26368b0b2b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504161"
---
# <a name="analyze-sentiment-using-the-mlnet-cli"></a>Stimmungsanalyse über die ML.NET-Befehlszeilenschnittstelle

Erfahren Sie, wie Sie mit der ML.NET-CLI automatisch ein ML.NET-Modell und den zugrunde liegenden C#-Code generieren. Sie stellen Ihr Dataset und die Machine Learning-Aufgabe bereit, die Sie implementieren möchten, und die CLI verwendet die AutoML-Engine, um Quellcode für die Modellgenerierung und Bereitstellung sowie das Binärmodell zu erstellen.

In diesem Tutorial führen Sie die folgenden Schritte durch:
> [!div class="checklist"]
>
> - Vorbereiten der Daten für die ausgewählte Machine Learning-Aufgabe
> - Ausführen des Befehls „mlnet auto-train“ über die CLI
> - Überprüfen der Ergebnisse der Qualitätsmetriken
> - Verstehen des generierten C#-Codes zur Verwendung des Modells in Ihrer Anwendung
> - Untersuchen des generierten C#-Codes, der zum Trainieren des Modells verwendet wurde

> [!NOTE]
> Dieses Thema bezieht sich auf das ML.NET-CLI-Tools, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie auf der Seite [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).

Die ML.NET-CLI ist Teil von ML.NET und das Hauptziel ist es, ML.NET für .NET-Entwickler beim Erlernen von ML.NET zu „demokratisieren“, damit Sie den Code nicht von Grund auf neu schreiben müssen, um loszulegen.

Sie können die ML.NET-CLI über jede Eingabeaufforderung (Windows, Mac oder Linux) ausführen, um qualitativ hochwertige ML.NET-Modelle und Quellcode basierend auf den von Ihnen bereitgestellten Trainingsdatasets zu generieren.

## <a name="pre-requisites"></a>Voraussetzungen

- [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) oder höher
- (Optional) [Visual Studio 2017 oder 2019](https://visualstudio.microsoft.com/vs/)
- [ML.NET-CLI](../how-to-guides/install-ml-net-cli.md)

Sie können die generierten C#-Codeprojekte entweder über Visual Studio oder mit `dotnet run` ausführen (.NET Core-CLI).

## <a name="prepare-your-data"></a>Vorbereiten Ihrer Daten

Wir werden ein vorhandenes Dataset verwenden, das für ein Szenario „Standpunktanalyse“ verwendet wird, bei dem es sich um eine Machine Learning-Aufgabe für die binäre Klassifizierung handelt. Sie können Ihr eigenes Dataset auf ähnliche Weise verwenden, und das Modell und der Code werden für Sie generiert.

1. Laden Sie [die Dataset-ZIP-Datei „UCI Sentiment Labeled Sentences“ (siehe Zitate im folgenden Hinweis)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) herunter, und entzippen Sie sie in einem beliebigen Ordner Ihrer Wahl.

    > [!NOTE]
    > Die in diesem Tutorial verwendeten Datasets stammen aus „From Group to Individual Labels using Deep Features“, Kotzias et al,. KDD 2015, und werden im UCI Machine Learning Repository – Dua, D. und Karra Taniskidou, E. gehostet. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ]. Irvine, CA: University of California, School of Information and Computer Science.

2. Kopieren Sie die `yelp_labelled.txt`-Datei in einen vorher von Ihnen erstellten Ordner (wie z.B. `/cli-test`).

3. Öffnen Sie die von Ihnen bevorzugte Eingabeaufforderung, und wechseln Sie in den Ordner, in den Sie die Datasetdatei kopiert haben. Zum Beispiel:

    ```console
    cd /cli-test
    ```

    Sie können die Datasetdatei `yelp_labelled.txt` mit einem beliebigen Text-Editor wie beispielsweise Visual Studio Code öffnen und durchsuchen. Sie sehen folgende Struktur:

    - Die Datei hat keinen Header. Sie verwenden den Index der Spalte.

    - Es gibt nur zwei Spalten:

        | Text (Spaltenindex 0) | Bezeichnung (Spaltenindex 1)|
        |--------------------------|-------|
        | Toll... Mir hat das Restaurant gefallen. | 1 |
        | Die Kruste ist nicht gut. | 0 |
        | Sie hat nicht geschmeckt und die Textur wurde einfach unangenehm. | 0 |
        | ... VIELE WEITERE TEXTZEILEN... | ...(1 oder 0)... |

    Stellen Sie sicher, dass Sie die Datasetdatei über den Editor schließen.

    Jetzt können Sie die CLI für das Szenario „Standpunktanalyse“ verwenden.

    > [!NOTE]
    > Nach Abschluss dieses Tutorials können Sie auch eigene Datasets ausprobieren, sofern sie für die ML-Aufgaben geeignet sind, die derzeit von der ML.NET-CLI-Vorschau unterstützt werden, d.h. *„Binäre Klassifizierung“, „Multiklassenklassifizierung“ und „Regression“* ).

## <a name="run-the-mlnet-auto-train-command"></a>Ausführen des Befehls „mlnet auto-train“

1. Führen Sie den folgenden ML.NET CLI-Befehl aus:

    ```console
    mlnet auto-train --task binary-classification --dataset "yelp_labelled.txt" --label-column-index 1 --has-header false --max-exploration-time 10
    ```

    Dieser Befehl führt den **`mlnet auto-train`-Befehl** aus:
    - für eine **ML-Aufgabe** des Typs **`binary-classification`**
    - verwendet die **Datasetdatei `yelp_labelled.txt`** als Trainings- und Testdataset (intern verwendet die CLI entweder eine Kreuzvalidierung oder teilt sie in zwei Datasets, eine für das Training und eine für den Test)
    - wenn die **Objekt-/Zielspalte**, die Sie vorhersagen möchten (allgemein **Bezeichnung** genannt), die **Spalte mit dem Index 1** ist (das ist die zweite Spalte, da der Index nullbasiert ist)
    - verwendet **keinen Dateiheader** mit Spaltennamen, da diese spezielle Datasetdatei keinen Header hat
    - die **angestrebte Explorationszeit** für das Experiment beträgt **10 Sekunden**

    Die CLI-Ausgabe sieht in etwas so aus:

    <!-- markdownlint-disable MD023 MD025 -->

    # <a name="windows"></a>[Windows](#tab/windows)

    ![Befehl „auto-train“ in der ML.NET-CLI auf PowerShell](./media/mlnet-cli/mlnet-auto-train-binary-classification-powershell.gif)

    # <a name="macos-bash"></a>[MacOS-Bash](#tab/macosbash)

    ![Befehl „auto-train“ in der ML.NET-CLI auf PowerShell](./media/mlnet-cli/mlnet-auto-train-binary-classification-bash.gif)

    In diesem speziellen Fall konnte das CLI-Tool in nur 10 Sekunden und mit dem bereitgestellten kleinen Dataset eine ganze Reihe von Iterationen durchführen. Das bedeutet, dass das Training basierend auf verschiedenen Kombinationen von Algorithmen/Konfigurationen mit unterschiedlichen internen Datentransformationen und den Hyperparametern des Algorithmus mehrfach durchgeführt wurde.

    Schließlich ist das „Modell mit der besten Qualität“, das in 10 Sekunden gefunden wurde, ein Modell, das einen bestimmten Trainer/Algorithmus mit einer bestimmten Konfiguration verwendet. Je nach Explorationszeit kann der Befehl ein anderes Ergebnis liefern. Die Auswahl basiert auf den zahlreichen dargestellten Metriken, wie z.B. `Accuracy`.

    **Verstehen der Qualitätsmetriken des Modells**

    Die erste und einfachste Metrik zur Bewertung eines binären Klassifikationsmodells ist die Genauigkeit. Diese Metrik ist einfach zu verstehen. „Die Genauigkeit ist der Anteil der korrekten Vorhersagen mit einem Testdataset.“ Je näher der Wert an 100 % (1,00) liegt, desto besser.

    Es gibt jedoch Fälle, in denen das bloße Messen mit der Metrik „Accuracy“ nicht ausreicht, insbesondere wenn die Bezeichnung (in diesem Fall 0 und 1) im Testdataset unausgewogen ist.

    Weitere Metriken und **detailliertere Informationen zu den Metriken**, etwa zu „Accuracy“. „AUC“, „AUCPR“ und „F1-score“, die zur Auswertung der verschiedenen Modelle verwendet werden, finden Sie unter [Verstehen der ML.NET-Metriken](../resources/metrics.md).

    > [!NOTE]
    > Sie können genau dieses Dataset ausprobieren und für `--max-exploration-time` ein paar Minuten angeben (z.B. für drei Minuten geben Sie 180 Sekunden an). Dadurch wird mit einer anderen Konfiguration der Trainingspipeline für dieses Dataset (das ziemlich klein ist, 1.000 Zeilen) ein besseres „bestes Modell“ für Sie ermittelt.

    Um für größere Datasets ein einsatzbereites Modell mit „bester/gute Qualität“ zu finden, sollten Sie mit der CLI experimentieren, wobei in der Regel je nach Größe des Datasets viel mehr Explorationszeit angegeben wird. In der Tat kann es in vielen Fällen vorkommen, dass Sie mehrere Stunden Explorationszeit benötigen, insbesondere wenn das Dataset viele Zeilen und Spalten enthält.

1. Durch die vorherige Befehlsausführung wurden die folgenden Objekte generiert:

    - Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort verwendet werden kann.
    - C#-Code, um das generierte Modell auszuführen/zu bewerten (um mit diesem Modell Vorhersagen in Ihren Endbenutzer-Apps zu treffen).
    - C#-Trainingscode, der zur Erstellung dieses Modells verwendet wird (zu Lernzwecken).
    - Eine Protokolldatei mit allen untersuchten Iterationen mit spezifischen Detailinformationen zu jedem Algorithmus, der mit seiner Kombination aus Hyperparametern und Datentransformationen getestet wurde.

    Die ersten beiden Objekte (ZIP-Datei des Modells und der C#-Code zur Ausführung des Modells) können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem generierten ML-Modell Vorhersagen zu treffen.

    Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie untersuchen können, welchen spezifischen Trainer/Algorithmus und Hyperparameter die CLI ausgewählt hat.

Die aufgezählten Objekte werden in den folgenden Schritten des Tutorials erläutert.

## <a name="explore-the-generated-c-code-to-use-for-running-the-model-to-make-predictions"></a>Erkunden des generierten C#-Codes, der für die Ausführung des Modells zum Treffen von Vorhersagen verwendet werden kann

1. Öffnen Sie in Visual Studio (2017 oder 2019) die Projektmappe, die in dem Ordner mit dem Namen `SampleBinaryClassification` in Ihrem ursprünglichen Zielordner generiert wurde (im Tutorial wurde der Name `/cli-test` verwendet). Die angezeigte Projektmappe sollte ungefähr so aussehen:

    > [!NOTE]
    > Im Tutorial empfehlen wir die Verwendung von Visual Studio. Sie können aber auch den generierten C#-Code (zwei Projekte) mit einem beliebigen Text-Editor untersuchen und die generierte Konsolen-App mit der `dotnet CLI` auf MacOS-, Linux- oder Windows-Computern ausführen.

    ![Von der CLI generierte VS-Projektmappe](./media/mlnet-cli/generated-csharp-solution-detailed.png)

    - Die generierte **Klassenbibliothek**, die das serialisierte ML-Modell (ZIP-Datei) und die Datenklassen (Datenmodelle) enthält, können Sie direkt in Ihrer Endbenutzeranwendung verwenden, auch wenn Sie direkt auf diese Klassenbibliothek verweisen (oder den Code verschieben, ganz wie Sie möchten).
    - Die generierte **Konsolen-App** enthält Ausführungscode, den Sie überprüfen müssen. Dann wird der „Bewertungscode“ (Code, der das ML-Modell ausführt, um Vorhersagen zu treffen) in der Regel wiederverwendet, indem Sie diesen einfachen Code (nur ein paar Zeilen) in Ihre Endbenutzeranwendung verschieben, wo Sie die Vorhersagen machen möchten.

1. Öffnen Sie die Klassendateien **ModelInput.cs** und **ModelOutput.cs** im Klassenbibliotheksprojekt. Sie sehen, dass diese Klassen „Datenklassen“ oder POCO-Klassen sind, die zum Speichern von Daten verwendet werden. Es handelt sich um einen "Textbausteincode", dessen Generierung jedoch sinnvoll ist, wenn Ihr Dataset Dutzende oder sogar Hunderte von Spalten enthält.
    - Die `ModelInput`-Klasse wird beim Auslesen von Daten aus dem Dataset verwendet.
    - Die `ModelOutput`-Klasse wird verwendet, um das Vorhersageergebnis (Vorhersagedaten) abzurufen.

1. Öffnen Sie die Datei „Program.cs“, und untersuchen Sie den Code. Mit nur wenigen Zeilen können Sie das Modell ausführen und eine Beispielvorhersage treffen.

    ```csharp
    static void Main(string[] args)
    {
        MLContext mlContext = new MLContext();

        // Training code used by ML.NET CLI and AutoML to generate the model
        //ModelBuilder.CreateModel();

        ITransformer mlModel = mlContext.Model.Load(MODEL_FILEPATH, out DataViewSchema inputSchema);
        var predEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // Create sample data to do a single prediction with it
        ModelInput sampleData = CreateSingleDataSample(mlContext, DATA_FILEPATH);

        // Try a single prediction
        ModelOutput predictionResult = predEngine.Predict(sampleData);

        Console.WriteLine($"Single Prediction --> Actual value: {sampleData.Label} | Predicted value: {predictionResult.Prediction}");
    }
    ```

    - Die erste Zeile des Codes erstellt einfach ein `MLContext`-Objekt, das bei der Ausführung von ML.NET-Code benötigt wird.

    - Die zweite Codezeile wird auskommentiert, da Sie das Modell nicht trainieren müssen, da es bereits vom CLI-Tool für Sie trainiert und in der serialisierten ZIP-Datei des Modells gespeichert wurde. Wenn Sie jedoch sehen möchten, *„wie das Modell von der CLI trainiert wurde“* , können Sie die Auskommentierung dieser Zeile aufheben und den für dieses spezielle ML-Modell verwendeten Trainingscode ausführen/debuggen.

    - In der dritten Zeile des Codes laden Sie das Modell mit der `mlContext.Model.Load()`-API aus der serialisierten ZIP-Datei des Modells, indem Sie den Pfad zu dieser Datei angeben.

    - In der vierten Codezeile, die Sie laden, erstellen Sie das `PredictionEngine`-Objekt mit der `mlContext.Model.CreatePredictionEngine<TSrc,TDst>(ITransformer mlModel)`-API. Sie benötigen das `PredictionEngine`-Objekt, wenn Sie eine Vorhersage für ein einzelnes Datenbeispiel erstellen möchten (in diesem Fall ein einzelnes Textstück, um dessen Standpunkt vorherzusagen).

    - In der fünften Zeile des Codes erstellen Sie die *einzelnen Beispieldaten*, die für die Vorhersage verwendet werden sollen, indem Sie die Funktion `CreateSingleDataSample()` aufrufen. Da das CLI-Tool nicht weiß, welche Art von Beispieldaten verwendet werden sollen, lädt es innerhalb dieser Funktion die erste Zeile des Datasets. Für diesen Fall können Sie jedoch auch eigene „hartcodierten“ Daten anstelle der aktuellen Implementierung der Funktion `CreateSingleDataSample()` erstellen, indem Sie diesen einfacheren Code aktualisieren, der diese Funktion implementiert:

        ```csharp
        private static ModelInput CreateSingleDataSample()
        {
            ModelInput sampleForPrediction = new ModelInput() { Col0 = "The ML.NET CLI is great for getting started. Very cool!", Label = true };
            return sampleForPrediction;
        }
        ```

1. Führen Sie das Projekt entweder mit den ursprünglichen Beispieldaten aus der ersten Zeile des Datasets oder mit Ihren eigenen, hartcodierten Beispieldaten aus. Die Vorhersage sollte ungefähr so aussehen:

    # <a name="windows"></a>[Windows](#tab/windows)

    Führen Sie die Konsolen-App über Visual Studio durch Drücken auf F5 („Wiedergabe“) aus:

    ![Befehl „auto-train“ in der ML.NET-CLI auf PowerShell](./media/mlnet-cli/sample-cli-prediction-execution.png))

    # <a name="macos-bash"></a>[MacOS-Bash](#tab/macosbash)

    Führen Sie die Konsolen-App über die Eingabeaufforderung aus, indem Sie die folgenden Befehle eingeben:

    ```dotnetcli
    cd SampleBinaryClassification
    cd SampleBinaryClassification.ConsoleApp

    dotnet run
    ```

    ![Befehl „auto-train“ in der ML.NET-CLI auf PowerShell](./media/mlnet-cli/sample-cli-prediction-execution-bash.png))

    ---

1. Versuchen Sie, die hartcodierten Beispieldaten in andere Sätze mit verschiedenen Standpunkten zu ändern, und schauen Sie sich an, wie das Modell positive oder negative Standpunkte vorhersagt.

## <a name="infuse-your-end-user-applications-with-ml-model-predictions"></a>Ergänzen Ihrer Endbenutzeranwendungen mit ML-Modellvorhersagen

Sie können einen ähnlichen „Bewertungscode für das ML-Modell“ verwenden, um das Modell in Ihrer Endbenutzeranwendung auszuführen und Vorhersagen zu treffen.

Beispielsweise können Sie diesen Code direkt in eine beliebige Windows-Desktop-Anwendung wie **WPF** und **WinForms** verschieben und das Modell auf die gleiche Weise ausführen wie in der Konsolen-App.

Die Art und Weise, wie Sie diese Codezeilen zur Ausführung des ML-Modells implementieren, sollte jedoch optimiert werden (d.h. die ZIP-Datei des Modells zwischenspeichern und einmal laden) und Sie sollten Singleton-Objekte verwenden, anstatt sie bei jeder Anforderung zu erstellen, insbesondere wenn Ihre Anwendung skalierbar sein muss, wie beispielsweise eine Webanwendung oder ein verteilter Dienst, wie im folgenden Abschnitt erläutert.

### <a name="running-mlnet-models-in-scalable-aspnet-core-web-apps-and-services-multi-threaded-apps"></a>Ausführen von ML.NET Modellen in skalierbaren ASP.NET Core-Web-Apps und -Diensten (Multithread-Apps)

Die Erstellung des Modellobjekts (`ITransformer`, das aus der ZIP-Datei eines Modells geladen wurde) und des `PredictionEngine`-Objekts sollte optimiert werden, insbesondere bei der Ausführung auf skalierbaren Web-Apps und verteilten Diensten. Für den ersten Fall, das Modellobjekt (`ITransformer`), ist die Optimierung einfach. Da das `ITransformer`-Objekt threadsicher ist, können Sie das Objekt als Singleton-Objekt oder statisches Objekt zwischenspeichern und das Modell einmal laden.

Für das zweite Objekt, das `PredictionEngine`-Objekt, ist es nicht so einfach, da das `PredictionEngine`-Objekt nicht threadsicher ist. Daher können Sie dieses Objekt nicht als Singleton- oder statisches Objekt in einer ASP.NET Core-App instanziieren. Dieses Problem der Threadsicherheit und Skalierbarkeit wird in diesem [Blogbeitrag](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/) ausführlich behandelt.

Allerdings ist die Praxis für Sie heute wesentlich einfacher, als in diesem Blogbeitrag beschrieben. Wir haben für Sie einen einfacheren Ansatz erarbeitet und ein praktisches **.NET Core-Integrationspaket** erstellt, das Sie problemlos in Ihren ASP.NET Core-Apps und -Diensten verwenden können, indem Sie es in den DI-Diensten der Anwendung (Dependency Injection Services) registrieren und dann direkt über Ihren Code verwenden. Schauen Sie sich dafür das folgende Tutorial und Beispiel an:

- [Tutorial: Ausführen von ML.NET-Modellen auf skalierbaren ASP.NET Core-Web-Apps und -Web-APIs](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [Beispiel: Skalierbares ML.NET-Modell auf ASP.NET Core-Web-API](https://aka.ms/mlnet-sample-netcoreintegrationpkg)

## <a name="explore-the-generated-c-code-that-was-used-to-train-the-best-quality-model"></a>Untersuchen des generierten C#-Codes, der zum Trainieren des „Modell mit der besten Qualität“ verwendet wurde

Für weiterführende Lernzwecke können Sie auch den generierten C#-Code untersuchen, der vom CLI-Tool zum Trainieren des generierten Modells verwendet wurde.

Dieser „Code des Trainingsmodells“ wird derzeit in der generierten benutzerdefinierten Klasse namens `ModelBuilder` generiert, sodass Sie diesen Trainingscode untersuchen können.

Noch wichtiger ist, dass Sie diesen generierten Trainingscode in diesem speziellen Szenario (Modell zur Standpunktanalyse) auch mit dem im folgenden Tutorial beschriebenen Code vergleichen können:

- Vergleich: [Tutorial: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung](sentiment-analysis.md).

Es ist interessant, den gewählten Algorithmus und die Pipelinekonfiguration im Tutorial mit dem vom CLI-Tool generierten Code zu vergleichen. Je nachdem, wie viel Zeit Sie mit der Iteration und der Suche nach besseren Modellen verbringen, können der ausgewählte Algorithmus, die jeweiligen Hyperparametern und die Pipelinekonfiguration jeweils unterschiedlich sein.

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Vorbereiten der Daten für die ausgewählte ML-Aufgabe (zu lösendes Problem)
> - Ausführen des Befehls „mlnet auto-train“ über das CLI-Tool
> - Überprüfen der Ergebnisse der Qualitätsmetriken
> - Verstehen des generierten C#-Codes zur Ausführung des Modells (Code zur Verwendung in Ihrer Endbenutzer-App)
> - Untersuchen des generierten C#-Codes, der zum Trainieren des „Modell mit der besten Qualität“ verwendet wurde (zu Lernzwecken)

## <a name="see-also"></a>Siehe auch

- [Automatisieren des Modelltrainings mit der ML.NET-CLI](../automate-training-with-cli.md)
- [Tutorial: Ausführen von ML.NET-Modellen auf skalierbaren ASP.NET Core-Web-Apps und -Web-APIs](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [Beispiel: Skalierbares ML.NET-Modell auf ASP.NET Core-Web-API](https://aka.ms/mlnet-sample-netcoreintegrationpkg)
- [Referenzhandbuch für den „auto-train“-Befehl in der ML.NET-CLI](../reference/ml-net-cli-reference.md)
- [Telemetrie in der ML.NET-CLI](../resources/ml-net-cli-telemetry.md)
