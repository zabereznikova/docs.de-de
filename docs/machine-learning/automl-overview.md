---
title: Automatisiertes Machine Learning mit ML.NET
description: Übersicht über die automatische Modellauswahl und das Training
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: c6c369dc0b0375f180d33d85ef320ddb24102f3e
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740096"
---
# <a name="automated-machine-learning-with-mlnet"></a>Automatisiertes Machine Learning mit ML.NET

Automatisiertes Machine Learning ist eine Funktion von ML.NET, die eine automatische Modellauswahl und das Training durchführt. Sie geben den Machine Learning-Task an, stellen das Dataset bereit, und automatisierte ML wählt das Modell mit den besten Metriken aus. Ausgabe:

- eine Modelldatei, die in die Vorhersageanwendung geladen werden kann
- Anwendungscode, um Vorhersagen zu treffen
- den Quellcode für die Funktionsauswahl und das Modelltraining (um das Modell zu verstehen)

> [!NOTE]
> Dieses Feature befindet sich derzeit in der Vorschauphase, und das Material kann jederzeit geändert werden.

Das automatisierte ML ist derzeit auf Machine Learning-[Tasks](resources/tasks.md) für binäre Klassifikation, Multiklassenklassifizierung und Regression beschränkt. Andere Machine Learning-Tasks werden in zukünftigen Versionen unterstützt.

Es gibt drei Möglichkeiten, automatisiertes ML zu verwenden:

1. Über eine grafische Benutzeroberfläche mit dem [ML.NET-Modell-Generator](automate-training-with-model-builder.md)
1. Über die Befehlszeile mit der [ML.NET CLI](automate-training-with-cli.md)
1. Über eine Anwendung mit der [automatisierten ML-API](how-to-guides/how-to-use-the-automl-api.md)
