---
title: Laden von Trainingsdaten für den Modell-Generator
description: Informieren Sie sich, wie Sie Trainingsdaten aus einer SQL Server-Datenbank oder einer Datei zur Verwendung in eines der Modell-Generator-Szenarios für ML.NET laden.
ms.date: 10/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: cc93b3f77284ed283a8d7cbd52b8cd02b4fd9066
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977056"
---
# <a name="load-training-data-into-model-builder"></a>Laden von Trainingsdaten in den Modell-Generator

Informieren Sie sich, wie Sie Ihre Trainingsdatasets aus einer Datei oder einer SQL Server-Datenbank zur Verwendung in eines der Modell-Generator-Szenarios für ML.NET laden. Modell-Generator-Szenarios können SQL Server-Datenbanken, Imagedateien und CSV- oder TSV-Dateiformate als Trainingsdaten verwenden.

## <a name="training-dataset-limitations-in-model-builder"></a>Trainingsdataseteinschränkungen im Modell-Generator

Der Modell-Generator schränkt die Menge und den Typ der Daten ein, die Sie für Trainingsmodelle verwenden können:

- SQL Server-Daten: 100.000 Zeilen
- CSV- und TSV-Dateien: kein Größenlimit
- Images: nur PNG und JPG

## <a name="model-builder-scenarios"></a>Modell-Generator-Szenarios

Der Modell-Generator unterstützt Sie beim Erstellen von Modellen für die folgenden Machine Learning-Szenarios:

- Standpunktanalyse (binäre Klassifizierung): Klassifizieren von Textdaten in zwei Kategorien
- Klassifizierung von Issues (Multiklassenklassifizierung): Klassifizieren von Textdaten in drei oder mehr Kategorien
- Preisvorhersage (Regression): Vorhersagen eines numerischen Werts
- Bildklassifizierung (Deep Learning): Kategorisieren von Bildern basierend auf Eigenschaften
- Benutzerdefiniertes Szenario: Erstellen benutzerdefinierter Szenarios aus Ihren Daten mithilfe von Regression, Klassifizierung und anderen Aufgaben

In diesem Artikel werden Klassifizierungs- und Regressionsszenarios mit Text- oder numerischen Daten sowie Bildklassifizierungsszenarios behandelt.

## <a name="load-text-or-numeric-data-from-a-file"></a>Laden von Text- oder numerischen Daten aus einer Datei

Sie können Text- oder numerische Daten aus einer Datei in den Modell-Generator laden. Dieser akzeptiert durch Trennzeichen getrennte (CSV) und durch Tabstopps getrennte (TSV) Dateiformate.

1. Wählen Sie im Schritt „Daten“ des Modell-Generators die Option **Datei** aus der Dropdownliste „Datenquelle“ aus.
2. Klicken Sie auf die Schaltfläche neben dem Textfeld **Datei auswählen**, und verwenden Sie den Datei-Explorer, um die Datendatei zu suchen und auszuwählen.
3. Wählen Sie in der Dropdownliste **Column to Predict (Label)** (Vorherzusagende Spalte (Bezeichnung)) eine Kategorie aus.
4. Vergewissern Sie sich, dass in der Dropdownliste **Input Columns (Features)** (Eingabespalten (Features)) die Datenspalten, die Sie einschließen möchten, überprüft werden.

Sie haben die Einrichtung der Datenquellendatei für den Modell-Generator abgeschlossen. Wählen Sie den Link **Trainieren** aus, um zum nächsten Schritt im Modell-Generator zu gelangen.

## <a name="load-data-from-a-sql-server-database"></a>Laden von Daten aus einer SQL Server-Datenbank

Der Modell-Generator unterstützt das Laden von Daten aus lokalen und SQL Server-Remotedatenbanken.

So laden Sie Daten aus einer SQL Server-Datenbank in den Modell-Generator:

1. Wählen Sie im Schritt „Daten“ des Modell-Generators die Option **SQL Server** aus der Dropdownliste „Datenquelle“ aus.
1. Klicken Sie auf die Schaltfläche neben dem Textfeld **Connect to SQL Server database** (Verbindung mit SQL Server-Datenbank herstellen).
    1. Klicken Sie im Dialogfeld **Choose Data** (Daten auswählen) auf **Microsoft SQL Server-Datenbankdatei**.
    1. Deaktivieren Sie das Kontrollkästchen **Immer diese Auswahl verwenden**, und klicken Sie auf **Weiter**.
    1. Klicken Sie im Dialogfeld **Verbindungseigenschaften** auf **Durchsuchen**, und klicken Sie auf die heruntergeladene MDF-Datei.
    1. Wählen Sie **OK** aus.
1. Wählen Sie in der Dropdownliste **Tabellenname** den Datasetnamen aus.
1. Wählen Sie in der Dropdownliste **Column to Predict (Label)** (Vorherzusagende Spalte (Bezeichnung)) die Datenkategorie aus, für die Sie eine Vorhersage erstellen möchten.
1. Vergewissern Sie sich, dass in der Dropdownliste **Input Columns (Features)** (Eingabespalten (Features)) die Spalten, die Sie einschließen möchten, überprüft werden.

Sie haben die Einrichtung der Datenquellendatei für den Modell-Generator abgeschlossen. Wählen Sie den Link **Trainieren** aus, um zum nächsten Schritt im Modell-Generator zu gelangen.

## <a name="set-up-image-data-files"></a>Einrichten von Bilddatendateien

Der Modell-Generator erwartet, dass Bilddaten JPG- oder PNG-Dateien sind, die in Ordnern organisiert sind, die den Kategorien der Klassifizierung entsprechen.

Geben Sie den Pfad zu einem einzelnen Verzeichnis der obersten Ebene an, um Bilder in den Modell-Generator zu laden:

- Dieses Verzeichnis der obersten Ebene enthält einen Unterordner für jede der vorherzusagenden Kategorien.
- Jeder Unterordner enthält die Bilddateien, die zur Kategorie gehören.

In der unten dargestellten Ordnerstruktur ist *flower_photos* das Verzeichnis der obersten Ebene. Es gibt fünf Unterverzeichnisse, die den Kategorien entsprechen, die Sie vorhersagen möchten: daisy, dandelion, roses, sunflowers und tulips. Jedes dieser Unterverzeichnisse enthält Bilder, die der jeweiligen Kategorie angehören.

```text
\---flower_photos
    +---daisy
    |       100080576_f52e8ee070_n.jpg
    |       102841525_bd6628ae3c.jpg
    |       105806915_a9c13e2106_n.jpg
    |
    +---dandelion
    |       10443973_aeb97513fc_m.jpg
    |       10683189_bd6e371b97.jpg
    |       10919961_0af657c4e8.jpg
    |
    +---roses
    |       102501987_3cdb8e5394_n.jpg
    |       110472418_87b6a3aa98_m.jpg
    |       118974357_0faa23cce9_n.jpg
    |
    +---sunflowers
    |       127192624_afa3d9cb84.jpg
    |       145303599_2627e23815_n.jpg
    |       147804446_ef9244c8ce_m.jpg
    |
    \---tulips
            100930342_92e8746431_n.jpg
            107693873_86021ac4ea_n.jpg
            10791227_7168491604.jpg
```

## <a name="next-steps"></a>Nächste Schritte

Führen Sie die Schritte dieses Tutorials aus, um mit dem Modell-Generator Machine Learning-Apps zu erstellen:

- [Vorhersagen von Preisen per Regression](../tutorials/predict-prices-with-model-builder.md)
- [Analysieren des Standpunkts in einer Webanwendung mithilfe der binären Klassifizierung](../tutorials/sentiment-analysis-model-builder.md )

Wenn Sie ein Modell mithilfe von Code trainieren, können Sie sich [hier informieren, wie Sie Daten mithilfe der ML.NET-API laden](load-data-ml-net.md).
