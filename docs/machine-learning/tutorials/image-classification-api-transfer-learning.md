---
title: 'Tutorial: Automatisierte visuelle Überprüfung mithilfe von Transferlernen'
description: In diesem Tutorial wird gezeigt, wie Sie anhand von Transferlernen ein TensorFlow-Modell mit Deep Learning in ML.NET mit der Bilderkennungs-API trainieren, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.
author: luisquintanilla
ms.author: luquinta
ms.date: 10/25/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b8aec80134188811eb80ad1394e5a64d65a3c6f0
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961953"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a>Tutorial: Automatisierte visuelle Überprüfung mithilfe von Transferlernen mit der ML.NET-Bildklassifizierungs-API

Erfahren Sie, wie Sie ein benutzerdefiniertes Deep-Learning-Modell mithilfe von Transferlernen, einem vorab trainierten TensorFlow-Modell und der ML.NET-Bildklassifizierungs-API trainieren, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.

> [!NOTE]
> In diesem Tutorial wird eine Vorschauversion der ML.NET-Bildklassifizierungs-API verwendet.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Das Problem verstehen
> - Informationen zur ML.NET-Bildklassifizierungs-API
> - Grundlegendes zum vorab trainierten Modell
> - Trainieren eines benutzerdefinierten TensorFlow-Bildklassifizierungsmodells mithilfe von Transferlernen
> - Klassifizieren von Bildern mit dem benutzerdefinierten Modell

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

## <a name="image-classification-transfer-learning-sample-overview"></a>Beispielübersicht zur Bildklassifizierung mit Transferlernen

Bei diesem Beispiel handelt es sich um eine C#.NET Core-Konsolenanwendung, die Bilder mit einem vorab mit Deep Learning trainierten TensorFlow-Modell klassifiziert. Den Code für dieses Beispiel finden Sie im [dotnet/machinelearning-Beispielrepository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) auf GitHub.

## <a name="understand-the-problem"></a>Das Problem verstehen

Bildklassifizierung ist ein Problem des maschinellen Sehens. Bei der Bildklassifizierung wird ein Bild eingegeben, das dann in eine bestimmte Klasse eingeordnet wird. Die Bildklassifizierung kann zum Beispiel in diesen Szenarios hilfreich sein:

- Gesichtserkennung
- Emotionserkennung
- Medizinische Diagnose
- Orientierungspunkterkennung

In diesem Tutorial wird ein benutzerdefiniertes Bildklassifizierungsmodell trainiert, um eine automatisierte visuelle Überprüfung von Brückenbelägen durchzuführen, bei der durch Risse unterbrochene Strukturen identifiziert werden.

## <a name="mlnet-image-classification-api"></a>ML.NET-Bildklassifizierungs-API

ML.NET bietet verschiedene Methoden zum Durchführen einer Bildklassifizierung. In diesem Tutorial wird die Methode des Transferlernens unter Verwendung der Bildklassifizierungs-API angewendet. Die Bildklassifizierungs-API nutzt [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), eine Low-Level-Bibliothek, die C#-Bindungen für die TensorFlow-C++-API bereitstellt.

## <a name="what-is-transfer-learning"></a>Was ist Übertragungslernen?

Beim Transferlernen werden Erkenntnisse aus der Lösung eines Problems für ein anderes verwandtes Problem genutzt.

Das von Grund auf neue Trainieren eines Deep-Learning-Modells erfordert das Festlegen mehrerer Parameter, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden). Die Verwendung eines vorab trainierten Modells zusammen mit dem Transferlernen ermöglicht es Ihnen, den Trainingsprozess zu verkürzen. 

## <a name="training-process"></a>Trainingsprozess

Die Bildklassifizierungs-API startet den Trainingsprozess, indem das vorab trainierte TensorFlow-Modell geladen wird. Der Trainingsprozess setzt sich aus zwei Schritten zusammen:

1. Engpassphase
2. Trainingsphase

![Trainingsschritte](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a>Engpassphase

Während der Engpassphase werden die Trainingsbilder geladen, wobei die Pixelwerte als Eingabe dienen, oder aber Features für die fixierten Ebenen des vorab trainierten Modells. Die fixierten Ebenen umfassen sämtliche Ebenen im neuronalen Netz bis hin zur vorletzte Ebene, die inoffiziell auch als Engpassebene bezeichnet wird. Diese Ebenen werden „fixiert“ genannt, da für diese kein Training stattfindet und Vorgänge lediglich weitergegeben werden. In diesen fixierten Ebenen werden die zugrunde liegenden Muster berechnet, anhand derer ein Modell zwischen den verschiedenen Klassen unterscheidet. Je mehr Ebenen es gibt, desto rechenintensiver ist dieser Schritt. Da es sich hierbei um eine einmalige Berechnung handelt, können die Ergebnisse zwischengespeichert und in späteren Durchläufen verwendet werden, wenn mit verschiedenen Parametern experimentiert wird.

### <a name="training-phase"></a>Trainingsphase

Sobald die Ausgabewerte aus der Engpassphase berechnet sind, dienen sie als Eingabe für das nochmalige Training der letzten Ebene des Modells. Dieser Prozess ist iterativ und wird so oft ausgeführt, wie durch Modellparameter angegeben ist. Bei jeder Ausführung werden Verlust und Genauigkeit ausgewertet. Anschließend werden die entsprechenden Anpassungen zur Verbesserung des Modells vorgenommen, um so den Verlust zu minimieren und die Genauigkeit zu maximieren. Nach Abschluss des Trainings verfügen Sie über zwei Modellformate. Eines wird als `.pb`-Version des Modells und das andere als für ML.NET serialisierte `.zip`-Version des Modells bezeichnet. Für die Arbeit in von ML.NET unterstützten Umgebungen wird die `.zip`-Version des Modells empfohlen. In Umgebungen, in denen ML.NET nicht unterstützt wird, haben Sie jedoch die Möglichkeit, die `.pb`-Version zu verwenden.

## <a name="understand-the-pretrained-model"></a>Grundlegendes zum vorab trainierten Modell

Das in diesem Tutorial verwendete vorab trainierte Modell ist die 101-Ebenen-Variante des Modells „Residual Network (ResNet) v2“. Das Originalmodell ist darauf trainiert, Bilder in tausend Kategorien einzuteilen. Das Modell verwendet ein Bild der Größe 224 × 224 als Eingabe und gibt die Klassenwahrscheinlichkeiten für jede der Klassen aus, für die es trainiert ist. Ein Teil dieses Modells wird verwendet, um ein neues Modell mit benutzerdefinierten Bildern zu trainieren, damit dieses Vorhersagen für zwei Klassen treffen kann. 

## <a name="create-console-application"></a>Erstellen einer Konsolenanwendung

Nachdem Sie nun grundlegende Kenntnisse über das Transferlernen und die Bildklassifizierungs-API haben, ist es an der Zeit, die Anwendung zu erstellen.

1. Erstellen Sie eine **.NET Core-Konsolenanwendung in C#** namens „DeepLearning_ImageClassification_Binary“.
1. Installieren Sie das NuGet-Paket **Microsoft.ML 1.4.0-preview2**:
    1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.
    1. Wählen Sie als Paketquelle „nuget.org“ aus.
    1. Wählen Sie die Registerkarte **Durchsuchen** aus.
    1. Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**.
    1. Suchen Sie nach **Microsoft.ML**.
    1. Wählen Sie die Schaltfläche **Installieren** aus.
    1. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.
    1. Wiederholen Sie die Schritte für **Microsoft.ML.Dnn 0.16.0-preview2** und **Microsoft.ML.ImageAnalytics 1.4.0-preview2**.

### <a name="prepare-and-understand-the-data"></a>Vorbereiten und Verstehen der Daten

> [!NOTE]
> Die Datasets für dieses Tutorial stammen von Marc Maguire, Sattar Dorafshan und Robert J. Thomas, „SDNET2018: A concrete crack image dataset for machine learning applications“ (2018). Durchsuchen Sie alle Datasets. Dokument 48. https://digitalcommons.usu.edu/all_datasets/48

SDNET2018 ist ein Bilddataset, das Anmerkungen für gerissene und nicht gerissene Betonstrukturen (Brückenbeläge, Mauern und Gehwege) enthält. 

![Beispiele für Brückenbeläge des SDNET2018-Datasets](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

Die Daten sind in drei Unterverzeichnissen organisiert:

- D enthält Bilder von Brückenbelägen
- P enthält Bilder von Gehwegen
- W enthält Bilder von Mauern

Jedes dieser Unterverzeichnisse enthält zwei zusätzliche Unterverzeichnisse mit Präfixen:

- C ist das Präfix für gerissene Oberflächen
- U ist das Präfix für nicht gerissene Oberflächen

In diesem Tutorial werden ausschließlich Bilder von Brückenbelägen verwendet.

1. Laden Sie das [Dataset](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) herunter, und entpacken Sie es.
1. Erstellen Sie in Ihrem Projekt ein Verzeichnis mit dem Namen „assets“, um darin die Datasetdateien zu speichern.
1. Kopieren Sie die Unterverzeichnisse *CD* und *UD* aus dem zuletzt entpackten Verzeichnis in das Verzeichnis *assets*.

### <a name="create-input-and-output-classes"></a>Erstellen von Eingabe- und Ausgabeklassen

1. Öffnen Sie die Datei *Program.cs*, und ersetzen Sie die vorhandenen `using`-Anweisungen am Anfang der Datei durch die folgenden Anweisungen:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L1-L7)]

1. Erstellen Sie in der Datei *Program.cs* unter der `Program`-Klasse eine Klasse mit dem Namen `ImageData`. Diese Klasse wird verwendet, um die ursprünglich geladenen Daten darzustellen. 

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L135-L140)]

    `ImageData` enthält die folgenden Eigenschaften:

    - `ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist.
    - `Label` ist die Kategorie, zu der das Bild gehört. Dies ist der vorherzusagende Wert.

1. Erstellen Sie Klassen für Ihre Eingabe- und Ausgabedaten.

    1. Definieren Sie unter der `ImageData`-Klasse das Schema Ihrer Eingabedaten in einer neuen Klasse namens `ModelInput`.

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L142-L151)]

        `ModelInput` enthält die folgenden Eigenschaften:

        - `ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist. 
        - `Label` ist die Kategorie, zu der das Bild gehört. Dies ist der vorherzusagende Wert.
        - `Image` ist die `byte[]`-Darstellung des Bilds. Bei dem Modell wird erwartet, dass Bilddaten diesen Typ für das Training aufweisen.
        - `LabelAsKey` ist die numerische Darstellung von `Label`. 

        Nur `Image` und `LabelAsKey` werden verwendet, um das Modell zu trainieren und Vorhersagen zu treffen. Die Eigenschaften `ImagePath` und `Label` werden beibehalten, damit einfacher auf den Namen und die Kategorie der ursprünglichen Bilddatei zugegriffen werden kann.

    1. Anschließend definieren Sie unter der `ModelInput`-Klasse das Schema Ihrer Ausgabedaten in einer neuen Klasse namens `ModelOutput`. 

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L153-L160)]

        `ModelOutput` enthält die folgenden Eigenschaften:

        - `ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist.
        - `Label` ist die ursprüngliche Kategorie, zu der das Bild gehört. Dies ist der vorherzusagende Wert. 
        - `PredictedLabel` ist der vom Modell vorhergesagte Wert.

        Ähnlich wie bei `ModelInput` ist nur `PredictedLabel` für Vorhersagen erforderlich, da dies die vom Modell getroffene Vorhersage enthält. Die Eigenschaften `ImagePath` und `Label` werden beibehalten, damit einfacher auf den Namen und die Kategorie der ursprünglichen Bilddatei zugegriffen werden kann.

### <a name="define-paths-and-initialize-variables"></a>Definieren von Pfaden und Initialisieren von Variablen

1. Definieren Sie innerhalb der `Main`-Methode den Speicherort Ihrer Objekte.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L15-L16)]

1. Initialisieren Sie dann die `mlContext`-Variable mit einer neuen Instanz von [MLContext](xref:Microsoft.ML.MLContext).

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L18)]

Die [MLContext](xref:Microsoft.ML.MLContext)-Klasse ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von MLContext wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

## <a name="load-the-data"></a>Laden der Daten

### <a name="create-data-loading-utility-method"></a>Erstellen einer Hilfsmethode zum Laden von Daten

Die Bilder werden in zwei Unterverzeichnissen gespeichert. Vor dem Laden der Daten müssen diese in eine Liste mit `ImageData`-Objekten formatiert werden. Erstellen Sie hierzu die `LoadImagesFromDirectory`-Methode unter der `Main`-Methode.

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. Fügen Sie in `LoadImagesDirectory` den folgenden Code hinzu, um alle Dateipfade aus den Unterverzeichnissen abzurufen:

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L102-L103)]

1. Durchlaufen Sie dann die einzelnen Dateien mithilfe einer `foreach`-Anweisung.

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. Überprüfen Sie, ob in der `foreach`-Anweisung die Dateierweiterungen unterstützt werden. Die Bildklassifizierungs-API unterstützt JPEG- und PNG-Formate.

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L107-L108)]

1. Rufen Sie anschließend die Bezeichnung für die Datei ab. Wenn der `useFolderNameAsLabel`-Parameter auf `true` festgelegt ist, wird das übergeordnete Verzeichnis, in dem die Datei gespeichert wird, als Bezeichnung verwendet. Andernfalls wird erwartet, dass die Bezeichnung ein Präfix des Dateinamens oder der Dateiname selbst ist.

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L110-L124)]

1. Abschließend erstellen Sie eine neue Instanz von `ModelInput`.

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L126-L130)]

### <a name="prepare-the-data"></a>Vorbereiten der Daten

1. Verwenden Sie in der `Main`-Methode die `LoadFromDirectory`-Hilfsmethode, um die Liste der Bilder abzurufen, die für das Training verwendet werden.

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L20)]

1. Laden Sie dann die Bilder mithilfe der [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)-Methode in eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle.

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L22)]    

1. Die Daten werden in der Reihenfolge geladen, in der sie aus den Verzeichnissen gelesen wurden. Um die Daten auszugleichen, mischen Sie sie zufällig mithilfe der [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*)-Methode.

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L24)]

1. Bei Modellen für maschinelles Lernen wird eine Eingabe im numerischen Format erwartet. Daher muss vor dem Training eine Vorverarbeitung der Daten durchgeführt werden. Erstellen Sie eine [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)-Klasse aus den Transformationen [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) und [`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*). Die `MapValueToKey`-Transformation übernimmt den kategorischen Wert aus der Spalte `Label`, konvertiert diesen in einen numerischen `KeyType`-Wert und speichert ihn in einer neuen Spalte namens `LabelAsKey`. `LoadImages` greift auf Werte aus der Spalte `ImagePath` zusammen mit dem Parameter `imageFolder` zu, um Bilder für das Training zu laden. Durch Festlegen von `useImageType` auf `false` wird das Bild in ein `byte[]`-Array konvertiert. 

    [!code-csharp [DefinePreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L26-L33)]

1. Verwenden Sie die [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*)-Methode, um die Daten auf die [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)-Klasse `preprocessingPipeline` gefolgt von der [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*)-Methode anzuwenden, wodurch eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle zurückgegeben wird, die die vorverarbeiteten Daten enthält.

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L35-L37)]

1. Beim Trainieren eines Modells ist es wichtig, sowohl über ein Trainingsdataset als auch ein Validierungsdataset zu verfügen. Das Modell wird mit dem Trainingsset trainiert. Wie gut es Vorhersagen über unbekannte Daten erstellt, wird an der Leistung im Vergleich zum Validierungsset gemessen. Basierend auf den Ergebnissen dieser Leistung nimmt das Modell Anpassungen an dem Gelernten vor, um die Ergebnisse zu verbessern. Das Validierungsset kann entweder aus der Aufteilung des ursprünglichen Datasets oder aus einer anderen Quelle stammen, die bereits für diesen Zweck vorgesehen ist. In diesem Fall wird das vorverarbeitete Datenset in Trainings-, Validierungs- und Testsets unterteilt.

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L39-L40)]

    Im obigen Codebeispiel werden zwei Aufteilungen vorgenommen. Zunächst werden die vorverarbeiteten Daten aufgeteilt, wobei 70% für das Training und die restlichen 30% für die Validierung verwendet werden. Anschließend werden die 30% des Validierungssets weiter in Validierungs- und Testsets unterteilt, wobei 90% für die Validierung und 10% für Tests verwendet werden. 

    Ein gutes Beispiel, um den Sinn und Zweck dieser Datenaufteilungen zu verstehen, ist eine Prüfungsituation. Wenn Sie für eine Prüfung lernen, lesen Sie Ihre Notizen, Bücher oder andere Unterlagen, um die in der Prüfung enthaltenen Themen zu lernen und zu vertiefen. Dafür ist das Trainingsset da. Dann können Sie eine Probeklausur ablegen, um Ihren Wissensstand zu überprüfen. Hier bietet sich das Validierungsset an. Sie möchten vor der eigentlichen Prüfung feststellen, ob Sie die Inhalte richtig verstanden haben. Ausgehend von den Ergebnissen können Sie herausfinden, was Sie falsch gemacht bzw. nicht richtig verstanden haben, und so die Ergebnisse in den Lernprozess für die eigentliche Prüfung einbeziehen. Zum Schluss legen Sie die Prüfung ab. Dafür wird das Testset verwendet. Sie haben die Fragen in der Prüfung noch nie gesehen und nutzen zur Bearbeitung der vorliegenden Aufgabe nun das, was Sie sich durch den Lernprozess (Training) und die Überprüfung des Gelernten (Validierung) angeeignet haben. 

1. Ordnen Sie den Teilbereichen die jeweiligen Werte für die Trainings-, Validierungs- und Testdaten zu.

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L42-L44)]

## <a name="define-the-training-pipeline"></a>Definieren der Trainingspipeline

Das Modelltraining umfasst mehrere Schritte. Zunächst wird die Bildklassifizierungs-API verwendet, um das Modell zu trainieren. Anschließend werden die verschlüsselten Bezeichnungen in der Spalte `PredictedLabel` mithilfe der `MapKeyToValue`-Transformation wieder in ihren ursprünglichen kategorischen Wert konvertiert. 

1. Definieren Sie die Trainingspipeline [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601), die sowohl aus der `mapLabelEstimator`- als auch aus der `ImageClassification`-Transformation besteht.

    [!code-csharp [DefineTrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L46-L58)]    

    Der `ImageClassification`-Estimator berücksichtigt mehrere Parameter:

    - `featuresColumnName` ist die Spalte, die als Eingabe für das Modell verwendet wird.
    - `labelColumnName` ist die Spalte für den vorherzusagenden Wert.
    - `arch` definiert, welche der vorab trainierten Modellarchitekturen verwendet werden soll. In diesem Tutorial wird die 101-Ebenen-Variante des Modells „ResNetv2“ verwendet.
    - `epoch` gibt die Höchstzahl von Iterationen über das gesamte Dataset während des Trainingsprozesses an. Je höher die Anzahl, desto länger trainiert das Modell und desto besser ist das dabei erzeugte Modell.
    - `batchSize` ist die Anzahl der Beispiele, die gleichzeitig für das Training verwendet werden können. Während einer Epoche werden mehrere Batches entsprechend dem batchSize-Wert verwendet, um das Modell zu trainieren und zu aktualisieren. Je niedriger der Wert, desto weniger Speicherplatz wird bei der Verarbeitung jedes Batches benötigt.
    - `testOnTrainSet` weist das Modell an, die Leistung anhand des Trainingssets zu messen, wenn kein Validierungsset vorhanden ist.
    - `metricsCallback` verknüpft eine Funktion, um den Fortschritt während des Trainings zu verfolgen.
    - `validationSet` ist die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle, die die Validierungsdaten enthält.
    - `reuseTrainSetBottleneckCachedValues` informiert das Modell, ob die zwischengespeicherten Werte aus der Engpassphase in nachfolgenden Durchläufen verwendet werden sollen. Die Engpassphase ist eine einmalige Pass-Through-Berechnung, die bei der ersten Durchführung sehr rechenintensiv ist. Wenn sich die Trainingsdaten nicht ändern, und Sie mit einer anderen Anzahl von Epochen oder anderen Batchgrößen experimentieren möchten, können Sie mit den zwischengespeicherten Werten den Zeitaufwand für das Training eines Modells erheblich verringern.
    - `reuseValidationSetBottleneckCachedValues` ist vergleichbar mit `reuseTrainSetBottleneckCachedValues`, allerdings handelt es sich in diesem Fall um das Validierungsdataset.
    - `disableEarlyStopping` informiert den ImageClassification-Estimator darüber, ob er eine Strategie zum frühzeitigen Abbrechen anwenden soll. Wenn das Modell nach den optimalen Werten sucht, mit denen es während des Trainings genaue Vorhersagen treffen kann, ist es möglich, dass die Leistung steigt oder sinkt. Erreicht das Modell schließlich die letzte Epoche, kann es vorkommen, dass die im Training erlernten Muster nicht optimal sind. Die Funktion zum frühzeitigen Abbrechen überwacht, ob es beim Training zu Leistungseinbrüchen kommt. Sollte dies der Fall sein, wird der Trainingsprozess abgebrochen, damit eine optimale Version des Modells erstellt werden kann.

1. Verwenden Sie die Methode [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*), um Ihr Modell zu trainieren.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L60)]

## <a name="use-the-model"></a>Verwenden des Modells

Nachdem Sie Ihr Modell trainiert haben, ist es an der Zeit, es zur Klassifizierung von Bildern zu verwenden.

Erstellen Sie unter der `Main`-Methode eine neue Hilfsmethode namens `OutputPrediction`, um Vorhersageinformationen in der Konsole anzuzeigen.

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L94-L98)]

### <a name="classify-a-single-image"></a>Klassifizieren eines einzelnen Bilds

1. Fügen Sie eine neue Methode namens `ClassifySingleImage` unter der `Main`-Methode hinzu, um eine Einzelbildvorhersage zu erstellen und auszugeben.

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. Erstellen Sie eine [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Klasse innerhalb der `ClassifySingleImage`-Methode. Die [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Klasse ist eine praktische API, mit der Sie eine Vorhersage für eine einzelne Dateninstanz übergeben und dann ausführen können.

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L71)]    

1. Um auf eine einzelne `ModelInput`-Instanz zuzugreifen, konvertieren Sie die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle `data` in eine [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)-Schnittstelle mit der [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode und erhalten Sie dann das erste Ergebnis. 

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L73)]

1. Verwenden Sie die [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*)-Methode, um das Bild zu klassifizieren.

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L75)]

1. Geben Sie die Vorhersage mit der `OutputPrediction`-Methode in der Konsole aus.

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L77-L78)]

1. Rufen Sie innerhalb der `Main`-Methode `ClassifySingleImage` mit dem Testset der Bilder auf.

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L62)]

### <a name="classify-multiple-images"></a>Klassifizieren mehrerer Bilder

1. Fügen Sie eine neue Methode namens `ClassifyImages` unter der `ClassifySingleImage`-Methode hinzu, um mehrere Bildvorhersagen zu erstellen und auszugeben.

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. Erstellen Sie mithilfe der [`Transform`](xref:Microsoft.ML.ITransformer.Transform*)-Methode eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle, die die Vorhersagen enthält. Fügen Sie der `ClassifyImages`-Methode den folgenden Code hinzu.

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L83)]

1. Zur Iteration über die Vorhersagen konvertieren Sie die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle `predictionData` in eine [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)-Schnittstelle mithilfe der [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode und erhalten Sie dann die ersten zehn Ergebnisse.

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L85)]

1. Iterieren Sie die ursprünglichen und vorhergesagten Bezeichnungen für die Vorhersagen, und geben Sie sie aus.

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L87-L91)]

1. Abschließend rufen Sie innerhalb der `Main`-Methode `ClassifyImages` mit dem Testset der Bilder auf.

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L64)]

## <a name="run-the-application"></a>Ausführen der Anwendung

Führen Sie die Konsolenanwendung aus. Die Ausgabe sollte in etwa wie folgt aussehen. Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt. Aus Gründen der Kürze wurde die Ausgabe komprimiert.

**Engpassphase**

Für den Bildnamen wird kein Wert ausgegeben, da die Bilder als `byte[]` geladen werden, sodass kein Bildname angezeigt werden kann.

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279, Image Name:
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280, Image Name:
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1, Image Name:
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2, Image Name:
```

**Trainingsphase**

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

**Klassifizieren der Ausgabe von Bildern**

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

Bei der Überprüfung des Bilds *7001-220.jpg* können Sie feststellen, dass tatsächlich kein Riss zu sehen ist. 

![Für die Vorhersage verwendetes SDNET2018-Datasetbild](./media/image-classification-api-transfer-learning/predictedimage.jpg)

Herzlichen Glückwunsch! Sie haben ein Deep-Learning-Modell zur Klassifizierung von Bildern erstellt.

### <a name="improve-the-model"></a>Verbessern des Modells

Wenn Sie mit den Ergebnissen des Modells nicht zufrieden sind, können Sie versuchen, seine Leistung zu verbessern, indem Sie einige der folgenden Ansätze ausprobieren:

- **Mehr Daten**: Je mehr Beispiele vorhanden sind, von denen ein Modell lernt, desto besser ist dessen Leistung. Laden Sie das vollständige [SDNET2018-Dataset](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) herunter, und verwenden Sie es für das Training. 
- **Erweitern der Daten**: Eine gängige Technik, um eine größere Datenvielfalt zu erreichen, ist die Erweiterung der Daten durch Aufnahme eines Bilds und Anwendung verschiedener Transformationen (Drehen, Spiegeln, Verschieben, Zuschneiden). Auf diese Weise erhalten Sie verschiedene Beispiele, von denen das Modell lernen kann. 
- **Längere Trainingsdauer**: Umso länger die Trainingsdauer, desto genauer werden die Ergebnisse des Modells sein. Durch die Erhöhung der Anzahl von Epochen kann sich die Leistung des Modell erheblich verbessern.
- **Experimentieren mit Hyperparametern**: Zusätzlich zu den in diesem Tutorial verwendeten Parametern können weitere Parameter angepasst werden, um die Leistung zu steigern. Die Änderung des Lerntempos, das den Umfang der Aktualisierungen am Modell nach jeder Epoche bestimmt, kann zu einer höheren Leistung führen.
- **Verwenden einer anderen Modellarchitektur**: Abhängig von der Beschaffenheit Ihrer Daten kann sich das Modell, das am besten deren Merkmale erlernen kann, unterscheiden. Wenn Sie mit der Leistung Ihres Modells unzufrieden sind, sollten Sie versuchen, die Architektur zu ändern.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Deep Learning im Vergleich zu maschinellem Lernen](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie erfahren, wie Sie ein benutzerdefiniertes Deep-Learning-Modell mithilfe von Transferlernen, einem vorab trainierten TensorFlow-Modell und der ML.NET-Bildklassifizierungs-API erstellen, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.

Fahren Sie mit dem nächsten Tutorial fort, um mehr zu erfahren.

> [!div class="nextstepaction"]
> [Objekterkennung](object-detection-onnx.md)
