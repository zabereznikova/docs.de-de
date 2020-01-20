---
title: Was ist der Modell-Generator und wie funktioniert er?
description: Erfahren Sie mehr über die Verwendung des ML.NET-Modell-Generators zum automatischen Trainieren eines Machine Learning-Modells.
ms.date: 01/07/2020
ms.custom: overview
ms.openlocfilehash: ac704b7961a8442a9174cdef5a4cd2a619236a4e
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777393"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>Was ist der Modell-Generator und wie funktioniert er?

Der ML.NET-Modell-Generator ist eine intuitive grafische Visual Studio-Erweiterung zum Erstellen, Trainieren und Bereitstellen von benutzerdefinierten Machine Learning-Modellen.

Der Modell-Generator verwendet automatisiertes maschinelles Lernen (AutoML), um verschiedene Machine Learning-Algorithmen und Einstellungen zu untersuchen, damit Sie die optimalen Einstellungen für Ihr Szenario ermitteln können.

Für die Verwendung des Modell-Generators sind keine Machine Learning-Kenntnisse erforderlich. Sie benötigen lediglich einige Daten und ein Problem, das Sie lösen möchten. Modell-Generator generiert den Code, um das Modell zur Ihrer .NET-Anwendung hinzuzufügen.

![Animation der Benutzeroberfläche der Visual Studio-Erweiterung für den Modell-Generator](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> Der Modell-Generator befindet sich derzeit in der Vorschauphase.

## <a name="scenarios"></a>Szenarien

Sie können viele verschiedene Szenarien in den Modell-Generator einbinden, um ein Machine Learning-Modell für Ihre Anwendung zu erstellen.

Ein Szenario ist eine Beschreibung der Art der Vorhersage, die Sie mit Ihren Daten treffen möchten. Zum Beispiel:

- Vorhersagen des zukünftigen Produktabsatzes auf der Grundlage historischer Verkaufsdaten
- Klassifizieren der Stimmungen als positiv oder negativ anhand von Kundenrezensionen
- Erkennen einer betrügerischen Banktransaktion
- Weiterleiten von Problemen beim Kundenfeedback an das richtige Team in Ihrem Unternehmen

### <a name="which-machine-learning-scenario-is-right-for-me"></a>Welches Machine Learning-Szenario ist für mich geeignet?

Im Modell-Generator müssen Sie ein Szenario auswählen. Der Typ des Szenarios hängt davon ab, welchen Typ von Vorhersage Sie treffen möchten.

#### <a name="predict-a-category-when-there-are-only-two-categories"></a>Vorhersagen einer Kategorie (wenn nur zwei Kategorien vorliegen)

Die binäre Klassifizierung wird verwendet, um Daten in zwei Kategorien zu unterteilen (ja/nein; Erfolg/Fehler; wahr/falsch; positiv/negativ).

![Diagramm mit Beispielen für die binäre Klassifizierung, einschließlich Betrugserkennung, Risikominderung und Bewerbungsüberprüfung](media/binary-classification-examples.png)

Die Standpunktanalyse kann verwendet werden, um positive oder negative Stimmungen im Kundenfeedback vorherzusagen. Es ist ein Beispiel für die binäre Machine Learning-Klassifizierungsaufgabe.

Wenn Ihr Szenario eine Klassifizierung in zwei Kategorien erfordert, können Sie diese Vorlage mit einem eigenen Dataset verwenden.

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a>Vorhersagen einer Kategorie (wenn drei oder mehr Kategorien vorliegen)

Die Multiklassenklassifizierung kann für die Kategorisierung von Daten in drei oder mehr Klassen verwendet werden.

![Beispiele für die Mehrklassenklassifizierung, einschließlich Dokument- und Produktklassifizierung, Supportticketweiterleitung und Kundenproblempriorisierung](media/multiclass-classification-examples.png)

Die Fehlerklassifizierung kann verwendet werden, um Kundenfeedback (z.B. zu GitHub) anhand des Problemtitels und der Beschreibung zu kategorisieren. Es ist ein Beispiel für die Machine Learning-Multiklassen-Klassifizierungsaufgabe.

Sie können die Vorlage für die Fehlerklassifizierung für Ihr Szenario verwenden, wenn Sie Daten in drei oder mehr Kategorien einteilen möchten.

#### <a name="predict-a-number"></a>Vorhersagen einer Zahl

Die Regression wird verwendet, um Zahlen vorherzusagen.

![Diagramm mit Regressionsbeispielen wie Preisvorhersagen, Umsatzvorhersagen und Predictive Maintenance](media/regression-examples.png)

Die Preisvorhersage kann verwendet werden, um Hauspreise anhand von Lage, Größe und anderen Merkmalen des Hauses vorherzusagen. Es ist ein Beispiel für die Machine Learning-Regressionsaufgabe.

Sie können die Vorlage für die Preisvorhersage für Ihr Szenario verwenden, wenn Sie einen Zahlenwert mit einem eigenen Dataset vorhersagen möchten.

#### <a name="classify-images-into-categories"></a>Klassifizieren von Bildern in Kategorien

Bei diesem Szenario handelt es sich um einen Sonderfall der Klassifizierung mit mehreren Klassen, bei dem die zu kategorisierenden Eingabedaten aus einem Satz von Bildern bestehen.

Bildklassifizierung kann verwendet werden, um Bilder unterschiedlicher Kategorien zu identifizieren. Beispiele hierfür sind unterschiedliche Arten von Gelände, Tieren oder Fertigungsfehlern.

Sie können die Bildklassifizierungsvorlage für Ihr Szenario verwenden, wenn Sie über einen Satz von Bildern verfügen und die Bilder in verschiedene Kategorien klassifizieren möchten.

#### <a name="custom-scenario"></a>Benutzerdefiniertes Szenario

Im benutzerdefinierten Szenario können Sie Ihr Szenario manuell auswählen.

## <a name="data"></a>Daten

Sobald Sie Ihr Szenario ausgewählt haben, fordert der Modell-Generator Sie auf, ein Dataset bereitzustellen. Die Daten werden verwendet, um das beste Modell für Ihr Szenario zu trainieren, zu evaluieren und auszuwählen.

![Diagramm mit dem Schritten im Modellgenerator](media/model-builder-steps.png)

Der Modell-Generator unterstützt Datasets im TSV-, CSV- und TXT-Format sowie im SQL-Datenbankformat. Wenn Sie über eine TXT-Datei verfügen, müssen die Spalten durch `,`, `;` oder `/t` getrennt werden, und die Datei muss eine Kopfzeile aufweisen.

Wenn das Dataset aus Bildern besteht, sind die unterstützten Dateitypen `.jpg` und `.png`.

Weitere Informationen finden Sie unter [Laden von Trainingsdaten in den Modell-Generator](how-to-guides/load-data-model-builder.md).

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

### <a name="example-datasets"></a>Beispieldatasets

Wenn Sie noch keine eigenen Daten haben, probieren Sie eines dieser Datasets aus:

|Szenario|ML-Aufgabe|Daten|Bezeichnung|Features|
|-|-|-|-|-|
|Preisvorhersage|Regression|[taxi fare data](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Preis|Fahrtzeit, Strecke|
|Anomalieerkennung|Binäre Klassifizierung|[product sales data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Produktverkäufe|Monat|
|Standpunktanalyse|Binäre Klassifizierung|[website comment data](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|Bezeichnung (0 bei negativer Stimmung, 1, wenn positiv)|Kommentar, Jahr|
|Betrugserkennung|Binäre Klassifizierung|[credit card data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Klasse (1, wenn betrügerisch, andernfalls 0)|Betrag, V1-V28 (anonymisierte Features)|
|Textklassifizierung|Multiklassenklassifizierung|[GitHub issue data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Bereich|Titel, Beschreibung|
|Bildklassifizierung|Multiklassenklassifizierung|[Blumenbilder](http://download.tensorflow.org/example_images/flower_photos.tgz)|Der Typ Blume: Gänseblümchen, Löwenzahn, Rosen, Sonnenblumen, Tulpen|Die Bilddaten selbst|

## <a name="train"></a>Training

Sobald Sie Ihr Szenario, Ihre Daten und Ihre Bezeichnung ausgewählt haben, trainiert der Modell-Generator das Modell.

### <a name="what-is-training"></a>Was bedeutet Training?

Das Training ist ein automatischer Prozess, bei dem der Modellgenerator dem Modell beibringt, wie es Fragen für Ihr Szenario beantworten kann. Nach dem Training kann Ihr Modell Vorhersagen mit ihm bisher unbekannten Eingabedaten treffen. Wenn Sie zum Beispiel die Hauspreise vorhersagen und ein neues Haus auf den Markt kommt, können Sie seinen Verkaufspreis vorhersagen.

Da der Modell-Generator automatisiertes maschinelles Lernen (AutoML) verwendet, ist während des Trainings keine Eingabe oder Anpassung durch Sie erforderlich.

### <a name="how-long-should-i-train-for"></a>Wie lange sollte ich das Modell trainieren?

Der Modell-Generator verwendet AutoML zum Untersuchen mehrerer Modelle, um das Modell mit der besten Leistung zu ermitteln.

Längere Trainingszeiträume ermöglichen es AutoML, mehr Modelle mit einer breiteren Palette von Einstellungen zu untersuchen.

In der folgenden Tabelle wird die durchschnittliche Zeit zusammengefasst, die benötigt wird, um eine gute Leistung für eine Suite von Beispieldatasets auf einem lokalen Computer zu erzielen.

|Datasetgröße|Durchschnittliche Trainingszeit|
|------------|---------------------|
|0 bis 10 MB|10 Sek.|
|10 bis 100 MB|10 Min.|
|100 bis 500 MB|30 Min.|
|500 MB bis 1 GB|60 Min.|
|Mehr als 1 GB|Mehr als 3 Stunden|

Diese Zahlen sind nur eine Richtlinie. Die genaue Trainingsdauer ist abhängig von:

- Anzahl der Merkmale (Spalten), die als Eingabe für das Modell verwendet werden
- Typ der Spalten
- ML-Aufgabe
- CPU-, Datenträger- und Arbeitsspeicherleistung des für das Training verwendeten Computers

## <a name="evaluate"></a>Auswerten

Auswertung ist der Prozess, bei dem gemessen wird, wie gut das Modell ist. Der Modell-Generator verwendet das trainierte Modell, um Vorhersagen mit neuen Testdaten zu treffen und anschließend zu messen, wie gut die Vorhersagen sind.

Der Modell-Generator unterteilt die Trainingsdaten in einen Trainingssatz und einen Testsatz. Die Trainingsdaten (80 %) werden zum Trainieren Ihres Modells verwendet, und die Testdaten (20 %) zur Evaluierung Ihres Modells zurückgehalten. 

### <a name="how-do-i-understand-my-model-performance"></a>Wie gewinne ich ein Verständnis für die Modellleistung?

Ein Szenario wird einer Machine Learning-Aufgabe zugeordnet. Jede ML-Aufgabe verfügt über einen eigenen Satz von Auswertungsmetriken.

#### <a name="regression-for-example-price-prediction"></a>Regression (z. B. Preisvorhersage)

Die Standardmetrik für Regressionsprobleme ist RSquared. Der Wert von RSquared liegt zwischen 0 und 1. 1 ist der bestmögliche Wert, d. h. je näher der Wert von RSquared bei 1 liegt, desto besser ist die Leistung Ihres Modells.

Andere erfasste Metriken wie „absolute-loss“, „squared-loss“ und „RMS-loss“ sind zusätzliche Metriken, die verwendet werden können, um die Leistung Ihres Modells zu verstehen und es mit anderen Regressionsmodellen zu vergleichen.

#### <a name="binary-classification-for-example-sentiment-analysis"></a>Binäre Klassifizierung (beispielsweise Standpunktanalyse)

Die Standardmetrik für binäre Klassifizierungsprobleme ist „accuracy“ (Genauigkeit). Sie definiert den Anteil an genauen Vorhersagen, die Ihr Modell anhand des Testdatasets trifft. Je näher der Wert bei 100 % oder 1,0 liegt, desto besser ist das Modell.

Andere gemeldete Metriken wie AUC (Area under the curve, Fläche unter der Kurve), die den Anteil der tatsächlich positiven Ergebnisse mit dem Anteil der falsch positiven Ergebnisse abgleicht, sollten größer als 0,50 sein, damit Modelle akzeptabel sind.

Zusätzliche Metriken wie die F1-Bewertung können verwendet werden, um das Gleichgewicht zwischen Genauigkeit und Rückruf zu steuern.

#### <a name="multi-class-classification-for-example-issue-classification-image-classification"></a>Mehrklassige Klassifizierung (beispielsweise Problemklassifizierung, Bildklassifizierung)

Die Standardmetrik für mehrklassige Klassifizierung ist „Micro Accuracy“. Je näher „Mico Accuracy“ bei 100 % oder 1,0 liegt, desto besser ist das Modell.

Eine weitere wichtige Metrik für die mehrklassige Klassifizierung ist „Macro-accuracy“. Ähnlich wie bei „Micro-accuracy“ ist das Modell umso besser, je näher der Wert bei 1,0 liegt. Eine gute Möglichkeit, diese beiden Genauigkeitstypen zu unterscheiden:

- Micro-accuracy: Wie oft wird ein eingehendes Ticket dem richtigen Team zugeordnet?
- Macro-accuracy: Wie oft ist für ein durchschnittliches Team ein eingehendes Ticket das richtige Ticket für das Team?

### <a name="more-information-on-evaluation-metrics"></a>Weitere Informationen zu Auswertungsmetriken

Weitere Informationen finden Sie unter [Metriken für die Modellevaluierung](resources/metrics.md).

## <a name="improve"></a>Verbessern

Wenn Ihr Modellleistungswert nicht so gut ist, wie Sie es sich wünschen, haben Sie die folgenden Möglichkeit:

- Längeres Trainieren. Mit mehr Zeit kann die automatisierte Machine Learning-Engine mehrere Algorithmen und Einstellungen auszuprobieren.

- Weitere Daten hinzufügen. Manchmal reicht die Datenmenge nicht aus, um ein hochwertiges Machine Learning-Modell zu trainieren.

- Ihre Daten ausgleichen. Achten Sie bei Klassifizierungsaufgaben darauf, dass der Trainingssatz über die Kategorien hinweg gleichmäßig verteilt ist. Wenn Sie beispielsweise vier Klassen für 100 Trainingsbeispiele haben und die beiden ersten Klassen (tag1 und tag2) für 90 Datensätze verwendet werden, die anderen beiden (tag3 und tag4) aber nur für die restlichen 10 Datensätze, kann das dazu führen, dass Ihr Modell Schwierigkeiten hat, tag3 oder tag4 korrekt vorherzusagen, da die Daten nicht gleichmäßig verteilt sind.

## <a name="code"></a>Code

Nach der Evaluierungsphase gibt der Modell-Generator eine Modelldatei und einen Code aus, mit dem Sie das Modell zur Ihrer Anwendung hinzufügen können. ML.NET-Modelle werden als Zip-Datei gespeichert. Der Code zum Laden und Verwenden Ihres Modells wird als neues Projekt in Ihrer Projektmappe hinzugefügt. Der Modell-Generator fügt auch eine Beispiel-Konsolen-App hinzu, die Sie ausführen können, um Ihr Modell in Aktion zu sehen.

Darüber hinaus gibt der Modell-Generator den Code aus, der das Modell generiert hat, sodass Sie die Schritte zur Generierung des Modells nachvollziehen können. Sie können den Modelltrainingscode auch verwenden, um Ihr Modell mit neuen Daten zu trainieren.

## <a name="whats-next"></a>Ausblick

[Installieren](how-to-guides/install-model-builder.md) Sie die Modellgeneratorerweiterung für Visual Studio.

Probieren Sie ein [Szenario für die Preisvorhersage oder Regression](tutorials/predict-prices-with-model-builder.md) aus.
