---
title: Automatisieren des Modelltrainings mit der ML.NET-CLI
description: Erfahren Sie, wie Sie mit dem ML.NET-CLI-Tool automatisch das beste Modell über die Befehlszeile trainieren können.
ms.date: 12/17/2019
ms.custom: how-to
ms.openlocfilehash: ffcdba28fcb73a02f5d4726075588fe3b7789375
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740122"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a>Automatisieren des Modelltrainings mit der ML.NET-CLI

Die ML.NET-CLI automatisiert die Modellgenerierung für .NET-Entwickler.

Um die ML.NET-API selbst zu verwenden (ohne ML.NET AutoML-CLI), müssen Sie einen Trainer (Implementierung eines Machine Learning-Algorithmus für eine bestimmte Aufgabe) und den Satz von Datentransformationen (Featureentwicklung) auswählen, die auf Ihre Daten angewendet werden. Die optimale Pipeline variiert für jedes Dataset, und die Auswahl des optimalen Algorithmus aus allen Optionen erhöht die Komplexität. Darüber hinaus muss für jeden Algorithmus ein Satz an Hyperparametern optimiert werden. Daher kann es manchmal Wochen oder Monate dauern, ein Machine Learning-Modell zu optimieren, um die beste Kombination aus Featureentwicklung, Lernalgorithmen und Hyperparametern zu finden.

Die ML.NET-CLI vereinfacht diesen Prozess mithilfe von automatisiertem Machine Learning (AutoML). 

> [!NOTE]
> Dieses Thema bezieht sich auf die ML.NET-**CLI** und ML.NET **AutoML**, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.

## <a name="what-is-the-mlnet-command-line-interface-cli"></a>Was ist die ML.NET-Befehlszeilenschnittstelle (CLI)?

Die ML.NET-CLI ist ein globales dotnet-Tool. Nach der Installation erhalten Sie eine Machine Learning-Aufgabe und ein Trainingsdataset. Es werden ein ML.NET-Modell und der C#-Code generiert, der für die Verwendung des Modells in der Anwendung ausgeführt wird.

Wie in der folgenden Abbildung dargestellt, ist es einfach, ein qualitativ hochwertiges ML.NET-Modell (serialisierte ZIP-Datei des Modells) plus den Beispiel-C#-Code zu generieren, um dieses Modell auszuführen/zu bewerten. Darüber hinaus wird der C#-Code zum Erstellen/Trainieren dieses Modells generiert, sodass Sie suchen und iterieren können, welcher Algorithmus und welche Einstellungen für dieses generierte „beste Modell“ verwendet wurden.

![Bild](media/automate-training-with-cli/cli-high-level-process.png "AutoML-Engine arbeitet in der ML.NET-CLI")

Sie können diese Objekte aus Ihren eigenen Datasets generieren, ohne selbst zu codieren. Damit steigern Sie also auch Ihre Produktivität, selbst wenn Sie ML.NET bereits kennen.

Derzeit unterstützt die ML.NET-CLI folgende Aufgaben:

- `binary-classification`
- `multiclass-classification`
- `regression`
- Zukünftig: weitere Machine Learning-Aufgaben wie `recommendation`, `ranking`, `anomaly-detection`, `clustering`

Beispiel für die Verwendung:

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![Bild](media/automate-training-with-cli/cli-model-generation.gif)

Sie können sie auf die gleiche Weise auf *Windows PowerShell*, *macOS-/Linux-Bash oder *Windows CMD* ausführen. Die tabellarische automatische Vervollständigung (Parametervorschläge) funktioniert jedoch nicht unter *Windows-CMD*.

## <a name="output-assets-generated"></a>Generierte Ausgabeobjekte

Der CLI-Befehl `auto-train` generiert die folgenden Objekte im Ausgabeordner:

- Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort für die Ausführung von Vorhersagen verwendet werden kann.
- C#-Lösung mit:
  - C#-Code, um das generierte Modell auszuführen/zu bewerten (um mit diesem Modell Vorhersagen in Ihren Endbenutzer-Apps zu treffen).
  - C#-Code mit dem Trainingscode, der zur Erstellung dieses Modells verwendet wird (zu Lernzwecken oder zum erneuten Trainieren des Modells).
- Protokolldatei mit Informationen über alle Iterationen/Sweep-Vorgänge über die verschiedenen ausgewerteten Algorithmen, einschließlich ihrer detaillierten Konfiguration/Pipeline.

Die ersten beiden Objekte können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem generierten ML-Modell Vorhersagen zu treffen.

Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie Ihr Modell erneut trainieren und untersuchen und iterieren können, welchen spezifischen Trainer/Algorithmus und Hyperparameter die CLI und AutoML im Hintergrund ausgewählt haben.

## <a name="understanding-the-quality-of-the-model"></a>Verstehen der Qualität des Modells

Wenn Sie mit dem CLI-Tool ein "bestes Modell" erstellen, werden Qualitätsmetriken angezeigt (wie Genauigkeit und Bestimmtheitsmaß), die für die von Ihnen angestrebte ML-Aufgabe geeignet sind.

Hier fassen wir diese Metriken zusammen, die nach ML-Aufgaben gruppiert sind, damit Sie die Qualität Ihres automatisch generierten „besten Modells“ verstehen können.

### <a name="metrics-for-binary-classification-models"></a>Metriken für binäre Klassifizierungsmodelle

Im Folgenden wird die Metrikliste der binären ML-Klassifizierungsaufgaben für die fünf besten, von der CLI gefundenen Modelle angezeigt:

![Bild](media/automate-training-with-cli/cli-binary-classification-metrics.png)

Die Genauigkeit ist eine beliebte Metrik für Klassifizierungsprobleme. Allerdings ist die Genauigkeit nicht immer die beste Metrik, um das beste Modell auszuwählen, wie in den folgenden Referenzen erläutert. Es gibt Fälle, in denen Sie die Qualität Ihres Modells mit zusätzlichen Metriken bewerten müssen.

Um die Metriken zu untersuchen und zu verstehen, die von der CLI ausgegeben werden, lesen Sie [Auswertungsmetriken für die binäre Klassifizierung](resources/metrics.md#evaluation-metrics-for-binary-classification).

### <a name="metrics-for-multi-class-classification-models"></a>Metriken für Multiklassen-Klassifizierungsmodelle

Im Folgenden wird die Metrikliste der ML-Aufgabe für die Multiklassenklassifizierung für die fünf besten Modelle angezeigt, die von der CLI ermittelt wurden:

![Bild](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

Um die Metriken zu untersuchen und zu verstehen, die von der CLI ausgegeben werden, lesen Sie [Auswertungsmetriken für mehrklassige Klassifizierung](resources/metrics.md#evaluation-metrics-for-multi-class-classification).

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
