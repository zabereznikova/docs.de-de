---
title: 'Tutorial: Klassifizieren von Integritätsverstößen mit dem Modell-Generator'
description: In diesem Tutorial wird veranschaulicht, wie Sie mithilfe des ML.NET-Modell-Generator ein Multiklassenklassifizierungsmodell zum Klassifizieren des Schweregrads von Integritätsverletzungen in Restaurants in San Francisco erstellen.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: e94313277a025d482105a6d78b6608d4df442c43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185834"
---
# <a name="tutorial-classify-the-severity-of-restaurant-health-violations-with-model-builder"></a>Tutorial: Klassifizieren des Schweregrads von Integritätsverletzungen in Restaurants mit dem Modell-Generator

Informieren Sie sich, wie Sie mithilfe des Modell-Generators ein Multiklassenklassifizierungsmodell zum Kategorisieren der Risikostufe von Verstößen in Restaurants erstellen, die bei Integritätsprüfungen festgestellt wurden.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> - Vorbereiten und Verstehen der Daten
> - Auswählen eines Szenarios
> - Laden von Daten aus einer Datenbank
> - Trainieren des Modells
> - Evaluieren des Modells
> - Verwenden des Modells für Vorhersagen

> [!NOTE]
> Der Modell-Generator befindet sich derzeit in der Vorschauphase.

## <a name="prerequisites"></a>Voraussetzungen

Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie in der [Installationsanleitung für den Modell-Generator](../how-to-guides/install-model-builder.md).

## <a name="model-builder-multiclass-classification-overview"></a>Übersicht über die Multiklassenklassifizierung des Modell-Generators

In diesem Beispiel wird eine C# .NET Core-Konsolenanwendung erstellt, die mithilfe eines mit dem Modell-Generator erstellten Machine Learning-Modells das Risiko von Integritätsverstößen kategorisiert. Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations).

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **C# .NET Core-Konsolenanwendung** mit dem Namen „RestaurantViolations“. Stellen Sie sicher, dass die Option zum **Platzieren von Projektmappe und Projekt im selben Verzeichnis** **deaktiviert** (VS 2019) oder die Option **Verzeichnis für Projektmappe erstellen** **aktiviert** ist (VS 2017).

## <a name="prepare-and-understand-the-data"></a>Vorbereiten und Verstehen der Daten

> Das Dataset, das zum Trainieren und Auswerten des Machine Learning-Modells verwendet wird, stammt ursprünglich vom [San Francisco Department of Public Health für Integritätsbewertungen von Restaurants](https://www.sfdph.org/dph/EH/Food/score/default.asp). Aus Gründen der Benutzerfreundlichkeit wurde das Dataset so komprimiert, dass nur die Spalten enthalten sind, die zum Trainieren des Modells und zum Treffen von Vorhersagen relevant sind. Weitere Informationen zum [Dataset](https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i?row_index=0) finden Sie auf der folgenden Website.

[Laden Sie das Dataset „Restaurant Safety Scores“](https://github.com/luisquintanilla/machinelearning-samples/raw/AB1608219/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantScores.zip) herunter, und entpacken Sie es.

Jede Zeile im Dataset enthält Informationen zu Verstößen, die im Rahmen einer Untersuchung des Gesundheitsamts festgestellt wurden, sowie eine Risikobewertung der aus diesen Verstößen resultierenden Gefahren für die öffentliche Gesundheit und Sicherheit.

| InspectionType | ViolationDescription | RiskCategory |
| --- | --- | --- |
| Routinekontrolle (nicht angekündigt) | Unzureichend gesäuberte oder desinfizierte Oberflächen | Mittleres Risiko |
| Neuer Besitzer | Hohes Risiko durch Schädlingsbefall | Hohes Risiko |
| Routinekontrolle (nicht angekündigt) | Klamotten nicht bzw. nicht ordnungsgemäß gelagert und gewaschen | Geringes Risiko |

- **InspectionType:** Dies entspricht der Art der Überprüfung. Dabei kann es sich um eine erstmalige Überprüfung eines neuen Ladens, eine Routineüberprüfung, eine Überprüfung infolge einer Beschwerde usw. handeln.
- **ViolationDescription:** Dies ist eine Beschreibung des während der Überprüfung festgestellten Verstoßes.
- **RiskCategory:** Dies beschreibt den Schweregrad des Verstoßes, den dieser für die öffentliche Gesundheit und Sicherheit darstellt.

`label` ist die Spalte, die vorhergesagt werden soll. Beim Ausführen einer Klassifizierungsaufgabe ist es das Ziel, eine Kategorie zuzuweisen (Text oder numerisch). In diesem Klassifizierungsszenario entspricht der Schweregrad des Verstoßes den Werten „geringes Risiko“, „mittleres Risiko“ oder „hohes Risiko“. Daher ist **RiskCategory** die Bezeichnung. Die `features` sind die Eingaben, die Sie dem Modell zum Vorhersagen von `label` bereitstellen. In diesem Fall werden **InspectionType** und **ViolationDescription** als Features oder Eingaben verwendet, um **RiskCategory** vorherzusagen.

## <a name="choose-a-scenario"></a>Auswählen eines Szenarios

![Modell-Generator-Assistent in Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Wählen Sie aus der vom Modell-Generator bereitgestellten Liste der verfügbaren Machine Learning-Szenarios ein Szenario aus, um Ihr Modell zu trainieren. In diesem Fall ist das Szenario *Issue Classification* (Klassifizierung von Issues).

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *RestaurantViolations*, und wählen Sie **Hinzufügen** > **Machine Learning** aus.
1. In diesem Fall ist das Szenario multiclass classification (Multiklassenklassifizierung). Wählen Sie im Schritt *Szenario* des Modell-Generators das **Issue Classification**-Szenario (Klassifizierung von Issues) aus.

## <a name="load-the-data"></a>Laden der Daten

Der Modell-Generator akzeptiert Daten aus einer SQL Server-Datenbank oder aus einer lokalen Datei im `csv`- oder `tsv`-Format.

1. Wählen Sie im Schritt „Daten“ des Modell-Generator-Tools **SQL Server** aus der Dropdownliste „Datenquelle“ aus.
1. Klicken Sie auf die Schaltfläche neben dem Textfeld **Connect to SQL Server database** (Verbindung mit SQL Server-Datenbank herstellen).
    1. Klicken Sie im Dialogfeld **Choose Data** (Daten auswählen) auf **Microsoft SQL Server-Datenbankdatei**.
    1. Deaktivieren Sie das Kontrollkästchen **Immer diese Auswahl verwenden**, und klicken Sie auf **Weiter**.
    1. Klicken Sie im Dialogfeld **Verbindungseigenschaften** auf **Durchsuchen**, und klicken Sie auf die heruntergeladene Datei *RestaurantScores.mdf*.
    1. Klicken Sie auf **OK**.
1. Klicken Sie in der Dropdownliste **Tabellenname** auf **Violations** (Verstöße).
1. Klicken Sie in der Dropdownliste **Column to Predict (Label)** (Vorherzusagende Spalte (Bezeichnung)) die Option **RiskCategory** aus.
1. Lassen Sie die in der Dropdownliste **Input Columns (Features)** (Eingabespalten (Features)) aktivierte Standardspaltenauswahl **InspectionType** und **ViolationDescription** unverändert.
1. Wählen Sie den Link **Trainieren** aus, um zum nächsten Schritt im Modell-Generator zu gelangen.

## <a name="train-the-model"></a>Trainieren des Modells

Die in diesem Tutorial zum Trainieren des Klassifizierungsmodells für Issues verwendete Machine Learning-Aufgabe ist eine Multiklassenklassifizierung. Während des Modelltrainings trainiert der Modell-Generator einzelne Modelle mit verschiedenen Algorithmen und Einstellungen für Multiklassenklassifizierungen, um das leistungsfähigste Modell für Ihr Dataset zu finden.

Die Zeit, die für das Trainieren des Modells benötigt wird, ist proportional zur Datenmenge. Der Modell-Generator legt automatisch einen Standardwert für **Time to train (seconds)** (Trainingszeit (Sekunden)) basierend auf der Größe der Datenquelle fest.

1. Obwohl der Modell-Generator den Wert von **Trainingszeit (Sekunden)** auf 10 Sekunden festlegt, erhöhen Sie den Wert auf 30 Sekunden. Ein längeres Training ermöglicht es dem Modell-Generator, eine größere Anzahl von Algorithmen und Kombinationen von Parametern auf der Suche nach dem besten Modell zu untersuchen.
1. Wählen Sie **Training starten** aus.

    Während des gesamten Trainingsprozesses werden die Fortschrittsdaten im Abschnitt `Progress` des Schritts „Trainieren“ angezeigt.

    - **Status** zeigt den Abschlussstatus des Trainingsprozesses an.
    - **Best accuracy**  (Beste Genauigkeit) zeigt die Genauigkeit des leistungsfähigsten Modells an, das bisher vom Modell-Generator gefunden wurde. Eine höhere Genauigkeit bedeutet, dass die Vorhersage des Modells anhand der Testdaten präziser ist.
    - **Best algorithm**  (Bester Algorithmus) zeigt den Namen des leistungsfähigsten Algorithmus an, der bisher vom Modell-Generator gefunden wurde.
    - **Last algorithm**  (Letzter Algorithmus) zeigt den Namen des Algorithmus an, der zuletzt vom Modell-Generator zum Trainieren des Modells verwendet wurde.

1. Wählen Sie nach Abschluss des Trainings den Link **Evaluieren** aus, um mit dem nächsten Schritt fortzufahren.

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Das Ergebnis des Schritts „Trainieren“ ist das Modell mit der besten Leistung. Im Schritt „Evaluieren“ des Modell-Generators enthält der Ausgabebereich den Algorithmus, der vom leistungsfähigsten Modell im Eintrag **Best Model** (Bestes Modell) verwendet wird, sowie Metriken in **Best Model Accuracy** (Beste Modellgenauigkeit). Zusätzlich werden eine Zusammenfassungstabelle mit bis zu fünf untersuchten Modellen und deren Metriken angezeigt.

Wenn Sie mit Ihren Genauigkeitsmetriken nicht zufrieden sind, gibt es einige einfache Möglichkeiten, die Modellgenauigkeit zu verbessern, indem Sie beispielsweise die Zeit für das Training des Modells erhöhen oder mehr Daten verwenden. Klicken Sie andernfalls auf den Link **Code**, um zum letzten Schritt im Modell-Generator zu gelangen.

## <a name="add-the-code-to-make-predictions"></a>Hinzufügen des Codes für Vorhersagen

Als Ergebnis des Trainingsprozesses werden zwei Projekte erstellt.

- RestaurantViolationsML.ConsoleApp: Dies ist eine .NET Core-Konsolenanwendung, die den Modelltrainings- und Beispielverbrauchscode enthält.
- RestaurantViolationsML.Model: Dies ist eine .NET Standard-Klassenbibliothek, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten, die gespeicherte Version des leistungsfähigsten Modells während des Trainings sowie eine Hilfsklasse namens `ConsumeModel` definieren, um Vorhersagen zu treffen.

1. Wählen Sie im Schritt „Code“ des Modell-Generators die Option **Projekte hinzufügen** aus, um der Projektmappe die automatisch generierten Projekte hinzuzufügen.
1. Öffnen Sie die Datei *Program.cs* im Projekt *RestaurantViolations*.
1. Fügen Sie die folgende using-Anweisung hinzu, um auf das Projekt *RestaurantViolationsML.Model* zu verweisen:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L2)]

1. Um eine Vorhersage für neue Daten mithilfe des Modells zu erstellen, erstellen Sie eine neue Instanz der Klasse `ModelInput` innerhalb der `Main`-Methode Ihrer Anwendung. Beachten Sie, dass die Risikokategorie nicht Teil der Eingabe ist. Das liegt daran, dass das Modell die Vorhersage dafür generiert.

    [!code-csharp [TestData](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L11-L15)]

1. Verwenden Sie die `Predict`-Methode aus der `ConsumeModel`-Klasse. Die `Predict`-Methode lädt das trainierte Modell, erstellt eine [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) für das Modell und verwendet sie, um Vorhersagen für neue Daten zu generieren.

    [!code-csharp [Prediction](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L17-L24)]

1. Führen Sie die Anwendung aus.

    Die vom Programm generierte Ausgabe sollte wie der folgende Ausschnitt aussehen:

    ```bash
    Inspection Type: Complaint
    Violation Description: Inadequate sewage or wastewater disposal
    Risk Category: Moderate Risk
    ```

Wenn Sie zu einem späteren Zeitpunkt innerhalb einer anderen Projektmappe auf die generierten Projekte verweisen müssen, finden Sie diese im Verzeichnis `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

Herzlichen Glückwunsch! Sie haben mithilfe des Modell-Generators erfolgreich ein Machine Learning-Modell zum Kategorisieren des Risikos von Integritätsverstößen erstellt. Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zu den in diesem Tutorial erwähnten Themen finden Sie in den folgenden Ressourcen:

- [Szenarien für den Modellgenerator](../automate-training-with-model-builder.md#scenarios)
- [Multiklassenklassifizierung](../resources/glossary.md#multiclass-classification)
- [Modellmetriken zur Multiklassenklassifizierung](../resources/metrics.md#evaluation-metrics-for-multi-class-classification)
