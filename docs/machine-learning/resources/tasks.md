---
title: Machine Learning-Aufgaben
description: Untersuchen Sie die anderen in ML.NET unterstützten Machine Learning-Aufgaben.
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 875006a9cddb87b5f9436b78773420858fd842dd
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207725"
---
# <a name="machine-learning-tasks"></a>Machine Learning-Aufgaben

Wenn Sie ein Machine Learning-Modell erstellen, müssen Sie zuerst definieren, was Sie mit Ihren Daten erreichen möchten. Danach können Sie die richtige Machine Learning-Aufgabe für Ihren Zweck auswählen. In der folgenden Liste werden die verschiedenen Machine Learning-Aufgaben beschrieben, unter denen Sie auswählen können, und einige häufige Anwendungsfälle. 

> [!NOTE]
> ML.NET ist derzeit als Vorschauversion verfügbar. Nicht alle Machine Learning-Aufgaben werden derzeit unterstützt. Um eine Anforderung für eine bestimmte Aufgabe zu übermitteln, öffnen Sie einen Fall im [dotnet/machinelearning-Repository](https://github.com/dotnet/machinelearning/issues).

> [!NOTE]
> Derzeit unterstützt ML.NET keine Machine Learning-Aufgaben mit Bildern. Die Unterstützung ist für zukünftige Releases geplant. 

## <a name="binary-classification"></a>Binäre Klassifizierung

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um vorherzusagen, zu welcher von zwei Klassen (Kategorien) eine Dateninstanz gehört. Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele, wo jede Bezeichnung entweder die Ganzzahl 0 oder 1 ist. Die Ausgabe eines binären Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen. Zu den Beispielen binärer Klassifizierungsszenarien zählen:

* [Verstehen des Standpunkts in Twitter-Kommentaren](../tutorials/sentiment-analysis.md) als „positiv“ oder „negativ“.
* Diagnostizieren, ob bei einem Patienten eine bestimmte Krankheit vorliegt oder nicht.
* Treffen einer Entscheidung, um eine E-Mail-Nachricht als „Spam“ zu markieren oder nicht.

Weitere Informationen finden Sie auf Wikipedia im Artikel zur [binären Klassifizierung](https://en.wikipedia.org/wiki/Binary_classification).

## <a name="multiclass-classification"></a>Multiklassenklassifizierung

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um die Klasse (Kategorie) einer Dateninstanz vorherzusagen. Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele. Jede Bezeichnung ist eine ganze Zahl zwischen 0 und k-1, wobei k die Anzahl der Klassen ist. Die Ausgabe eines Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen. Zu den Beispielen für Multiklassen-Klassifizierungsszenarien zählen:

* Ermitteln der Rasse eines Hundes als „Sibirischer Husky“, „Golden Retriever“, „Pudel“ usw.
* Verstehen von Filmkritiken als „positiv“, „neutral“ oder „negativ“.
* Kategorisieren von Hoteltests in „Lage“, „Preis“, „Sauberkeit“ usw.

Weitere Informationen finden Sie auf Wikipedia im Artikel zur [Multiklassenklassifizierung](https://en.wikipedia.org/wiki/Multiclass_classification).

## <a name="regression"></a>Regression

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, die verwendet wird, um den Wert der Bezeichnung aus einem Satz verwandter Features vorherzusagen. Die Bezeichnung kann einen realen Wert haben und stammt nicht aus einem endlichen Satz von Werten wie bei Klassifizierungsaufgaben. Regressionsalgorithmen modellieren die Abhängigkeit der Bezeichnung von den zugehörigen verwandten Features, um zu bestimmen, wie sich die Bezeichnung ändert, wenn die Werte der Features variiert werden. Die Eingabe eines Regressionsalgorithmus ist eine Reihe von Beispielen mit Bezeichnungen bekannter Werte. Die Ausgabe eines Regressionsalgorithmus ist eine Funktion, die Sie verwenden können, um den Bezeichnungswert für einen neuen Satz von Eingabefeatures vorherzusagen. Beispiele für Regressionsszenarien sind:

* Hauspreisvorhersagen basierend auf Hausattributen wie der Anzahl von Schlafzimmern, Lage und Größe.
* Vorhersagen zukünftiger Aktienkurse basierend auf historischen Daten und aktuellen Markttrends.
* Vorhersagen für den Verkauf eines Produkts basierend auf Werbebudgets.

> [!NOTE]
> Derzeit wird noch an der ML.NET-Unterstützung für Regressionsaufgaben, die Zeitreihen umfassen, gearbeitet.

## <a name="clustering"></a>Clusterbildung

Eine [nicht überwachte Machine Learning](glossary.md#unsupervised-machine-learning)-Aufgabe, die verwendet wird, um Instanzen von Daten in Clustern zu gruppieren, die ähnliche Merkmale aufweisen. Die Clusterbildung kann auch zum Identifizieren von Beziehungen in einem Dataset verwendet werden, die Sie möglicherweise nicht logisch durch Durchsuchen oder einfache Beobachtung ableiten können. Die Eingaben und Ausgaben eines Clusterbildungsalgorithmus hängen von der ausgewählten Methodik ab. Sie können einen verteilungs-, schwerpunkt-, konnektivitäts- oder dichtebasierten Ansatz wählen. ML.NET unterstützt derzeit einen schwerpunktbasierten Ansatz bei Verwendung der K-Means-Clusterbildung. Beispiele für Clusterbildungsszenarien sind:

* Grundlegendes zu Segmenten von Hotelgästen basierend auf Gewohnheiten und Merkmalen der Hotelauswahl.
* Identifizieren von Kundensegmenten und demografischen Daten, um gezielte Werbekampagnen erstellen zu können.
* Kategorisieren des Lagerbestands basierend auf Produktionsmetriken.

## <a name="anomaly-detection-coming-soon"></a>Anomalieerkennung (*in Kürze*)

## <a name="ranking-coming-soon"></a>Rangfolge (*in Kürze*)

## <a name="recommendation-coming-soon"></a>Empfehlung (*in Kürze*)

