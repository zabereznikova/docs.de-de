---
title: Automatisieren des Modelltrainings mit der ML.NET-CLI
description: Erfahren Sie, wie Sie mit dem ML.NET-CLI-Tool automatisch das beste Modell über die Befehlszeile trainieren können.
ms.date: 06/03/2020
ms.custom: how-to, mlnet-tooling
ms.openlocfilehash: d7c6102c2257be1daa613fde0edabce83d04b414
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589660"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a>Automatisieren des Modelltrainings mit der ML.NET-CLI

Die ML.NET-CLI automatisiert die Modellgenerierung für .NET-Entwickler.

Um die ML.NET-API selbst zu verwenden (ohne ML.NET AutoML-CLI), müssen Sie einen Trainer (Implementierung eines Machine Learning-Algorithmus für eine bestimmte Aufgabe) und den Satz von Datentransformationen (Featureentwicklung) auswählen, die auf Ihre Daten angewendet werden. Die optimale Pipeline variiert für jedes Dataset, und die Auswahl des optimalen Algorithmus aus allen Optionen erhöht die Komplexität. Darüber hinaus muss für jeden Algorithmus ein Satz an Hyperparametern optimiert werden. Daher kann es manchmal Wochen oder Monate dauern, ein Machine Learning-Modell zu optimieren, um die beste Kombination aus Featureentwicklung, Lernalgorithmen und Hyperparametern zu finden.

Die ML.NET-CLI vereinfacht diesen Prozess mithilfe von automatisiertem Machine Learning (AutoML).

> [!NOTE]
> Dieses Thema bezieht sich auf die ML.NET-**CLI** und ML.NET **AutoML**, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.

## <a name="what-is-the-mlnet-command-line-interface-cli"></a>Was ist die ML.NET-Befehlszeilenschnittstelle (CLI)?

Die ML.NET-CLI ist ein [.NET Core-Tool](../core/tools/global-tools.md). Nach der Installation erhalten Sie eine Machine Learning-Aufgabe und ein Trainingsdataset. Es werden ein ML.NET-Modell und der C#-Code generiert, der für die Verwendung des Modells in der Anwendung ausgeführt wird.

Wie in der folgenden Abbildung dargestellt, ist es einfach, ein qualitativ hochwertiges ML.NET-Modell (serialisierte ZIP-Datei des Modells) plus den Beispiel-C#-Code zu generieren, um dieses Modell auszuführen/zu bewerten. Darüber hinaus wird der C#-Code zum Erstellen/Trainieren dieses Modells generiert, sodass Sie suchen und iterieren können, welcher Algorithmus und welche Einstellungen für dieses generierte „beste Modell“ verwendet wurden.

![Bild](media/automate-training-with-cli/cli-high-level-process.png "AutoML-Engine arbeitet in der ML.NET-CLI")

Sie können diese Objekte aus Ihren eigenen Datasets generieren, ohne selbst zu codieren. Damit steigern Sie also auch Ihre Produktivität, selbst wenn Sie ML.NET bereits kennen.

Derzeit unterstützt die ML.NET-CLI folgende Aufgaben:

- Klassifizierung (mit zwei oder mehr Klassen)
- Regression
- Empfehlung
- In Zukunft: weitere Machine-Learning-Tasks wie Bildklassifizierung, Zuweisen von Rängen, Anomalieerkennung und Clustering

Verwendungsbeispiel (Klassifizierungsszenario):

```console
mlnet classification --dataset "yelp_labelled.txt" --label-col 1 --has-header false --train-time 10
```

![Bild](media/automate-training-with-cli/mlnet-classification-powershell.gif)

Sie können sie auf die gleiche Weise auf *Windows PowerShell*, *macOS-/Linux-Bash* oder *Windows CMD* ausführen. Die tabellarische automatische Vervollständigung (Parametervorschläge) funktioniert jedoch nicht unter *Windows-CMD*.

## <a name="output-assets-generated"></a>Generierte Ausgabeobjekte

Die ML-Taskbefehle in der CLI generieren die folgenden Objekte im Ausgabeordner:

- Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort für die Ausführung von Vorhersagen verwendet werden kann.
- C#-Lösung mit:
  - C#-Code, um das generierte Modell auszuführen/zu bewerten (um mit diesem Modell Vorhersagen in Ihren Endbenutzer-Apps zu treffen).
  - C#-Code mit dem Trainingscode, der zur Erstellung dieses Modells verwendet wird (zu Lernzwecken oder zum erneuten Trainieren des Modells).
- Protokolldatei mit Informationen über alle Iterationen/Sweep-Vorgänge über die verschiedenen ausgewerteten Algorithmen, einschließlich ihrer detaillierten Konfiguration/Pipeline.

Die ersten beiden Objekte können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem generierten ML-Modell Vorhersagen zu treffen.

Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie Ihr Modell erneut trainieren und untersuchen und iterieren können, welchen spezifischen Trainer/Algorithmus und Hyperparameter die CLI und AutoML im Hintergrund ausgewählt haben.

## <a name="understanding-the-quality-of-the-model"></a>Verstehen der Qualität des Modells

Wenn Sie mit dem CLI-Tool ein „bestes Modell“ erstellen, werden Qualitätsmetriken angezeigt (wie Genauigkeit und Bestimmtheitsmaß), die für die von Ihnen angestrebte ML-Aufgabe geeignet sind.

Hier werden diese Metriken zusammengefasst, die nach ML-Aufgaben gruppiert sind, damit Sie die Qualität Ihres automatisch generierten „besten Modells“ verstehen können.

### <a name="metrics-for-classification-models"></a>Metriken für Klassifizierungsmodelle

Im Folgenden wird die Liste mit Klassifizierungsmetriken für die fünf besten von der CLI gefundenen Modelle angezeigt:

![Bild](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

 Die Genauigkeit ist eine beliebte Metrik für Klassifizierungsprobleme. Allerdings ist die Genauigkeit nicht immer die beste Metrik, um das beste Modell auszuwählen, wie in den folgenden Referenzen erläutert. Es gibt Fälle, in denen Sie die Qualität Ihres Modells mit zusätzlichen Metriken bewerten müssen.

Lesen Sie [Auswerten des ML.NET-Modells mit Metriken](resources/metrics.md#evaluation-metrics-for-multi-class-classification), um die Metriken kennenzulernen und zu verstehen, die von der CLI ausgegeben werden.

### <a name="metrics-for-regression-and-recommendation-models"></a>Metriken für Regressions- und Empfehlungsmodelle

Ein Regressionsmodell eignet sich gut für die Daten, wenn die Unterschiede zwischen den beobachteten Werten und den vorhergesagten Werten des Modells klein und zufällig sind. Die Regression kann mit bestimmten Metriken ausgewertet werden.

Es wird eine ähnliche Metrikliste für die fünf besten, von der CLI gefundenen Modelle angezeigt. In diesem speziellen Fall bezogen auf eine ML-Regressionsaufgabe:

![Bild](media/automate-training-with-cli/cli-regression-metrics.png)

Um die Metriken zu untersuchen und zu verstehen, die von der CLI ausgegeben werden, lesen Sie [Auswertungsmetriken für die Regression](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Installieren des ML.NET-CLI-Tools](how-to-guides/install-ml-net-cli.md)
- [Tutorial: Stimmungsanalyse mit der ML.NET-CLI](tutorials/sentiment-analysis-cli.md)
- [Befehlsreferenz für die ML.NET-CLI](reference/ml-net-cli-reference.md)
- [Telemetrie in der ML.NET-CLI](resources/ml-net-cli-telemetry.md)
