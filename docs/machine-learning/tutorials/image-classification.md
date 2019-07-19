---
title: 'Tutorial: Erneutes Trainieren der TensorFlow-Bildklassifizierung: Übertragungslernen'
description: Erfahren Sie, wie ein TensorFlow-Modell für die Bildklassifizierung mit Übertragungslernen und ML.NET neu trainieren. Das ursprüngliche Modell war so trainiert, dass es einzelne Bilder klassifizieren konnte. Nach dem erneuten Training ordnet das neue Modell die Bilder in allgemeine Kategorien ein.
ms.date: 07/09/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 65f94fa5e725703d79d0dddae761cbfbc3f89e0e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804761"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a>Tutorial: Erneutes Trainieren einer TensorFlow-Bildklassifizierung mit Übertragungslernen und ML.NET

Erfahren Sie, wie ein TensorFlow-Modell für die Bildklassifizierung mit Übertragungslernen und ML.NET neu trainieren. Das ursprüngliche Modell war so trainiert, dass es einzelne Bilder klassifizieren konnte. Nach dem erneuten Training ordnet das neue Modell die Bilder in allgemeine Kategorien ein. 

Das von Grund auf neue Trainieren eines Modells zur [Bildklassifizierung](https://en.wikipedia.org/wiki/Outline_of_object_recognition) erfordert das Einstellen von Millionen von Parametern, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden). Transfer Learning ist zwar nicht so effektiv wie das von Grund auf neue Trainieren eines benutzerdefinierten Modells, doch damit können Sie diesen Prozess durch die Arbeit mit Tausenden von Bildern im Vergleich zur Arbeit mit Millionen bezeichneter Bilder abkürzen und relativ schnell ein benutzerdefiniertes Modell erstellen (innerhalb einer Stunde auf einem Computer ohne eine GPU).

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Wiederverwenden und Optimieren des vortrainierten Modells
> * Klassifizieren von Bildern

## <a name="what-is-transfer-learning"></a>Was ist Übertragungslernen?

Was wäre, wenn Sie ein zum Lösen eines ähnlichen Problems bereits vortrainiertes Modell wiederverwenden und entweder alle oder einige Ebenen dieses Modells neu trainieren könnten, damit es Ihr Problem löst? Dieses Verfahren der erneuten Nutzung eines Teils eines bereits trainierten Modells zum Erstellen eines neuen Modells wird als [Transfer Learning](https://en.wikipedia.org/wiki/Transfer_learning) (Übertragungslernen) bezeichnet.

## <a name="image-classification-sample-overview"></a>Übersicht über das Bildklassifizierungsbeispiel

Das Beispiel ist eine Konsolenanwendung, die ML.NET verwendet, um eine Bildklassifizierung mittels Wiederverwendung eines vortrainierten Modells zum Klassifizieren von Bildern mit einer kleinen Menge von Trainingsdaten zu erstellen.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF). Hinweis: Die .NET-Projektkonfiguration, die für dieses Tutorial verwendet wird, ist standardmäßig auf .NET Core 2.2 ausgerichtet.

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“. 

* Microsoft.ML 1.0.0 NuGet-Paket
* Microsoft.ML.ImageAnalytics 1.0.0 NuGet-Paket
* Microsoft.ML.TensorFlow 0.12.0 NuGet-Paket

* [Die ZIP-Datei mit dem Tutorialassetsverzeichnis ](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [Das Machine Learning-Modell von InceptionV1](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a>Auswählen der entsprechenden Machine Learning-Aufgabe

[Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) ist eine Teilmenge von Machine Learning, die Bereiche wie maschinelles Sehen und Spracherkennung revolutioniert.

Deep Learning-Modelle werden mithilfe großer Mengen [bezeichneter Daten](https://en.wikipedia.org/wiki/Labeled_data) und [neuronaler Netze](https://en.wikipedia.org/wiki/Artificial_neural_network) trainiert, die mehrere Lernebenen enthalten. Deep Learning:

* Bietet bei einigen Aufgaben eine bessere Leistung als maschinelles Sehen.

* Bietet gute Leistungen bei großen Datenmengen.

Bildklassifizierung ist eine gängige Machine Learning-Aufgabe, mit der automatisch Bilder in mehrere Kategorien klassifiziert werden können, z.B.:

* Erkennen, ob ein Bild ein menschliches Gesicht enthält oder nicht.
* Unterscheiden zwischen Katzen und Hunden.

 Es lässt sich auch wie in den folgenden Bildern bestimmen, ob ein Bild ein Lebensmittel, ein Spielzeug oder ein Gerät zeigt:

![Pizzabild](./media/image-classification/220px-Pepperoni_pizza.jpg)
![Teddybärbild](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![Toasterbild](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> Die vorherigen Abbildungen stammen aus Wikimedia-Commons und unterliegen folgendem Urheberrecht:
>
> * „220px-Pepperoni_pizza.jpg“ Public Domain https://commons.wikimedia.org/w/index.php?curid=79505,
> * „119px-Nalle_-_a_small_brown_teddy_bear.jpg“ von [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) – selbst fotografiert, CC-BY-SA-2.0, https://commons.wikimedia.org/w/index.php?curid=48166.
> * „193px-Broodrooster.jpg“ von [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) – eigenes Werk, CC-BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403

Transfer Learning umfasst einige Strategien wie z.B. *erneutes Trainieren aller Ebenen* und die *vorletzte Ebene*. In diesem Tutorial wird die Verwendung der *Strategie der vorletzten Ebene* erläutert und veranschaulicht. Die *Strategie der vorletzten Ebene* verwendet ein Modell erneut, das bereits vortrainiert wurde, um ein bestimmtes Problem zu lösen. Die Strategie trainiert dann die letzte Ebene dieses Modells erneut, um ein neues Problem zu lösen. Aus dem Wiederverwenden des vortrainierten Modells als Teil des neuen Modells resultiert eine erhebliche Zeit- und Ressourcenersparnis.

Ihr Bildklassifizierungsmodell verwendet das [Inception-Modell](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) erneut, ein gängiges, am `ImageNet`-Dataset trainiertes Bilderkennungsmodell, in dem das TensorFlow-Modell versucht, ganze Bilder in Tausenden von Klassen wie „Regenschirm“, „Jersey“ und „Spülmaschine“ zu klassifizieren.

Das `Inception v1 model` kann als [Deep Convolutional Neural Network](https://en.wikipedia.org/wiki/Convolutional_neural_network) (tiefes faltendes neuronales Netzwerk) klassifiziert werden und kann eine angemessene Leistung bei schwierigen visuellen Erkennungsaufgaben erzielen, die in einigen Bereichen dem menschlichen Leistungsvermögen ebenbürtig ist oder es überschreitet. Das Modell / der Algorithmus wurde von mehreren Forschern entwickelt und basiert auf der ursprünglichen Arbeit: [„Rethinking the Inception Architecture for Computer Vision“ von Szegedy, et al.](https://arxiv.org/abs/1512.00567) (Neuer Ansatz der Inception-Architektur für maschinelles Sehen)

Da das `Inception model` bereits anhand von Tausenden anderer Bilder vortrainiert wurde, enthält es die zur Bildidentifizierung erforderlichen [Bildfeatures](https://en.wikipedia.org/wiki/Feature_(computer_vision)). Die unteren Bildfeatureebenen erkennen einfache Features (z.B. Kanten), und die höheren Ebenen erkennen komplexere Features (z.B. Formen). Die letzte Ebene wird anhand einer viel kleinerer Menge von Daten trainiert, da Sie mit einem vortrainierten Modell beginnen, das bereits weiß, wie Bilder klassifiziert werden. Da Sie mit Ihrem Modell mehr als zwei Kategorien klassifizieren können, ist dies ein Beispiel für eine [Multiklassenklassifizierung](../resources/tasks.md#multiclass-classification). 

`TensorFlow` ist ein gängiges Deep Learning- und Machine Learning-Toolkit, das das Trainieren von Deep Neural Networks (und allgemeine numerische Berechnungen) ermöglicht, und wird als `transformer` in ML.NET implementiert. Für dieses Tutorial dient es zum Wiederverwenden des `Inception model`.

Wie im folgenden Diagramm dargestellt, fügen Sie einen Verweis auf die ML.NET-NuGet-Pakete in Ihrer .NET Core- oder .NET Framework-Anwendung hinzu. Im Hintergrund enthält ML.NET die native `TensorFlow`-Bibliothek, mit der Sie Code schreiben können, der eine vorhandene trainierte `TensorFlow`-Modelldatei für die Bewertung lädt, und verweist darauf.  

![TensorFlow-Transformation – ML.NET Arch-Diagramm](./media/image-classification/tensorflow-mlnet.png)

Das `Inception model` ist darauf trainiert, Bilder in tausend Kategorien zu klassifizieren, jedoch müssen Sie Bilder in eine kleinere Kategoriegruppe und nur in diese Kategorien klassifizieren. Geben Sie den `transfer`-Teil von `transfer learning` ein. Sie können die Fähigkeit des `Inception model` zum Erkennen und Klassifizieren von Bildern auf die neuen begrenzten Kategorien Ihrer benutzerdefinierten Bildklassifizierung übertragen.  

 Sie werden die letzte Ebene dieses Modells mit einem Satz von drei Kategorien neu trainieren:

* Lebensmittel
* Spielzeug
* Gerät

Ihre Ebene verwendet einen [Algorithmus für multinomiale logistische Regression](https://en.wikipedia.org/wiki/Multinomial_logistic_regression), um so schnell wie möglich die richtige Kategorie zu finden. Dieser Algorithmus verwendet zur Klassifizierung Wahrscheinlichkeiten, um die Antwort zu bestimmen, wobei der richtigen Kategorie der Wert 1 und den anderen der Wert 0 zugewiesen wird.  

### <a name="dataset"></a>Dataset

Es gibt zwei Datenquellen: die `.tsv`-Datei und die Bilddateien.  Die `tags.tsv`-Datei enthält zwei Spalten: die erste ist als `ImagePath` definiert und die zweite das `Label` für das Bild. Die folgende Beispieldatei verfügt nicht über eine Kopfzeile und sieht wie folgt aus:

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

Die Trainings- und Testbilder befinden sich in dem Assetsordner, den Sie in einer ZIP-Datei herunterladen. Diese Bilder gehören zu Wikimedia Commons.
> *[Wikimedia-Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), das Repository für kostenlose Medien.* Abgerufen am 17. Oktober 2018 um 10:48 Uhr aus:  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

### <a name="create-a-project"></a>Erstellen eines Projekts

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TransferLearningTF“.

2. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.ML**. Klicken Sie auf die **Version**-Dropdownliste, wählen Sie das **1.0.0**-Paket in der Liste und dann die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen. Wiederholen Sie diese Schritte für **Microsoft.ML.ImageAnalytics v1.0.0** und **Microsoft.ML.TensorFlow v0.12.0**.

### <a name="prepare-your-data"></a>Vorbereiten Ihrer Daten

1. Laden Sie [die ZIP-Datei des Projektassetverzeichnisses](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) herunter, und entzippen Sie sie.

2. Kopieren Sie das `assets`-Verzeichnis in Ihr *TransferLearningTF*-Projektverzeichnis. Dieses Verzeichnis und seine Unterverzeichnisse enthalten die für dieses Tutorial erforderlichen Daten und Unterstützungsdateien (mit Ausnahme des Inception-Modells, das Sie im nächsten Schritt herunterladen und hinzufügen).

3. Laden Sie das [Inception-Modell](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) herunter, und entzippen Sie es.

4. Kopieren Sie den Inhalt des gerade entzippten `inception5h`-Verzeichnisses in Ihr *TransferLearningTF*-Projektverzeichnis `assets\inputs-train\inception`. Dieses Verzeichnis enthält das Modell und die zusätzlich für dieses Tutorial erforderlichen Unterstützungsdateien wie in der folgenden Abbildung gezeigt:

   ![Inhalt des Inception-Verzeichnisses](./media/image-classification/inception-files.png)

5. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf alle Dateien im Assetverzeichnis und den Unterverzeichnissen, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

Erstellen Sie globale Felder, die die Pfade zu den verschiedenen Assets enthalten, und globale Variablen für `LabelTokey`, `ImageReal` und `PredictedLabelValue`:

* `_assetsPath` enthält den Pfad zu den Assets.
* `_trainTagsTsv` enthält den Pfad zur TSV-Datei mit den Trainingsbilddaten-Tags.
* `_predictTagsTsv` enthält den Pfad zur TSV-Datei mit den Vorhersagebilddaten-Tags.
* `_trainImagesFolder` enthält den Pfad zu den Bildern, die zum Trainieren des Modells verwendet werden.
* `_predictImagesFolder` enthält den Pfad zu den Bildern, die vom trainierten Modell klassifiziert werden sollen.
* `_inceptionPb` enthält den Pfad zu dem vortrainierten Inception-Modell, das zum erneuten Trainieren Ihres Modells wiederverwendet werden soll.
* `_inputImageClassifierZip` enthält den Pfad, über den das trainierte Modell geladen wird.
* `_outputImageClassifierZip` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.
* `LabelTokey` ist der einem Schlüssel zugeordnete `Label`-Wert.
* `ImageReal` ist die Spalte, die den vorhergesagten Bildwert enthält.
* `PredictedLabelValue` ist die Spalte, die den vorhergesagten Bezeichnungswert enthält.

Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die anderen Variablen anzugeben:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

Erstellen Sie einige Klassen für Ihre Eingabedaten und Vorhersagen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImageData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *ImageData.cs* wird im Code-Editor geöffnet. Fügen Sie die folgende `using`-Anweisung am Anfang der *ImageData.cs*-Datei hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code für die `ImageData`-Klasse der *ImageData.cs*-Datei hinzu:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

`ImageData` ist die Eingabebilddaten-Klasse mit den folgenden <xref:System.String>-Feldern:

* `ImagePath` enthält den Bilddateinamen.
* `Label` enthält einen Wert für die Bildbezeichnung.

Fügen Sie dem Projekt eine neue Klasse für `ImagePrediction` hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImagePrediction.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *ImagePrediction.cs* wird im Code-Editor geöffnet. Entfernen Sie sowohl die `System.Collections.Generic`- als auch die `System.Text` `using`-Anweisung am Anfang von *ImagePrediction.cs*:

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit der Klasse `ImagePrediction` der Datei *ImagePrediction.cs* hinzu:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

`ImagePrediction` ist die Bildvorhersageklasse und hat die folgenden Felder:

* `Score` enthält den Zuverlässigkeitsprozentsatz für eine bestimmte Bildklassifizierung.
* `PredictedLabelValue` enthält einen Wert für die vorhergesagte Bildklassifizierungsbezeichnung.

Die `ImagePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde. Sie besitzt einen `string` (`ImagePath`) für den Bildpfad. Mit `Label` wird das Modell wiederverwendet und neu trainiert. Das `PredictedLabelValue` wird während der Vorhersage und Evaluierung verwendet. Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.

Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von `MLContext`.  Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a>Erstellen einer Struktur für Standardparameter

Das Inception-Modell verfügt über mehrere Standardparameter, die Sie übergeben müssen. Erstellen Sie unmittelbar nach der `Main()`-Methode eine Struktur, um Anzeigenamen mit dem folgenden Code die Standardparameterwerte zuzuordnen:

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>Erstellen einer Anzeigehilfsprogramm-Methode

Da Sie die Bilddaten und die zugehörigen Vorhersagen mehr als einmal anzeigen werden, erstellen Sie eine Anzeigehilfsmethode, um die Anzeige der Bild- und Vorhersageergebnisse zu verarbeiten.

Die `DisplayResults()`-Methode führt die folgenden Aufgaben aus:

* Anzeigen der vorhergesagten Ergebnisse.

Erstellen Sie die `DisplayResults()`-Methode mit dem folgenden Code direkt nach der `InceptionSettings`-Struktur:

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

Der in `ImagePrediction` eingegebene `ImagePath` der `Transform()`-Methode mit den vorhergesagten Feldern. Im Laufe des ML.NET-Prozesses fügt jede Komponente Spalten hinzu, sodass die Ergebnisse leicht angezeigt werden können:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

Sie rufen die `DisplayResults()` -Methode in den zwei Bildklassifizierungsmethoden auf.

### <a name="create-a-tsv-file-utility-method"></a>Erstellen einer Hilfsprogrammmethode für die TSV-Datei

Die `ReadFromTsv()`-Methode führt die folgenden Aufgaben aus:

* Lesen der Bilddatendatei `tags.tsv`.
* Hinzufügen des Bildpfads zum Bilddateinamen.
* Laden der Dateidaten in ein IEnumerable`ImageData`-Objekt.

Erstellen Sie die `ReadFromTsv()`-Methode mit dem folgenden Code direkt nach der `PairAndDisplayResults()`-Methode:

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

Der folgende Code analysiert die `tags.tsv`-Datei, um den Dateipfad für die `ImagePath`-Eigenschaft dem Namen der Bilddatei hinzuzufügen und ihn und das `Label` in ein `ImageData`-Objekt zu laden. Fügen Sie ihn als erste Zeile der `ReadFromTsv()`-Methode hinzu.  Zum Anzeigen der Vorhersageergebnisse benötigen Sie den vollqualifizierten Dateipfad.

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
In ML.NET werden die folgenden drei Hauptkonzepte genutzt: [Daten](../resources/glossary.md#data), [Transformatoren](../resources/glossary.md#transformer) (Transformers) und [Schätzer](../resources/glossary.md#estimator) (Estimators).

## <a name="reuse-and-tune-pre-trained-model"></a>Wiederverwenden und Optimieren des vortrainierten Modells

Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode den folgenden Aufruf als nächste Codezeile der `Main()`-Methode hinzu:

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

Die `ReuseAndTuneInceptionModel()`-Methode führt die folgenden Aufgaben aus:

* Laden der Daten.
* Extrahieren und Transformieren der Daten.
* Bewerten des TensorFlow-Modells.
* Optimieren (erneutes Trainieren) des Modells.
* Anzeigen von Modellergebnissen.
* Auswerten des Modells.
* Zurückgeben des Modells.

Erstellen Sie die `ReuseAndTuneInceptionModel()`-Methode mithilfe des folgenden Codes unmittelbar nach der `InceptionSettings`-Struktur und direkt vor der `DisplayResults()`-Methode:

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a>Laden der Daten

Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt. Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden. Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.

Laden der Daten mithilfe des `MLContext.Data.LoadFromTextFile`-Wrappers. Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a>Extrahieren von Features und Transformieren der Daten

Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird.  Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.

Machine Learning-Algorithmen verstehen [mit Features ausgestattete](../resources/glossary.md#feature) Daten, und beim Umgang mit Deep Neural Networks müssen Sie die Bilder dem Format anpassen, das vom Netzwerk erwartet wird. Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).

Führen Sie nach Training und Auswertung eine Vorhersage mit den Werten der **Label**-Spalte durch. Da Sie ein vortrainiertes Modell verwenden, ordnen Sie dem neuen Modell Felder mit der [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A)-Methode zu. Diese Methode wandelt das `Label` in einen numerischen Schlüsseltyp (`LabelTokey`) um und fügt es als neue Datasetspalte hinzu:  Benennen Sie diese mit `estimator`, da Sie ihr auch den Trainer hinzufügen. Fügen Sie die nächste Codezeile hinzu:

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

Ihr Bildverarbeitungsschätzer verwendet vortrainierte [Deep Neural Network (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks)-Featurebereitsteller für die Featureextraktion. Beim Umgang mit Deep Neural Networks passen Sie die Bilder dem vom Netzwerk erwarteten Format an. Aus diesem Grund verwenden Sie mehrere Bildtransformationen, um die Bilddaten in die vom Modell erwartete Form zu bringen:

1. Die `LoadImages`-Transformationsbilder werden als Bitmaptyp in den Arbeitsspeicher geladen.
2. Die `ResizeImages`-Transformation ändert die Größe der Bilder, da Breite und Höhe des Eingabebilds beim vortrainierten Modell definiert sind.
3. Die `ExtractPixels`-Transformation extrahiert die Pixel aus den Eingabebildern und wandelt sie in einen numerischen Vektor um.

Fügen Sie diese Bildtransformationen als nächste Codezeilen hinzu:

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

Das `LoadTensorFlowModel` ist eine praktische Methode, die es ermöglicht, das `TensorFlow`-Modell einmal zu laden und dann den `TensorFlowEstimator` mit dem `ScoreTensorFlowModel` zu erstellen. Die `ScoreTensorFlowModel` extrahiert angegebene Ausgaben (die `softmax2_pre_activation` der Bildfeatures des `Inception model`) und bewertet ein Dataset mithilfe des vorab trainierten `TensorFlow`-Modells.

`softmax2_pre_activation` unterstützt das Modell mit der Bestimmung, zu welcher Klasse die Bilder gehören. `softmax2_pre_activation` gibt für jede Kategorie eine Wahrscheinlichkeit für ein Bild zurück, und alle diese Wahrscheinlichkeiten müssen 1 ergeben. Es wird davon ausgegangen, dass ein Bild nur zu einer einzigen Kategorie gehört, wie im folgenden Beispiel gezeigt:

| Klasse         | Wahrscheinlichkeit   |
| ------------- | ------------- |
| `Food`        |  0,001        |
| `Toy`         |  0,95         |
| `Appliance`   |  0,06         |

Fügen Sie die `TensorFlowTransform` mit den folgenden Codezeilen dem `estimator` an:

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a>Auswählen eines Trainingsalgorithmus

Um den Trainingsalgorithmus hinzuzufügen, rufen Sie die `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()`-Wrappermethode auf.  [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) wird dem `estimator` angefügt und akzeptiert die Inception-Bildfeatures (`softmax2_pre_activation`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.  Fügen Sie den Trainer mit dem folgenden Code hinzu:

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

Sie müssen auch das `predictedlabel` dem `predictedlabelvalue` zuordnen:

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

Mit der `Fit()`-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird. Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `ReuseAndTuneInceptionModel()`-Methode ein, um das Modell an das Trainingsdataset anzupassen und das trainierte Modell zurückzugeben:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

Die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere bereitgestellte Eingabezeilen eines Testdatasets.  Fügen Sie `ReuseAndTuneInceptionModel()` den folgenden Code hinzu, um die `Training`-Daten zu transformieren:

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

Konvertieren Sie Ihre Bilddaten und die Vorhersage-`DataViews` zur Kopplung für eine einfachere Anzeige in stark typisierte `IEnumerables`. Verwenden Sie hierzu die `MLContext.CreateEnumerable()`-Methode mit dem folgenden Code:

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

Rufen Sie die `DisplayResults()`-Methode zum Anzeigen Ihrer Daten und Vorhersagen als nächste Zeile in der `ReuseAndTuneInceptionModel()`-Methode auf:

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

Nachdem Sie die Vorhersage festgelegt haben, führt die [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A)-Methode Folgendes aus:

* Bewerten des Modells (Vergleich der vorhergesagten Werte mit dem tatsächlichen Dataset `Labels`).

* Rückgabe der Modellleistungsmetriken.

Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

Für die Bildklassifizierung werden die folgenden Metriken ausgewertet:

* `Log-loss` – siehe [Protokollverlust](../resources/glossary.md#log-loss). Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.

* `Per class Log-loss`. Der Protokollverlust pro Klasse sollte so nahe wie möglich bei 0 liegen.

Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 Fügen Sie den folgenden Code hinzu, um das trainierte Modell als nächste Zeile zurückzugeben:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a>Klassifizieren von Bildern mit einem geladenen Modell

Fügen Sie den folgenden Aufruf der `ClassifyImages()`-Methode als nächste Codezeile der `Main`-Methode hinzu:

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

Die `ClassifyImages()`-Methode führt die folgenden Aufgaben aus:

* Einlesen der TSV-Datei in `IEnumerable`.
* Vorhersage der Bildklassifizierungen anhand von Testdaten.

Erstellen Sie die `ClassifyImages()`-Methode mithilfe des folgenden Codes unmittelbar nach der `ReuseAndTuneInceptionModel()`-Methode und direkt vor der `PairAndDisplayResults()`-Methode:

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

Rufen Sie zunächst die `ReadFromTsv()`-Methode zum Erstellen einer `IEnumerable<ImageData>`-Klasse auf, die den vollqualifizierten Pfad für jeden `ImagePath` enthält. Sie benötigen diesen Dateipfad, um Ihre Daten und Vorhersageergebnisse zu koppeln. Sie müssen außerdem die `IEnumerable<ImageData>`-Klasse in eine `IDataView` konvertieren, die Sie zur Vorhersage verwenden. Fügen Sie der `ClassifyImages()`-Methode den folgenden Code in den nächsten beiden Zeilen hinzu:

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

Sagen Sie wie zuvor bei den Trainingsbilddaten die Kategorie der Testbilddaten mit der [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode des übergebenen Modells vorher. Fügen Sie der `ClassifyImages()`-Methode den folgenden Code für die Vorhersagen und zum Konvertieren der `predictions` `IDataView` in ein `IEnumerable` für Kopplung und Anzeige hinzu:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

Fügen Sie zum Koppeln und Anzeigen Ihrer Testbilddaten und Vorhersagen den folgenden Code zum Aufrufen der zuvor erstellten `DisplayResults()`-Methode als nächste Zeile der `ClassifyImages()`-Methode hinzu:

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a>Klassifizieren eines einzelnen Bilds mit einem geladenen Modell

Fügen Sie den folgenden Aufruf der `ClassifySingleImage()`-Methode der `Main`-Methode als nächste Codezeile hinzu:

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

Die `ClassifySingleImage()`-Methode führt die folgenden Aufgaben aus:

* Laden einer `ImageData`-Instanz.
* Vorhersagen der Bildklassifizierung anhand von Testdaten.

Erstellen Sie die `ClassifySingleImage()`-Methode mithilfe des folgenden Codes unmittelbar nach der `ClassifyImages()`-Methode und direkt vor der `PairAndDisplayResults()`-Methode:

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

Erstellen Sie zunächst eine `ImageData`-Klasse, die den vollqualifizierten Pfad und Bilddateinamen für den einzelnen `ImagePath` enthält. Fügen Sie der `ClassifySingleImage()`-Methode folgenden Code als nächste Zeilen hinzu:

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

Die [PredictionEngine-Klasse](xref:Microsoft.ML.PredictionEngine%602) ist eine komfortable API, die eine Vorhersage für eine einzelne Dateninstanz ausführt. Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenspalte. Übergeben Sie `imageData` an die `PredictionEngine`, um die Bildkategorie vorherzusagen, indem Sie `ClassifySingleImage()` den folgenden Code hinzufügen:

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

Zeigen Sie das Vorhersageergebnis als nächste Codezeile in der `ClassifySingleImage()`-Methode an:

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a>Ergebnisse

Nachdem Sie die vorherigen Schritte durchgeführt haben, führen Sie die Konsolen-App aus (STRG+F5). Ihre Ergebnisse sollten der folgenden Ausgabe ähneln.  Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

Herzlichen Glückwunsch! Sie haben nun durch Wiederverwenden eines vortrainierten `TensorFlow`-Modells in ML.NET erfolgreich ein Machine Learning-Modell für die Bildklassifizierung erstellt.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Wiederverwenden und Optimieren des vortrainierten Modells
> * Klassifizieren von Bildern mit einem geladenen Modell

Sehen Sie sich im GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für erweiterte Bildklassifizierung um, damit Sie es untersuchen können.
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples-GitHub-Repository](https://github.com/dotnet/machinelearning-samples/)
