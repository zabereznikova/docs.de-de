---
title: Verwenden von ML.NET für das Iris-Clustering
description: Hier erfahren Sie, wie Sie ML.NET in einem Clusteringszenario verwenden.
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bb41fd317507c14b46aea94e1ce576e390932a65
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49453189"
---
# <a name="tutorial-use-mlnet-to-cluster-iris-flowers-clustering"></a>Tutorial: Verwenden von ML.NET für das Iris-Clustering

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in der [ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Dieses Tutorial zeigt, wie Sie mit ML.NET ein [Clusteringmodell](../resources/tasks.md#clustering) für das [Iris-Dataset](https://en.wikipedia.org/wiki/Iris_flower_data_set) erstellen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Das Problem verstehen
> - Auswählen der entsprechenden Machine Learning-Aufgabe
> - Vorbereiten der Daten
> - Laden und Transformieren der Daten
> - Auswählen eines Lernalgorithmus
> - Trainieren des Modells
> - Verwenden des Modells für Vorhersagen

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

## <a name="understand-the-problem"></a>Das Problem verstehen

Bei diesem Problem geht es darum, Iris anhand ihrer Blütenmerkmale in unterschiedliche Gruppen einzuteilen. Die entsprechenden Merkmale sind Länge und Breite des Kelchblatts sowie Länge und Breite des Kronblatts. Für dieses Tutorial wird angenommen, dass der Typ jeder Blume unbekannt ist. Sie werden die Struktur eines Datasets basierend auf Merkmalen kennenlernen und vorhersagen können, wie eine Dateninstanz in diese Struktur passt.

## <a name="select-the-appropriate-machine-learning-task"></a>Auswählen der entsprechenden Machine Learning-Aufgabe

Da Sie nicht wissen, zu welcher Gruppe jede Blume gehört, wählen Sie die Aufgabe [Unüberwachtes maschinelles Lernen](../resources/glossary.md#unsupervised-machine-learning) aus. Um ein Dataset so in Gruppen zu unterteilen, dass Elemente in derselben Gruppe einander ähnlicher sind als in anderen Gruppen, verwenden Sie eine [Clustering](../resources/tasks.md#clustering)-Aufgabe für maschinelles Lernen.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie im Textfeld **Name** „IrisClustering“ ein, und wählen Sie dann die Schaltfläche **OK** aus.

1. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset und die Modelldateien zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

1. Installieren Sie das NuGet-Paket **Microsoft.ML**:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, wählen Sie das Paket in der Liste aus, und klicken Sie anschließend auf die Schaltfläche **Installieren**. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

## <a name="prepare-the-data"></a>Vorbereiten der Daten

1. Laden Sie das Dataset [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) herunter und speichern Sie es im Ordner *Data*, den Sie im vorherigen Schritt erstellt haben. Weitere Informationen zum Iris-Dataset finden Sie im englischen Wikipedia-Artikel [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) und auf der Website [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris), der Quelle des Datasets.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *iris.data*, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

Die Datei *iris.data* enthält fünf Spalten, die Folgendes darstellen:

- Kelchblattlänge in Zentimetern
- Kelchblattbreite in Zentimetern
- Kronblattlänge in Zentimetern
- Kronblattbreite in Zentimetern
- Iristyp

Für das Clusteringbeispiel wird in diesem Tutorial die letzte Spalte ignoriert.

## <a name="create-data-classes"></a>Erstellen von Datenklassen

Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *IrisData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.
1. Fügen Sie der neuen Datei die folgenden `using`-Anweisungen hinzu:

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *IrisData.cs* den folgenden Code hinzu, der die Klassen `IrisData` und `ClusterPrediction` definiert:

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

`IrisData` ist die Eingabedatenklasse und verfügt über Definitionen für jedes Merkmal im Dataset. Verwenden Sie das Attribut [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute), um die Indizes der Quellspalten in der Datasetdatei festzulegen.

Die Klasse `ClusterPrediction` repräsentiert die Ausgabe des Clusteringmodells, das auf eine `IrisData`-Instanz angewendet wird. Verwenden Sie das Attribut [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute), um die Felder `PredictedClusterId` und `Distances` an die Spalten **PredictedLabel** bzw. **Score** zu binden. Bei der Clusteringaufgabe haben diese Spalten die folgende Bedeutung:

- Die Spalte **PredictedLabel** enthält die ID des vorhergesagten Clusters.
- Die Spalte **Score** enthält ein Array mit den quadratischen euklidischen Abständen zum Clusterschwerpunkt. Die Arraylänge ist gleich der Anzahl von Clustern.

> [!NOTE]
> Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.

## <a name="define-data-and-model-paths"></a>Definieren von Daten und Modellpfaden

Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie zwei Felder hinzu, die die Pfade zur Datasetdatei und zur Datei zum Speichern des Modells enthalten:

- `_dataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.
- `_modelPath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.

Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzu, um den obenstehenden Code zu kompilieren:

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a>Erstellen einer Lernpipeline

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

Ersetzen Sie in der `Main`-Methode `Console.WriteLine("Hello World!")` durch den folgenden Code:

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

Die `Train`-Methode trainiert das Modell. Erstellen Sie die Methode direkt unter der Methode `Main` mit dem folgenden Code:

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

Die Lernpipeline lädt alle Daten und Algorithmen, die zum Trainieren des Modells erforderlich sind. Fügen Sie den folgenden Code der `Train`-Methode hinzu:

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a>Laden und Transformieren der Daten

Laden Sie zuerst das Trainingsdataset. In diesem Fall wird das Trainingsdataset in der Textdatei mit einem Pfad gespeichert, der vom Feld `_dataPath` definiert wird. Die Spalten in der Datei werden durch Kommas („,“) getrennt. Fügen Sie den folgenden Code der `Train`-Methode hinzu:

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

Im nächsten Schritt werden alle Spalten mit Merkmalen mithilfe der Transformationsklasse <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> in der Spalte **Features** zusammengefasst. Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**. Fügen Sie den folgenden Code hinzu:

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a>Auswählen eines Lernalgorithmus

Nach dem Hinzufügen von Daten zur Pipeline und dem Transformieren in das richtige Eingabeformat wählen Sie einen Lernalgorithmus (**Lernmodul**) aus. Das Lernmodul trainiert das Modell. ML.NET bietet ein Lernmodul <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer>, das den [k-Means-Algorithmus](https://en.wikipedia.org/wiki/K-means_clustering) mit einer verbesserten Methode zur Auswahl der anfänglichen Clusterschwerpunkte implementiert.

Fügen Sie den folgenden Code nach dem im vorherigen Schritt hinzugefügten Datenverarbeitungscode in die `Train`-Methode ein:

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

Verwenden Sie die Eigenschaft <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType>, um die Anzahl von Clustern anzugeben. Der obige Code gibt an, dass das Dataset in drei Cluster aufgeteilt wird.

## <a name="train-the-model"></a>Trainieren des Modells

Die in den vorangegangenen Abschnitten hinzugefügten Schritte haben die Pipeline für das Training vorbereitet, es wurden jedoch keine ausgeführt. Die Methode `pipeline.Train<TInput, TOutput>` erzeugt das Modell, das eine Instanz vom Typ `TInput` annimmt und eine Instanz vom Typ `TOutput` ausgibt. Fügen Sie den folgenden Code der `Train`-Methode hinzu:

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a>Speichern des Modells

An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann. Um das Modell in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code der Methode `Main` unter dem Aufruf der Methode `Train` hinzu:

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

Wenn Sie `await` in der Methode `Main` verwenden, bedeutet dies, dass die `Main`-Methode den Modifizierer `async` erfordert und eine Aufgabe `Task` zurückgeben muss:

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

Außerdem müssen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzufügen:

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

Da die `async Main`-Methode ein neues Feature in C# 7.1 und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern. Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus. Klicken Sie auf die Schaltfläche **OK**.

## <a name="use-the-model-for-predictions"></a>Verwenden des Modells für Vorhersagen

Erstellen Sie die Klasse `TestIrisData`, um Testdateninstanzen unterzubringen:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestIrisData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.
1. Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

Dieses Tutorial führt eine Irisdateninstanz innerhalb dieser Klasse ein. Sie können weitere Szenarios zum Testen des Models hinzufügen. Fügen Sie den folgenden Code der `TestIrisData`-Klasse hinzu:

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

Um herauszufinden, zu welchem Cluster das angegebene Element gehört, gehen Sie zurück zur Datei *Program.cs* und fügen Sie den folgenden Code in die Methode `Main` ein:

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

Führen Sie das Programm aus, um festzustellen, welcher Cluster die angegebene Dateninstanz und die quadratischen Abstände von dieser Instanz zum Clusterschwerpunkt enthält. Die Ergebnisse sollten den unten dargestellten ähneln. Während die Pipeline verarbeitet wird, werden möglicherweise Warnungen oder Meldungen zur Verarbeitung angezeigt. Diese wurden der Übersichtlichkeit halber aus der folgenden Ausgabe entfernt.

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

Herzlichen Glückwunsch! Sie haben erfolgreich ein Machine Learning-Modell für Iris-Clustering erstellt und für Vorhersagen verwendet. Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Das Problem verstehen
> - Auswählen der entsprechenden Machine Learning-Aufgabe
> - Vorbereiten der Daten
> - Laden und Transformieren der Daten
> - Auswählen eines Lernalgorithmus
> - Trainieren des Modells
> - Verwenden des Modells für Vorhersagen

In unserem GitHub-Repository können Sie mit dem Lernen fortfahren und weitere Beispiele finden.
> [!div class="nextstepaction"]
> [dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/)
