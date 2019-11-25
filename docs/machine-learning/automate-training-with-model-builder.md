---
title: Was ist der Modell-Generator und wie funktioniert er?
description: Erfahren Sie mehr über die Verwendung des ML.NET-Modell-Generators zum automatischen Trainieren eines Machine Learning-Modells.
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: 77fe56dba3532617ad9fb0c89bfaac7c8e031ce7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971521"
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

Ein Szenario ist eine Beschreibung der Art der Vorhersage, die Sie mit Ihren Daten treffen möchten. Beispiel:

- Vorhersagen des zukünftigen Produktabsatzes auf der Grundlage historischer Verkaufsdaten
- Klassifizieren der Stimmungen als positiv oder negativ anhand von Kundenrezensionen
- Erkennen einer betrügerischen Banktransaktion
- Weiterleiten von Problemen beim Kundenfeedback an das richtige Team in Ihrem Unternehmen

## <a name="choose-a-model-type"></a>Auswählen eines Modelltyps

Sie müssen einen Machine-Learning-Modelltyp im Modellgenerator auswählen. Der Modelltyp hängt davon ab, welche Art von Vorhersage Sie erzielen möchten.

Für Szenarios, bei denen Sie eine Zahl vorhersagen möchten, lautet der Machine-Learning-Modelltyp `regression`.

Für Szenarios, bei denen Sie eine Kategorie vorhersagen möchten, lautet der Machine-Learning-Modelltyp `classification`. Es gibt zwei Arten von Klassifizierung:

- Klassifizierungen mit nur zwei Kategorien: `binary classification`.
- Klassifizierungen mit drei oder mehr Kategorien: `multiclass classification`.

### <a name="which-model-type-is-right-for-me"></a>Welches Modell eignet sich für mich?

#### <a name="predict-a-category-when-there-are-only-two-categories"></a>Vorhersagen einer Kategorie (wenn nur zwei Kategorien vorliegen)

Die binäre Klassifizierung wird verwendet, um Daten in zwei Kategorien zu unterteilen (ja/nein; Erfolg/Fehler; wahr/falsch; positiv/negativ).

![Diagramm mit Beispielen für die binäre Klassifizierung, einschließlich Betrugserkennung, Risikominderung und Bewerbungsüberprüfung](media/binary-classification-examples.png)

Die Standpunktanalyse kann verwendet werden, um positive oder negative Stimmungen im Kundenfeedback vorherzusagen. Dies ist ein Beispiel für einen binären Klassifizierungsmodelltyp.

Wenn Ihr Szenario eine Klassifizierung in zwei Kategorien erfordert, können Sie diese Vorlage mit einem eigenen Dataset verwenden.

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a>Vorhersagen einer Kategorie (wenn drei oder mehr Kategorien vorliegen)

Die Multiklassenklassifizierung kann für die Kategorisierung von Daten in drei oder mehr Klassen verwendet werden.

![Beispiele für die Mehrklassenklassifizierung, einschließlich Dokument- und Produktklassifizierung, Supportticketweiterleitung und Kundenproblempriorisierung](media/multiclass-classification-examples.png)

Die Fehlerklassifizierung kann verwendet werden, um Kundenfeedback (z.B. zu GitHub) anhand des Problemtitels und der Beschreibung zu kategorisieren. Dies ist ein Beispiel für den Modelltyp für Multiklassenklassifizierung.

Sie können die Vorlage für die Fehlerklassifizierung für Ihr Szenario verwenden, wenn Sie Daten in drei oder mehr Kategorien einteilen möchten.

#### <a name="predict-a-number"></a>Vorhersagen einer Zahl

Die Regression wird verwendet, um Zahlen vorherzusagen.

![Diagramm mit Regressionsbeispielen wie Preisvorhersagen, Umsatzvorhersagen und Predictive Maintenance](media/regression-examples.png)

Die Preisvorhersage kann verwendet werden, um Hauspreise anhand von Lage, Größe und anderen Merkmalen des Hauses vorherzusagen. Dies ist ein Beispiel für den Regressionsmodelltyp.

Sie können die Vorlage für die Preisvorhersage für Ihr Szenario verwenden, wenn Sie einen Zahlenwert mit einem eigenen Dataset vorhersagen möchten.

#### <a name="custom-scenario-choose-your-model-type"></a>Benutzerdefiniertes Szenario (wählen Sie Ihren Modelltyp aus)

Im benutzerdefinierten Szenario können Sie Ihren Modelltyp manuell auswählen.

## <a name="data"></a>Daten

Sobald Sie Ihren Modelltyp ausgewählt haben, fordert der Modellgenerator Sie auf, ein Dataset bereitzustellen. Die Daten werden verwendet, um das beste Modell für Ihr Szenario zu trainieren, zu evaluieren und auszuwählen.

![Diagramm mit dem Schritten im Modellgenerator](media/model-builder-steps.png)

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

|Szenario|Modelltyp|Daten|Bezeichnung|Features|
|-|-|-|-|-|
|Preisvorhersage|Regression|[taxi fare data](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Preis|Fahrtzeit, Strecke|
|Anomalieerkennung|Binäre Klassifizierung|[product sales data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Produktverkäufe|Monat|
|Stimmungsanalyse|Binäre Klassifizierung|[website comment data](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|Bezeichnung (0 bei negativer Stimmung, 1, wenn positiv)|Kommentar, Jahr|
|Betrugserkennung|Binäre Klassifizierung|[credit card data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Klasse (1, wenn betrügerisch, andernfalls 0)|Betrag, V1-V28 (anonymisierte Features)|
|Textklassifizierung|Multiklassenklassifizierung|[GitHub issue data](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Bereich|Titel, Beschreibung|

## <a name="train"></a>Trainieren

Sobald Sie Ihr Szenario, Ihre Daten und Ihre Bezeichnung ausgewählt haben, trainiert der Modell-Generator das Modell.

### <a name="what-is-training"></a>Was bedeutet Training?

Das Training ist ein automatischer Prozess, bei dem der Modellgenerator dem Modell beibringt, wie es Fragen für Ihr Szenario beantworten kann. Nach dem Training kann Ihr Modell Vorhersagen mit ihm bisher unbekannten Eingabedaten treffen. Wenn Sie zum Beispiel die Hauspreise vorhersagen und ein neues Haus auf den Markt kommt, können Sie seinen Verkaufspreis vorhersagen.

Da der Modell-Generator automatisiertes maschinelles Lernen (AutoML) verwendet, ist während des Trainings keine Eingabe oder Anpassung durch Sie erforderlich.

## <a name="evaluate"></a>Auswerten

Unter Evaluierung versteht man den Prozess, bei dem mit dem trainierten Modell Vorhersagen mit neuen Testdaten getroffen werden und anschließend gemessen wird, wie gut die Vorhersagen sind.

Der Modell-Generator unterteilt die Trainingsdaten in einen Trainingssatz und einen Testsatz. Die Trainingsdaten (80 %) werden zum Trainieren Ihres Modells verwendet, und die Testdaten (20 %) zur Evaluierung Ihres Modells zurückgehalten. Der Modellgenerator verwendet Metriken, um zu messen, wie gut das Modell ist. Welche spezifischen Metriken verwendet werden, hängt vom Modelltyp ab. Weitere Informationen finden Sie unter [Metriken für die Modellevaluierung](resources/metrics.md).

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
