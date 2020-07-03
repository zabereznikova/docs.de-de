---
title: Befehlsreferenz für die ML.NET-CLI
description: Übersicht, Beispiele und Verweise für den Befehl „auto-train“ im ML.NET-CLI-Tool
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 397f6fda8554024624b3ef630856dc8eca9696b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594542"
---
# <a name="the-mlnet-cli-command-reference"></a>Befehlsreferenz für die ML.NET-CLI

Die Befehle `classification`, `regression` und `recommendation` sind die Hauptbefehle, die vom ML.NET-CLI-Tool bereitgestellt werden. Mit diesen Befehlen können Sie ein qualitativ hochwertiges ML.NET-Modell für Klassifizierungs-, Regressions- und Empfehlungsmodelle mithilfe von automatisiertem maschinellen Lernen (AutoML) sowie den C#-Beispielcode generieren, um dieses Modell auszuführen bzw. zu bewerten. Außerdem wird der C#-Code zum Trainieren des Modells für Sie generiert, damit Sie den Algorithmus und die Einstellungen des Modells untersuchen können.

> [!NOTE]
> Dieses Thema bezieht sich auf die ML.NET-CLI und ML.NET AutoML, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.

## <a name="overview"></a>Übersicht

Verwendungsbeispiel:

```console
mlnet regression --dataset "cars.csv" --label-col price
```

Mit den `mlnet`-Befehlen für ML-Tasks (`classification`, `regression` und `recommendation`) werden die folgenden Objekte generiert:

- Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort verwendet werden kann.
- C#-Code zum Ausführen/Bewerten des generierten Modells.
- C#-Code mit dem Trainingscode, der zur Erstellung dieses Modells verwendet wird.

Die ersten beiden Objekte können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem Modell Vorhersagen zu treffen.

Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie den spezifischen Algorithmus und die Einstellungen des Modells untersuchen können.

## <a name="examples"></a>Beispiele

Der einfachste CLI-Befehl für ein Klassifizierungsproblem (AutoML leitet den Großteil der Konfiguration aus den bereitgestellten Daten ab):

```console
mlnet classification --dataset "customer-feedback.tsv" --label-col Sentiment
```

Ein weiterer einfacher CLI-Befehl für ein Regressionsproblem:

``` console
mlnet regression --dataset "cars.csv" --label-col Price
```

Erstellen und trainieren Sie ein Klassifizierungsmodell mit einem Trainingsdataset, einem Testdataset und weiteren expliziten Anpassungsargumenten:

```console
mlnet classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-col "InsuranceRisk" --cache on --train-time 600
```

## <a name="command-options"></a>Befehlsoptionen

Die `mlnet`-Befehle für ML-Tasks (`classification`, `regression` und `recommendation`) trainieren mehrere Modelle basierend auf dem bereitgestellten Dataset und den bereitgestellten ML.NET-CLI-Optionen. Diese Befehle wählen außerdem das beste Modell aus, speichern das Modell als serialisierte ZIP-Datei und generieren zugehörigen C#-Code für die Bewertung und das Training.

### <a name="classification-options"></a>Klassifizierungsoptionen

Durch das Ausführen von `mlnet classification` wird ein Klassifizierungsmodell trainiert. Wählen Sie diesen Befehl aus, wenn Sie möchten, dass ein ML-Modell Daten in mindestens zwei Klassen kategorisiert (z. B. bei der Standpunktanalyse).

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="regression-options"></a>Regressionsoptionen

Durch das Ausführen von `mlnet regression` wird ein Regressionsmodell trainiert. Wählen Sie diesen Befehl aus, wenn Sie möchten, dass ein ML-Modell einen numerischen Wert vorhersagt (z. B. Preisvorhersage).

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="recommendation-options"></a>Empfehlungsoptionen

Durch das Ausführen von `mlnet recommendation` wird ein Empfehlungsmodell trainiert.  Wählen Sie diesen Befehl aus, wenn Sie möchten, dass ein ML-Modell Benutzern Artikel auf der Grundlage von Bewertungen (z. B. Produktempfehlungen) empfiehlt.

```console
mlnet classification

--dataset <path> (REQUIRED)

--item-col <col> (REQUIRED)

--rating-col <col> (REQUIRED)

--user-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

Ungültige Eingabeoptionen bewirken, dass das CLI-Tool eine Liste gültiger Eingaben und eine Fehlermeldung ausgibt.

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

## <a name="label-column"></a>Bezeichnungsspalte

`--label-col` (ganze Zahl oder Zeichenfolge)

Mit diesem Argument kann eine bestimmte Zielspalte (die Variable, die Sie vorhersagen möchten) angegeben werden, indem Sie den im Header des Dataset festgelegten Namen der Spalte oder den numerischen Index der Spalte in der Datasetdatei (Spaltenindexwerte beginnen bei 0) verwenden.

Dieses Argument wird für Probleme bei der *Klassifizierung* und der *Regression* verwendet.

## <a name="item-column"></a>Artikelspalte

`--item-col` (ganze Zahl oder Zeichenfolge)

Die Artikelspalte enthält die Liste der Artikel, die von Benutzern bewertet werden (Artikel werden Benutzern empfohlen). Diese Spalte kann angegeben werden, indem Sie den im Header des Dataset festgelegten Namen der Spalte oder den numerischen Index der Spalte in der Datasetdatei (Spaltenindexwerte beginnen bei 0) verwenden.

Dieses Argument wird nur für den *Empfehlungstask* verwendet.

## <a name="rating-column"></a>Bewertungsspalte

`--rating-col` (ganze Zahl oder Zeichenfolge)

Die Bewertungsspalte enthält die Liste der Bewertungen, die Benutzer für Artikel abgeben. Diese Spalte kann angegeben werden, indem Sie den im Header des Dataset festgelegten Namen der Spalte oder den numerischen Index der Spalte in der Datasetdatei (Spaltenindexwerte beginnen bei 0) verwenden.

Dieses Argument wird nur für den *Empfehlungstask* verwendet.

## <a name="user-column"></a>Benutzerspalte

`--user-col` (ganze Zahl oder Zeichenfolge)

Die Benutzerspalte enthält die Liste der Benutzer, die Bewertungen für Artikel abgeben. Diese Spalte kann angegeben werden, indem Sie den im Header des Dataset festgelegten Namen der Spalte oder den numerischen Index der Spalte in der Datasetdatei (Spaltenindexwerte beginnen bei 0) verwenden.

Dieses Argument wird nur für den *Empfehlungstask* verwendet.

## <a name="ignore-columns"></a>Spalten ignorieren

`--ignore-columns` (Zeichenfolge)

Mit diesem Argument können Sie vorhandene Spalten in der Datasetdatei ignorieren, sodass sie nicht geladen und nicht in den Trainingsprozessen verwendet werden.

Geben Sie die Namen der Spalten an, die Sie ignorieren möchten. Verwenden Sie „, „ (Komma mit Leerzeichen) oder „ „ (Leerzeichen), um mehrere Spaltennamen zu trennen. Sie können Anführungszeichen für Spaltennamen verwenden, die Leerzeichen enthalten (z.B. „ist angemeldet“).

Beispiel:

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a>Hat Header

`--has-header` (Bool)

Geben Sie an, ob die Datasetdatei(en) eine Kopfzeile enthält/enthalten.
Dabei sind folgende Werte möglich:

- `true`
- `false`

Die ML.NET-CLI versucht, diese Eigenschaft zu erkennen, wenn dieses Argument vom Benutzer nicht angegeben wird.

## <a name="train-time"></a>Trainingszeit

`--train-time` (Zeichenfolge)

Die maximale Untersuchungs-/Trainingszeit beträgt standardmäßig 30 Minuten.

Dieses Argument legt die maximale Zeit (in Sekunden) für den Prozess fest, um mehrere Trainer und Konfigurationen zu untersuchen. Die konfigurierte Zeit kann überschritten werden, wenn die angegebene Zeit für eine einzelne Iteration zu kurz ist (z.B. 2 Sekunden). In diesem Fall ist die tatsächliche Zeit die erforderliche Zeit, um eine Modellkonfiguration in einer einzigen Iteration zu erstellen.

Die für Iterationen benötigte Zeit kann je nach Größe des Datasets variieren.

## <a name="cache"></a>cache

`--cache` (Zeichenfolge)

Wenn Sie Caching verwenden, wird das gesamte Trainingsdataset im Speicher geladen.

Bei kleinen und mittleren Datasets kann Caching die Trainingsleistung erheblich verbessern, sodass die Trainingszeit im Vergleich zu einem Training ohne Cache kürzer sein kann.

Bei großen Datasets kann das Laden aller Daten im Speicher jedoch negative Auswirkungen haben, da Sie unter Umständen nicht mehr genügend Speicher zur Verfügung haben. Wenn Sie für das Training mit großen Datasetdateien arbeiten und keinen Cache verwenden, streamt ML.NET Datenblöcke vom Laufwerk, wenn während des Trainings mehr Daten geladen werden müssen.

Sie können folgende Werte angeben:

`on`: Erzwingt, dass während des Trainings der Cache verwendet wird
`off`: Erzwingt, dass während des Trainings der Cache nicht verwendet wird
`auto`: Je nach AutoML-Heuristiken wird der Cache verwendet oder nicht verwendet. In der Regel verwenden kleine/mittlere Datasets den Cache, und große Datasets verwenden keinen Cache, wenn Sie die Option `auto` verwenden.

Wenn Sie den `--cache`-Parameter nicht angeben, wird standardmäßig die Cachekonfiguration `auto` verwendet.

## <a name="name"></a>name

`--name` (Zeichenfolge)

Der Name für das erstellte Ausgabeprojekt oder die erstellte Projektmappe. Wenn kein Name angegeben ist, wird der Name `sample-{mltask}` verwendet.

Die ML.NET-Modelldatei (ZIP-Datei) erhält ebenfalls denselben Namen.

## <a name="output-path"></a>Ausgabepfad

`--output-path | -o` (Zeichenfolge)

Stammspeicherort/-ordner für die generierte Ausgabe. Der Standardwert ist das aktuelle Verzeichnis.

## <a name="verbosity"></a>Ausführlichkeit

`--verbosity | -v` (Zeichenfolge)

Legt den Ausführlichkeitsgrad für die Standardausgabe fest.

Zulässige Werte sind:

- `q[uiet]`
- `m[inimal]` (Standardwert)
- `diag[nostic]` (Protokollierung der Informationsebene)

Standardmäßig sollte das CLI-Tool, wenn es funktioniert, ein Mindestfeedback (`minimal`) anzeigen, z. B. dass es funktioniert und, wenn möglich, wie viel Zeit übrig ist oder wie viel Prozent der Zeit abgeschlossen sind.

## <a name="help"></a>Hilfe

`-h |--help`

Druckt die Hilfe für den Befehl und eine Beschreibung der einzelnen Parameter für den Befehl aus.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Installieren des ML.NET-CLI-Tools](../how-to-guides/install-ml-net-cli.md)
- [Übersicht über die ML.NET-CLI](../automate-training-with-cli.md)
- [Tutorial: Stimmungsanalyse über die ML.NET-Befehlszeilenschnittstelle](../tutorials/sentiment-analysis-cli.md)
- [Telemetrie in der ML.NET-CLI](../resources/ml-net-cli-telemetry.md)
