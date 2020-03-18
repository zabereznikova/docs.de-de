---
title: 'Vorgehensweise: Verbessern der Modellgenauigkeit'
description: Erfahren Sie, wie Sie die Modellgenauigkeit verbessern.
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc
ms.openlocfilehash: 8f3b283de378a37bfe429688207ea9fb52f9ca7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75739583"
---
# <a name="improve-mlnet-model-accuracy"></a>Verbessern der ML.NET-Modellgenauigkeit

Erfahren Sie, wie die Genauigkeit Ihres Modells verbessern.

## <a name="reframe-the-problem"></a>Definieren des Problems

Manchmal hat die Verbesserung eines Modells nichts mit den Daten oder Techniken zu tun, die zum Trainieren des Modells verwendet werden. Stattdessen wird vielleicht nur die falsche Frage gestellt. Betrachten Sie das Problem aus verschiedenen Blickwinkeln und nutzen Sie die Daten, um latente Indikatoren und versteckte Beziehungen zu extrahieren, um die Frage zu verfeinern.

## <a name="provide-more-data-samples"></a>Bereitstellen weiterer Datenbeispiele

Wie bei Menschen steigt auch die Wahrscheinlichkeit für eine bessere Leistung bei Algorithmen, je mehr diese trainiert werden. Eine Möglichkeit, die Modellleistung zu verbessern, besteht darin, den Algorithmen mehr Trainingsdatenbeispiele zur Verfügung zu stellen. Je größer die Datenmenge ist, von der ein Algorithmus lernt, desto mehr Fälle kann er richtig identifizieren.

## <a name="add-context-to-the-data"></a>Hinzufügen von Kontext zu den Daten

Ein einzelner Datenpunkt kann schwer zu interpretieren sein. Der Aufbau von Kontext um die Datenpunkte herum hilft Algorithmen und Experten, bessere Entscheidungen zu treffen. Zum Beispiel ist die Tatsache, dass ein Haus über drei Schlafzimmer verfügt, nicht allein ein guter Indikator auf den Preis. Wenn Sie jedoch den Kontext hinzufügen und jetzt wissen, dass es sich in einem Vorort außerhalb eines großen Ballungsgebietes befindet, in dem das Durchschnittsalter 38 Jahre und das durchschnittliche Haushaltseinkommen 80.000 Dollar beträgt und die Schulen im oberen 20. Perzentil liegen, dann hat der Algorithmus mehr Informationen, auf denen seine Entscheidungen aufbauen können. Diese Kontexte können als Eingabe für das Machine Learning-Modell als Features hinzugefügt werden.

## <a name="use-meaningful-data-and-features"></a>Verwenden von aussagekräftige Daten und Features

Mehr Datenbeispiele und Features können zwar dazu beitragen, die Genauigkeit des Modells zu verbessern, aber sie können auch Rauschen verursachen, da nicht alle Daten und Features sinnvoll sind. Daher ist es wichtig zu verstehen, welche Features die Entscheidungen des Algorithmus am stärksten beeinflussen. Die Verwendung von Techniken wie Permutation Feature Importance (PFI) kann helfen, diese wichtigen Features zu identifizieren. Und damit können Sie nicht nur das Modell erklären, sondern auch die Ausgabe als Methode zur Auswahl von Features verwenden, um die Anzahl der verrauschten Features zu reduzieren, die in den Trainingsprozess eingehen.

Weitere Informationen zur Verwendung von PFI finden Sie unter [Erläutern von Modellvorhersagen mit PFI (Permutation Feature Importance, Permutationsmerkmalsgewichtung)](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md).

## <a name="cross-validation"></a>Kreuzvalidierung

Die Kreuzvalidierung ist eine Trainings- und Modellevaluierungstechnik, die die Daten in mehrere Partitionen unterteilt und mehrere Algorithmen auf diesen Partitionen trainiert. Dieses Verfahren verbessert die Stabilität des Modells, indem Daten aus dem Trainingsprozess bereitgehalten werden. Abgesehen vom Verbessern der Leistung bei nicht angezeigten Beobachtungen kann es in Umgebungen mit Dateneinschränkungen ein effektives Tool sein, um Modelle mit einem kleineren Dataset zu trainieren.

Besuchen Sie den folgenden Link, um zu erfahren, wie Sie die [Kreuzvalidierung in ML.NET verwenden](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md).

## <a name="hyperparameter-tuning"></a>Hyperparameteroptimierung

Das Trainieren von Machine Learning-Modellen ist eine iterativer Erkundungsvorgang. Was ist zum Beispiel die optimale Anzahl von Clustern beim Training eines Modells mit dem K-Means-Algorithmus?? Die Antwort hängt von vielen Faktoren ab, wie z.B. der Struktur der Daten. Um diese Zahl zu bestimmen, müssten Sie mit verschiedenen Werten für k experimentieren und dann die Leistung bewerten, um festzustellen, welcher Wert der beste ist. Die Vorgehensweise, diese Parameter zu optimieren, um ein optimales Modell zu finden, wird als Hyperparameteroptimierung bezeichnet.

## <a name="choose-a-different-algorithm"></a>Auswählen eines anderen Algorithmus

Machine Learning-Aufgaben wie Regressions- und Klassifizierungsmodelle enthalten verschiedene Algorithmusimplementierungen. Es kann sein, dass das Problem, das Sie zu lösen versuchen, und die Struktur Ihrer Daten nicht gut zum aktuellen Algorithmus passt. In diesem Fall sollten Sie einen anderen Algorithmus für Ihre Aufgabe verwenden, um zu sehen, ob dieser mit Ihren Daten besser lernt.

Der folgende Link bietet weitere [Anleitungen zur Auswahl des Algorithmus](../how-to-choose-an-ml-net-algorithm.md).
