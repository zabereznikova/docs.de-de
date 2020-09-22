---
title: Azure-Trainingsressourcen für den Modellgenerator
description: Ein Leitfaden zu Ressourcen für Azure Machine Learning
ms.topic: reference
ms.date: 06/01/2020
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 1321967cacdd373acc19923f992d30c5453ea869
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556218"
---
# <a name="model-builder-azure-training-resources"></a>Azure-Trainingsressourcen für den Modellgenerator

Im nachfolgenden Leitfaden werden die Ressourcen erläutert, die zum Trainieren von Modellen in Azure mit dem Modellgenerator verwendet werden.

## <a name="what-is-an-azure-machine-learning-experiment"></a>Was ist ein Azure Machine Learning-Experiment?

Ein Azure Machine Learning-Experiment ist eine Ressource, die vor der Ausführung des Modellgeneratortrainings in Azure erstellt werden muss.

Das Experiment kapselt die Konfiguration und die Ergebnisse für eine oder mehrere Ausführungen des Machine Learning-Trainings. Experimente sind einem bestimmten Arbeitsbereich zugeordnet. Wenn ein Experiment zum ersten Mal erstellt wird, wird dessen Name im Arbeitsbereich registriert. Alle darauffolgenden Ausführungen werden – sofern derselbe Experimentname verwendet wird – als Teil desselben Experiments protokolliert. Andernfalls wird ein neues Experiment erstellt.

## <a name="what-is-an-azure-machine-learning-workspace"></a>Was ist ein Azure Machine Learning-Arbeitsbereich?

Ein Arbeitsbereich ist eine Azure Machine Learning-Ressource, die einen zentralen Ort für alle Azure Machine Learning-Ressourcen sowie als Teil der Trainingsausführung erstellte Artefakte bietet.

Folgendes ist erforderlich, um einen Azure Machine Learning-Arbeitsbereich zu erstellen:

- Name: Ein Name für Ihren Arbeitsbereich. Dieser darf zwischen 3 und 33 Zeichen lang sein. Namen dürfen nur alphanumerische Zeichen und Bindestriche enthalten.
- Region: Der geografische Standort des Rechenzentrums, in dem Ihr Arbeitsbereich und Ihre Ressourcen bereitgestellt werden. Es wird empfohlen, einen Standort in Ihrer Nähe und nahe bei Ihren Kunden zu wählen.
- Ressourcengruppe: Ein Container, der verwandte Ressourcen für eine Azure-Lösung enthält

## <a name="what-is-an-azure-machine-learning-compute"></a>Was ist eine Azure Machine Learning-Compute-Instanz?

Eine Azure Machine Learning-Compute-Instanz ist eine cloudbasierte Linux-VM für das Training.

Folgendes ist erforderlich, um einen Azure Machine Learning-Arbeitsbereich zu erstellen:

- Name: Ein Name für Ihren Arbeitsbereich. Dieser darf zwischen 2 und 16 Zeichen lang sein. Namen dürfen nur alphanumerische Zeichen und Bindestriche enthalten.
- Computegröße

    Der Modellgenerator kann einen der folgenden GPU-optimierten Computetypen verwenden:

    | Größe | vCPU | Memory: GiB | Temporärer Speicher (SSD): GiB | GPU | GPU-Arbeitsspeicher: GiB | Max. Anzahl Datenträger | Maximale Anzahl NICs |
    |---|---|---|---|---|---|---|---|
    | Standard_NC12   | 12 | 112 | 680  | 2 | 24 | 48 | 2 |
    | Standard_NC24   | 24 | 224 | 1440 | 4 | 48 | 64 | 4 |

    Weitere Details zu GPU-optimierten Computetypen finden Sie in der [Linux-VM-Dokumentation zur NC-Serie](/azure/virtual-machines/nc-series?bc=%252fazure%252fvirtual-machines%252flinux%252fbreadcrumb%252ftoc.json&toc=%252fazure%252fvirtual-machines%252flinux%252ftoc.json).
- Computepriorität

  - Niedrige Priorität: Geeignet für Aufgaben mit kürzerer Ausführungszeit. Kann durch Unterbrechungen und fehlende Verfügbarkeit beeinträchtigt werden. Kostet in der Regel weniger, weil überschüssige Kapazitäten in Azure genutzt werden.
  - Dediziert: Geeignet für Aufgaben beliebiger Dauer, aber besonders für Aufträge mit langer Ausführungszeit. Nicht beeinträchtigt durch Unterbrechungen oder fehlende Verfügbarkeit. Kostet in der Regel mehr, weil eine dedizierte Gruppe von Computeressourcen in Azure für Ihre Aufgaben reserviert wird.

## <a name="training"></a>Aus- und Weiterbildung

Das Training in Azure ist nur für das Bildklassifizierungsszenario für den Modellgenerator verfügbar. Der zum Trainieren dieses Modells verwendete Algorithmus ist ein Deep Neural Network und basiert auf der ResNet50-Architektur. Der Trainingsprozess nimmt einige Zeit in Anspruch. Diese Zeitspanne kann je nach Computegröße und Datenmenge variieren. Sie können den Status Ihrer Ausführung verfolgen, indem Sie den Link „Monitor current run in Azure portal“ (Aktuelle Ausführung im Azure-Portal verfolgen) in Visual Studio auswählen.

## <a name="results"></a>Ergebnisse

Sobald das Training abgeschlossen ist, werden Ihrer Projektmappe zwei Projekte mit den folgenden Suffixen hinzugefügt:

- *ConsoleApp*: Eine .NET Core-Konsolenanwendung für C#, die den Startercode zum Erstellen der Vorhersagepipeline und zum Durchführen von Vorhersagen bereitstellt.
- *Model*: Eine .NET Standard-Anwendung für C#, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten sowie die folgenden Objekte enthält:

  - bestModel.onnx: Eine serialisierte Modellversion im ONNX-Format (Open Neural Network Exchange). ONNX ist ein Open-Source-Format für KI-Modelle, das Interoperabilität zwischen Frameworks wie ML.NET, PyTorch und TensorFlow unterstützt.
  - bestModelMap.json: Eine Liste der Kategorien, die beim Erstellen von Vorhersagen verwendet werden, um die Modellausgabe einer Textkategorie zuzuordnen.
  - MLModel.zip: Eine serialisierte Version der ML.NET-Vorhersagepipeline, die die serialisierte Version des Modells *bestModel.onnx* verwendet, um Vorhersagen zu erstellen und mithilfe der `bestModelMap.json`-Datei Ausgaben zuzuordnen.

## <a name="use-the-machine-learning-model"></a>Verwenden des Machine Learning-Modells

Die Klassen `ModelInput` und `ModelOutput` im Projekt *Model* definieren das Schema der erwarteten Eingabe bzw. Ausgabe des Modells.

In einem Imageklassifizierungsszenario enthält die `ModelInput`-Klasse zwei Spalten:

- `ImageSource`: Der Zeichenfolgenpfad des Bildspeicherorts
- `Label`: Die tatsächliche Kategorie, zu der das Bild gehört. `Label` wird nur als Eingabe beim Training verwendet und muss nicht bereitgestellt werden, wenn Vorhersagen getroffen werden.

`ModelOutput` enthält zwei Spalten:

- `Prediction`: Die vorhergesagte Bildkategorie
- `Score`: Die Liste der Wahrscheinlichkeiten für alle Kategorien (das wahrscheinlichste Szenario gehört zur `Prediction`)

## <a name="troubleshooting"></a>Problembehandlung

### <a name="cannot-create-compute"></a>Computeinstanz kann nicht erstellt werden

Wenn ein Fehler während der Azure Machine Learning-Computeerstellung auftritt, ist es möglich, dass die Computeressource noch immer in einem fehlerhaften Zustand vorhanden ist. Wenn Sie versuchen, die Computeressource mit dem gleichen Namen neu zu erstellen, schlägt der Vorgang fehl. Sie haben folgende Möglichkeiten, um diesen Fehler zu beheben:

- Erstellen Sie den neuen Computeinstanz mit einem anderen Namen.
- Wechseln Sie zum Azure-Portal, und entfernen Sie die ursprüngliche Computeressource.
