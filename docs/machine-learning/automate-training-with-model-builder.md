---
title: Was ist der Modell-Generator und wie funktioniert er?
description: Erfahren Sie mehr über die Verwendung des ML.NET-Modell-Generators zum automatischen Trainieren eines Machine Learning-Modells.
author: natke
ms.date: 06/26/2019
ms.custom: overview
ms.openlocfilehash: 6049db79753986544de18faebfd047aa190af153
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539814"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>Was ist der Modell-Generator und wie funktioniert er?

Der ML.NET-Modell-Generator ist eine leicht verständliche grafische Visual Studio-Erweiterung zum Erstellen, Trainieren und Bereitstellen von benutzerdefinierten Machine Learning-Modellen.

Der Modell-Generator verwendet automatisiertes maschinelles Lernen (AutoML), um verschiedene Machine Learning-Algorithmen und Einstellungen zu untersuchen, damit Sie die optimalen Einstellungen für Ihr Szenario ermitteln können.

Für die Verwendung des Modell-Generators sind keine Machine Learning-Kenntnisse erforderlich. Sie benötigen lediglich einige Daten und ein Problem, das Sie lösen möchten. Modell-Generator generiert den Code, um das Modell zur Ihrer .NET-Anwendung hinzuzufügen.

![Animation der Benutzeroberfläche der Visual Studio-Erweiterung für den Modell-Generator](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> Der Modell-Generator befindet sich derzeit in der Vorschauphase.

## <a name="scenarios"></a>Szenarien

Sie können viele verschiedene Szenarien in den Modell-Generator einbinden, um ein Machine Learning-Modell für Ihre Anwendung zu erstellen.

Ein Szenario ist eine Beschreibung der Art der Vorhersage, die Sie für Ihre Daten treffen möchten. Beispiel:
- Vorhersagen des zukünftigen Produktabsatzes auf der Grundlage historischer Verkaufsdaten
- Klassifizieren der Stimmungen als positiv oder negativ anhand von Kundenrezensionen
- Erkennen einer betrügerischen Banktransaktion
- Weiterleiten von Problemen beim Kundenfeedback an das richtige Team in Ihrem Unternehmen

Im Modell-Generator müssen Sie Ihr Szenario einer [ML.NET-Aufgabe](resources/tasks.md) zuordnen. Sie können den Modell-Generator für **Regression** (Vorhersage von Zahlen) und **Klassifizierung** (Vorhersage von Kategorien) verwenden.

### <a name="which-machine-learning-scenario-is-right-for-me"></a>Welches Machine Learning-Szenario ist für mich geeignet?

Der Modell-Generator enthält Vorlagen für die Standpunktanalyse, die Klassifizierung von Problemen, die Preisvorhersage und benutzerdefinierte Szenarien. Diese Vorlagen können als Ausgangspunkt für Ihr spezifisches ML.NET-Szenario verwendet werden.

#### <a name="sentiment-analysis-binary-classification"></a>Standpunktanalyse (binäre Klassifikation)

Die Standpunktanalyse kann verwendet werden, um positive oder negative Stimmungen im Kundenfeedback vorherzusagen. Es ist ein Beispiel für die binäre Klassifizierungsaufgabe.

Die binäre Klassifizierung wird verwendet, um Daten in zwei Klassen zu kategorisieren (ja/nein; erfolgreich/Fehler; wahr/falsch; positiv/negativ). Sie kann zur Beantwortung der folgenden Fragen verwendet werden:

- Ist diese E-Mail Spam? (Spamerkennung)
- Welche Bewerber können Mitglied werden? (Überprüfung von Bewerbungen)
- Welche Konten bezahlen ihre Rechnungen möglicherweise nicht pünktlich? (Risikominderung)
- Ist diese Kreditkartentransaktion betrügerisch? (Betrugserkennung)

Wenn Ihr Szenario eine Klassifizierung in zwei Kategorien erfordert, können Sie diese Vorlage mit einem eigenen Dataset verwenden.

#### <a name="issue-classification-multiclass-classification"></a>Fehlerklassifizierung (Multiklassenklassifizierung)

Die Fehlerklassifizierung kann verwendet werden, um Kundenfeedback (z.B. zu GitHub) anhand des Problemtitels und der Beschreibung zu kategorisieren. Es ist ein Beispiel für die Multiklassen-Klassifizierungsaufgabe.

Die Multiklassenklassifizierung kann für die Kategorisierung von Daten in drei oder mehr Klassen verwendet werden. Sie kann zur Beantwortung der folgenden Fragen verwendet werden:

- An welche Abteilung sollte ich ein Supportticket weiterleiten? (Weiterleitung von Supporttickets)
- Welche Priorität hat ein Kundenproblem? (Kundenproblempriorisierung)
- In welche Kategorie gehört ein Produkt? (Produktklassifizierung)
- Welche Art von Dokument? (Dokument-/E-Mail-Klassifizierung)

Sie können die Vorlage für die Fehlerklassifizierung für Ihr Szenario verwenden, wenn Sie Daten in drei oder mehr Kategorien einteilen möchten.

#### <a name="price-prediction-regression"></a>Preisvorhersage (Regression)

Die Preisvorhersage kann verwendet werden, um Hauspreise anhand von Lage, Größe und anderen Merkmalen des Hauses vorherzusagen. Es ist ein Beispiel für die Regressionsaufgabe.

Die Regression wird verwendet, um Zahlen vorherzusagen. Sie kann zur Beantwortung der folgenden Fragen verwendet werden:

- Für welchen Preis wird ein Haus verkauft? (Preisvorhersage)
- Nach welcher Zeit muss ein mechanisches Teil gewartet werden? (Vorhersagbarer Wartungsbedarf)
- Wie hoch ist der Feuchtigkeitsgehalt in diesem Trockner? (Geräteüberwachung)
- Wie hoch wird der Gesamtjahresumsatz dieser Region sein? (Umsatzvorhersage)

Sie können die Vorlage für die Preisvorhersage für Ihr Szenario verwenden, wenn Sie einen Zahlenwert mit einem eigenen Dataset vorhersagen möchten.

#### <a name="custom-scenario-choose-your-task"></a>Benutzerdefiniertes Szenario (Aufgabe auswählen)

Mit dem benutzerdefinierten Szenario können Sie eine eigene Aufgabe auswählen. Wählen Sie das Szenario, das für Ihr Problem am sinnvollsten ist.

Mit dem benutzerdefinierten Szenario können Sie eine eigene Machine Learning-Aufgabe auswählen. In den vorherigen Vorlagen war die Machine Learning-Aufgaben an das Szenario gebunden: binäre Klassifizierung, Multiklassenklassifizierung und Regression. In dieser Vorlage können Sie die ML-Aufgabe auswählen, die Sie für Ihre Daten nutzen möchten.

## <a name="data"></a>Daten

Nachdem Sie Ihr Szenario einer Aufgabe zugeordnet haben, fordert Sie der Modell-Generator auf, ein Dataset anzugeben. Die Daten werden verwendet, um das beste Modell für Ihr Szenario zu trainieren, zu evaluieren und auszuwählen. Außerdem müssen Sie die Ausgabe auswählen, die Sie vorhersagen möchten.

### <a name="choose-the-output-to-predict-label"></a>Auswählen der Ausgabe für die Vorhersage (Bezeichnung)

Ein Dataset ist eine Tabelle mit Zeilen mit Trainingsbeispielen und Spalten mit Attributen. Jede Zeile enthält:
- eine **Bezeichnung** (das Attribut, das Sie vorhersagen möchten)
- **Features** (Attribute, die als Eingaben verwendet werden, um die Bezeichnung vorherzusagen).

Für das Szenario der Hauspreisvorhersage könnten folgende Features verwendet werden:
- die Quadratmeterzahl des Hauses
- die Anzahl an Schlafzimmern und Badezimmern
- die Postleitzahl

Die Bezeichnung ist der historische Hauspreis für diese Zeile mit den Werten für die Quadratmeterzahl, Schlafzimmer- und Badezimmeranzahl und Postleitzahl.

![Tabelle mit Zeilen und Spalten mit Hauspreisdaten mit Features bestehend aus Größe, Räumen, Postleitzahl und Preisangabe](media/model-builder-data.png)

### <a name="data-formats"></a>Datenformate

Im Modell-Generator gelten die folgenden Einschränkungen für die Daten:

- Daten müssen in einer Datei (CSV oder TSV mit einer Kopfzeile) oder in einer SQL Server-Datenbank gespeichert werden.
- Das Trainingsdataset ist auf 1 GB begrenzt.
- Für SQL Server gilt ein Grenzwert von 100.000 Zeilen für das Training.
- Daten von SQL Server werden vor dem Training vom Server auf Ihren lokalen Computer kopiert.

### <a name="example-datasets"></a>Beispieldatasets

Wenn Sie noch keine eigenen Daten haben, probieren Sie eines dieser Datasets aus:

|Szenario|ML-Aufgabe|Daten|Bezeichnung|Features|
|-|-|-|-|-|
|Preisvorhersage|Regression|[taxi fare data](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Preis|Fahrtzeit, Strecke|
|Anomalieerkennung|Binäre Klassifizierung|[product sales data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Produktverkäufe|Monat|
|Stimmungsanalyse|Binäre Klassifizierung|[website comment data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_SentimentAnalysis/SentimentAnalysis/Data/wikiDetoxAnnotated40kRows.tsv)|Bezeichnung (0 bei negativer Stimmung, 1, wenn positiv)|Kommentar, Jahr|
|Betrugserkennung|Binäre Klassifizierung|[credit card data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Klasse (1, wenn betrügerisch, andernfalls 0)|Betrag, V1-V28 (anonymisierte Features)|
|Textklassifizierung|Multiklassenklassifizierung|[GitHub issue data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Bereich|Titel, Beschreibung|

## <a name="train"></a>Trainieren

Sobald Sie Ihr Szenario, Ihre Daten und Ihre Bezeichnung ausgewählt haben, trainiert der Modell-Generator das Modell.

### <a name="what-is-training"></a>Was bedeutet Training?

Das Training ist ein automatischer Prozess, bei dem der Modellgenerator dem Modell beibringt, wie es Fragen für Ihr Szenario beantworten kann. Nach dem Training kann Ihr Modell Vorhersagen mit ihm bisher unbekannten Eingabedaten treffen. Wenn Sie zum Beispiel die Hauspreise vorhersagen und ein neues Haus auf den Markt kommt, können Sie seinen Verkaufspreis vorhersagen.

Da der Modell-Generator automatisiertes maschinelles Lernen (AutoML) verwendet, ist während des Trainings keine Eingabe oder Anpassung durch Sie erforderlich.

### <a name="how-long-should-i-train-for"></a>Wie lange sollte ich das Modell trainieren?

Sie können eine Trainingszeit angeben. Wenn Sie das Modell über einen längeren Zeitraum trainieren, wird es in der Regel genauer. Mit zunehmender Größe des Trainingsdatasets wird auch mehr Trainingszeit benötigt. Die folgende Tabelle enthält einige Richtlinien für die Trainingszeit bei immer größer werdenden Datasets.

Datasetgröße  | Datasettyp       | Durchschn. Trainingszeit
------------- | ------------------ | --------------
0 bis 10 MB     | Numerisch und Text   | 10 Sek.
10 bis 100 MB   | Numerisch und Text   | 10 Min.
100 bis 500 MB  | Numerisch und Text   | 30 Min.
500 MB bis 1 GB    | Numerisch und Text   | 60 Min.
1 GB+         | Numerisch und Text   | 3 Stunden +

Die genaue Trainingszeit hängt auch ab von:

- dem Spaltentyp – also Text oder numerischer Typ
- dem Typ der Machine Learning-Aufgabe (Regression oder Klassifizierung)
- der Anzahl der Zeilen, die für das Training verwendet werden
- der Anzahl der Featurespalten, die für das Training verwendet werden

Der Modell-Generator wurde im Maßstab mit einem 1-TB-Dataset getestet, aber die Erstellung eines hochwertigen Modells für diese Datasetgröße kann bis zu vier Tage dauern!

## <a name="evaluate"></a>Auswerten

Unter Evaluierung versteht man den Prozess, bei dem mit dem trainierten Modell Vorhersagen mit neuen Testdaten getroffen werden und anschließend gemessen wird, wie gut die Vorhersagen sind.

Der Modell-Generator unterteilt die Trainingsdaten in einen Trainingssatz und einen Testsatz. Die Trainingsdaten (80 %) werden zum Trainieren Ihres Modells verwendet, und die Testdaten (20 %) zur Evaluierung Ihres Modells zurückgehalten.  Die für die Evaluierung verwendeten Metriken hängen von der ML-Aufgabe ab. Weitere Informationen finden Sie unter [Metriken für die Modellevaluierung](resources/metrics.md).

### <a name="sentiment-analysis-binary-classification"></a>Standpunktanalyse (binäre Klassifikation)

Die Standardmetrik für binäre Klassifizierungsprobleme ist **accuracy**. Sie definiert den Anteil an genauen Vorhersagen, die Ihr Modell anhand des Testdatasets trifft. Je **näher der Wert an 100 % liegt, desto besser ist das Modell**.

Andere gemeldete Metriken wie AUC (Area under the curve, Fläche unter der Kurve), die den Anteil der tatsächlich positiven Ergebnisse mit dem Anteil der falsch positiven Ergebnisse abgleicht, sollten größer als 0,50 sein, damit Modelle akzeptabel sind.

Zusätzliche Metriken wie der F1-score können verwendet werden, um das Verhältnis zwischen „Precision“ (Genauigkeit) (Verhältnis der korrekten Vorhersagen zu den Gesamtvorhersagen dieser Klasse) und „Recall“ (Wiedererkennung) (Verhältnis der korrekten Vorhersagen zu den gesamten tatsächlichen Membern dieser Klasse) zu steuern.

### <a name="issue-classification-multiclass-classification"></a>Fehlerklassifizierung (Multiklassenklassifizierung)

Die Standardmetrik für Multiklassen-Klassifizierungsprobleme ist **micro accuracy**. Je **näher der Wert an 100 % liegt, desto besser ist das Modell**.

Bei Problemen, bei denen Daten in mehrere Klassen eingeteilt werden, gibt es zwei Arten von Genauigkeit:

- Micro-accuracy: der Anteil an Vorhersagen, die für alle Instanzen korrekt waren. Im Szenario der Problemklassifizierung ist die „micro-accuracy“ der Anteil der eingehenden Probleme, die der richtigen Kategorie zugeordnet werden.
- Macro-accuracy: die durchschnittliche Genauigkeit auf Klassenebene. Im Szenario der Problemklassifizierung wird die Genauigkeit für jede Kategorie gemessen, und anschließend werden die Genauigkeiten der Kategorie gemittelt. Für diese Metrik erhalten alle Klassen die gleiche Gewichtung. Für perfekt ausgewogene Datensätze (bei denen es in jeder Kategorie die gleiche Anzahl von Beispielen gibt), sind „micro-accuracy“ and „macro-accuracy“ gleich.

### <a name="price-prediction-regression"></a>Preisvorhersage (Regression)

Ist die Standardmetrik für Regressionsprobleme ist **R-squared**. 1 ist der beste mögliche Wert. Je näher R-squared an 1 liegt, umso besser ist das Modell.

Andere gemeldete Metriken wie „Absolute-loss“, „Squared-loss“ und „RMS-loss“ können verwendet werden, um Ihr Modell zu verstehen und es mit anderen Regressionsmodellen zu vergleichen.

## <a name="improve"></a>Verbessern

Wenn Ihr Modellleistungswert nicht so gut ist, wie Sie es sich wünschen, haben Sie die folgenden Möglichkeit:

* Längeres Trainieren. Mit mehr Zeit kann die automatisierte Machine Learning-Engine mehrere Algorithmen und Einstellungen auszuprobieren.

* Weitere Daten hinzufügen. Manchmal reicht die Datenmenge nicht aus, um ein hochwertiges Machine Learning-Modell zu trainieren.

* Ihre Daten ausgleichen. Achten Sie bei Klassifizierungsaufgaben darauf, dass der Trainingssatz über die Kategorien hinweg gleichmäßig verteilt ist. Wenn Sie beispielsweise vier Klassen für 100 Trainingsbeispiele haben und die beiden ersten Klassen (tag1 und tag2) für 90 Datensätze verwendet werden, die anderen beiden (tag3 und tag4) aber nur für die restlichen 10 Datensätze, kann das dazu führen, dass Ihr Modell Schwierigkeiten hat, tag3 oder tag4 korrekt vorherzusagen, da die Daten nicht gleichmäßig verteilt sind.

## <a name="code"></a>Code

Nach der Evaluierungsphase gibt der Modell-Generator eine Modelldatei und einen Code aus, mit dem Sie das Modell zur Ihrer Anwendung hinzufügen können. ML.NET-Modelle werden als Zip-Datei gespeichert. Der Code zum Laden und Verwenden Ihres Modells wird als neues Projekt in Ihrer Projektmappe hinzugefügt. Der Modell-Generator fügt auch eine Beispiel-Konsolen-App hinzu, die Sie ausführen können, um Ihr Modell in Aktion zu sehen.

Darüber hinaus gibt der Modell-Generator den Code aus, der das Modell generiert hat, sodass Sie die Schritte zur Generierung des Modells nachvollziehen können. Sie können den Modelltrainingscode auch verwenden, um Ihr Modell mit neuen Daten zu trainieren.

## <a name="whats-next"></a>Ausblick

Probieren Sie ein [Szenario für die Preisvorhersage oder Regression](tutorials/predict-prices-with-model-builder.md) aus.
