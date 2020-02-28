---
title: Befehlsreferenz für die ML.NET-CLI
description: Übersicht, Beispiele und Verweise für den Befehl „auto-train“ im ML.NET-CLI-Tool
ms.date: 12/18/2019
ms.openlocfilehash: 537f8d361c170378f5fe8cf454320831d7c8cbf2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449698"
---
# <a name="the-mlnet-cli-command-reference"></a>Befehlsreferenz für die ML.NET-CLI

Der `auto-train`-Befehl ist der Hauptbefehl des ML.NET-CLI-Tools. Mit dem Befehl können Sie ein qualitativ hochwertiges ML.NET-Modell mithilfe von automatisiertem maschinellen Lernen (AutoML) sowie den C#-Beispielcode generieren, um dieses Modell auszuführen bzw. zu bewerten. Außerdem wird der C#-Code zum Trainieren des Modells für Sie generiert, damit Sie den Algorithmus und die Einstellungen des Modells untersuchen können.

> [!NOTE]
> Dieses Thema bezieht sich auf die ML.NET-CLI und ML.NET AutoML, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.

## <a name="overview"></a>Übersicht

Verwendungsbeispiel:

```console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

Der Befehl `mlnet auto-train` generiert folgende Objekte:

- Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort verwendet werden kann.
- C#-Code zum Ausführen/Bewerten des generierten Modells.
- C#-Code mit dem Trainingscode, der zur Erstellung dieses Modells verwendet wird.

Die ersten beiden Objekte können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem Modell Vorhersagen zu treffen.

Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie den spezifischen Algorithmus und die Einstellungen des Modells untersuchen können.

## <a name="examples"></a>Beispiele

Der einfachste CLI-Befehl für ein binäres Klassifizierungsproblem (AutoML leitet den Großteil der Konfiguration aus den bereitgestellten Daten ab):

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

Ein weiterer einfacher CLI-Befehl für ein Regressionsproblem:

``` console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

Erstellen und trainieren Sie ein binäres Klassifizierungsmodell mit einem Trainingsdataset, einem Testdataset und weiteren benutzerdefinierten Argumenten:

```console
mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="command-options"></a>Befehlsoptionen

`mlnet auto-train`: Trainiert mehrere Modelle basierend auf dem bereitgestellten Dataset und wählt schließlich das beste Modell aus, speichert es als serialisierte ZIP-Datei und generiert außerdem den zugehörigen C#-Code für Bewertung und Training.

```console
mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

Ungültige Eingabeoptionen bewirken, dass das CLI-Tool eine Liste gültiger Eingaben und eine Fehlermeldung ausgibt.

## <a name="task"></a>Aufgabe

`--task | --mltask | -T` (Zeichenfolge)

Eine einzelne Zeichenfolge, die das zu lösende ML-Problem enthält. Zum Beispiel eine der folgenden Aufgaben (die CLI wird später alle in AutoML unterstützten Aufgaben unterstützen):

- `regression` – Wählen Sie, ob das ML-Modell zur Vorhersage eines numerischen Werts verwendet werden soll.
- `binary-classification` –Wählen Sie, ob das Ergebnis des ML-Modells zwei mögliche kategorische boolesche Werte hat (0 oder 1).
- `multiclass-classification` –Wählen Sie, ob das Ergebnis des ML-Modells zwei mögliche kategorische boolesche Werte hat (0 oder 1).

In diesem Argument sollte nur eine ML-Aufgabe bereitgestellt werden.

## <a name="dataset"></a>DataSet

`--dataset | -d` (Zeichenfolge)

Dieses Argument stellt den Dateipfad zu einer der folgenden Optionen bereit:

- *A: Die gesamte Datasetdatei:* Wenn Sie diese Option verwenden und der Benutzer das `--test-dataset` und das `--validation-dataset` nicht bereitstellt, werden intern Kreuzvalidierungen (k-fach, etc.) oder automatisierte Verfahren zur Aufteilung das Daten für die Validierung des Modells verwendet. In diesem Fall muss der Benutzer nur den Dateipfad zum Dataset angeben.

- *B: Die Datei für das Trainingsdataset:* Wenn der Benutzer auch Datasets für die Modellvalidierung bereitstellt (mit `--test-dataset` und optional `--validation-dataset`), dann bedeutet das Argument `--dataset`, dass nur das „Trainingsdataset“ vorhanden ist. Wenn Sie beispielsweise 80%-20%ig-Ansatz zur Validierung der Modellqualität und zum Ermitteln von Genauigkeitsmetriken verwenden, enthält das „Trainingsdataset“ 80 % der Daten und das „Testdataset“ 20 % der Daten.

## <a name="test-dataset"></a>Testdataset

`--test-dataset | -t` (Zeichenfolge)

Dateipfad, der auf die Datei des Testdatasets zeigt, z.B. bei Verwendung eines 80%-20%-Ansatzes bei regelmäßigen Validierungen zur Ermittlung von Genauigkeitsmetriken.

Bei der Verwendung des `--test-dataset` ist auch das `--dataset` erforderlich.

Das `--test-dataset`-Argument ist optional, sofern das „--validation-dataset“ verwendet wird. In diesem Fall muss der Benutzer die drei Argumente verwenden.

## <a name="validation-dataset"></a>Validierungsdataset

`--validation-dataset | -v` (Zeichenfolge)

Dateipfad, der auf die Datei für das Validierungsdataset zeigt. Das Validierungsdataset ist in jedem Fall optional.

Bei der Verwendung des `validation dataset` sollte folgendes Verhalten auftreten:

- Es sind auch die `test-dataset`- und `--dataset`-Argumente erforderlich.

- Das `validation-dataset`-Dataset wird verwendet, um den Vorhersagefehler für die Modellauswahl zu schätzen.

- Das `test-dataset` wird zur Beurteilung des Generalisierungsfehlers des endgültig ausgewählten Modells verwendet. Idealerweise sollte das Testset in einem „Tresor“ aufbewahrt werden und erst am Ende der Datenanalyse zur Anwendung kommen.

Grundsätzlich wird bei die Validierungsphase bei Verwendung eines `validation dataset` plus des `test dataset` in zwei Teile aufgeteilt:

1. Im ersten Teil betrachten Sie einfach Ihre Modelle und wählen den leistungsstärksten Ansatz anhand der Validierungsdaten (=Validierung) aus.
2. Dann schätzen Sie die Genauigkeit des gewählten Ansatzes (=Test).

Daher sollten die Daten im Verhältnis 80/10/10 oder 75/15/10 geteilt werden. Zum Beispiel:

- Die Datei `training-dataset` sollte 75 % der Daten enthalten.
- Die Datei `validation-dataset` sollte 15 % der Daten enthalten.
- Die Datei `test-dataset` sollte 10 % der Daten enthalten.

In jedem Fall entscheidet der Benutzer anhand der CLI, die die bereits aufgeteilten Dateien bereitstellt, über die Prozentangaben.

## <a name="label-column-name"></a>Bezeichnung Spaltenname

`--label-column-name | -n` (Zeichenfolge)

Mit diesem Argument kann eine bestimmte Objekt-/Zielspalte (die Variable, die Sie vorhersagen möchten) angegeben werden, indem der Name der Spalte im Header des Datasets verwendet wird.

Dieses Argument wird nur für überwachte ML-Aufgaben verwendet, wie z.B. ein *Klassifizierungsproblem*. Es kann nicht für nicht überwachte ML-Aufgaben verwendet werden, wie z.B. *Clustering*.

## <a name="label-column-index"></a>Bezeichnung Spaltenindex

`--label-column-index | -i` (Ganzzahl)

Mit diesem Argument kann eine bestimmte Ziel-/Zielspalte (die Variable, die Sie vorhersagen möchten) angegeben werden, indem Sie den numerischen Index der Spalte in der Datasetdatei verwenden (Spaltenindexwerte beginnen bei 1).

*Hinweis*: Wenn der Benutzer auch `--label-column-name` verwendet, wird `--label-column-name` verwendet.

Dieses Argument wird nur für eine überwachte ML-Aufgabe verwendet, wie z.B. ein *Klassifizierungsproblem*. Es kann nicht für nicht überwachte ML-Aufgaben verwendet werden, wie z.B. *Clustering*.

## <a name="ignore-columns"></a>Spalten ignorieren

`--ignore-columns | -I` (Zeichenfolge)

Mit diesem Argument können Sie vorhandene Spalten in der Datasetdatei ignorieren, sodass sie nicht geladen und nicht in den Trainingsprozessen verwendet werden.

Geben Sie die Namen der Spalten an, die Sie ignorieren möchten. Verwenden Sie „, „ (Komma mit Leerzeichen) oder „ „ (Leerzeichen), um mehrere Spaltennamen zu trennen. Sie können Anführungszeichen für Spaltennamen verwenden, die Leerzeichen enthalten (z.B. „ist angemeldet“).

Beispiel:

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a>Hat Header

`--has-header | -h` (Bool)

Geben Sie an, ob die Datasetdatei(en) eine Kopfzeile enthält/enthalten.
Dabei sind folgende Werte möglich:

- `true`
- `false`

Der Standardwert ist `true`, wenn der Benutzer dieses Argument nicht angibt.

Um das `--label-column-name`-Argument zu verwenden, benötigen Sie in der Datasetdatei einen Header und `--has-header` muss auf `true` (Standardwert) gesetzt werden.

## <a name="max-exploration-time"></a>Maximale Auswertungszeit

`--max-exploration-time | -x` (Zeichenfolge)

Die maximale Untersuchungszeit beträgt standardmäßig 30 Minuten.

Dieses Argument legt die maximale Zeit (in Sekunden) für den Prozess fest, um mehrere Trainer und Konfigurationen zu untersuchen. Die konfigurierte Zeit kann überschritten werden, wenn die angegebene Zeit für eine einzelne Iteration zu kurz ist (z.B. 2 Sekunden). In diesem Fall ist die tatsächliche Zeit die erforderliche Zeit, um eine Modellkonfiguration in einer einzigen Iteration zu erstellen.

Die für Iterationen benötigte Zeit kann je nach Größe des Datasets variieren.

## <a name="cache"></a>cache

`--cache | -c` (Zeichenfolge)

Wenn Sie Caching verwenden, wird das gesamte Trainingsdataset im Speicher geladen.

Bei kleinen und mittleren Datasets kann Caching die Trainingsleistung erheblich verbessern, sodass die Trainingszeit im Vergleich zu einem Training ohne Cache kürzer sein kann.

Bei großen Datasets kann das Laden aller Daten im Speicher jedoch negative Auswirkungen haben, da Sie unter Umständen nicht mehr genügend Speicher zur Verfügung haben. Wenn Sie für das Training mit großen Datasetdateien arbeiten und keinen Cache verwenden, streamt ML.NET Datenblöcke vom Laufwerk, wenn während des Trainings mehr Daten geladen werden müssen.

Sie können folgende Werte angeben:

`on`: Erzwingt, dass während des Trainings der Cache verwendet wird
`off`: Erzwingt, dass während des Trainings der Cache nicht verwendet wird
`auto`: Je nach AutoML-Heuristiken wird der Cache verwendet oder nicht verwendet. In der Regel verwenden kleine/mittlere Datasets den Cache, und große Datasets verwenden keinen Cache, wenn Sie die Option `auto` verwenden.

Wenn Sie den `--cache`-Parameter nicht angeben, wird standardmäßig die Cachekonfiguration `auto` verwendet.

## <a name="name"></a>name

`--name | -N` (Zeichenfolge)

Der Name für das erstellte Ausgabeprojekt oder die erstellte Projektmappe. Wenn kein Name angegeben ist, wird der Name `sample-{mltask}` verwendet.

Die ML.NET-Modelldatei (ZIP-Datei) erhält ebenfalls denselben Namen.

## <a name="output-path"></a>Ausgabepfad

`--output-path | -o` (Zeichenfolge)

Stammspeicherort/-ordner für die generierte Ausgabe. Der Standardwert ist das aktuelle Verzeichnis.

## <a name="verbosity"></a>Ausführlichkeit

`--verbosity | -V` (Zeichenfolge)

Legt den Ausführlichkeitsgrad für die Standardausgabe fest.

Zulässige Werte sind:

- `q[uiet]`
- `m[inimal]` (Standardwert)
- `diag[nostic]` (Protokollierung der Informationsebene)

Standardmäßig sollte das CLI-Tool ein Mindestfeedback (minimal) anzeigen, wenn es funktioniert, wie z.B. die Angabe, dass es funktioniert und, wenn möglich, Angaben dazu, wie viel Zeit übrig ist oder wie viel Prozent der Zeit abgeschlossen sind.

## <a name="help"></a>Hilfe

`-h|--help`

Druckt die Hilfe für den Befehl und eine Beschreibung der einzelnen Parameter für den Befehl aus.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Installieren des ML.NET-CLI-Tools](../how-to-guides/install-ml-net-cli.md)
- [Übersicht über die ML.NET-CLI](../automate-training-with-cli.md)
- [Tutorial: Stimmungsanalyse über die ML.NET-Befehlszeilenschnittstelle](../tutorials/sentiment-analysis-cli.md)
- [Telemetrie in der ML.NET-CLI](../resources/ml-net-cli-telemetry.md)
