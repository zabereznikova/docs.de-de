---
title: Wart barkeits Regeln (Code Analyse)
description: Erfahren Sie mehr über die wart barkeits Regeln der Code Analyse.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- rules, maintainability
- managed code analysis rules, maintainability rules
- maintainability rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: fc2ef2b42eeba241b7af66b579a60365ad2b88c7
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590682"
---
# <a name="maintainability-rules"></a>Wartbarkeitsregeln

Wart barkeits Regeln unterstützen die Verwaltung von Bibliotheken und Anwendungen.

## <a name="in-this-section"></a>In diesem Abschnitt

| Regel | Beschreibung |
|-----------|-----------------------------------|
| [CA1501: Übermäßige Vererbung vermeiden.](ca1501.md) | Ein Typ ist in seiner Vererbungshierarchie mehr als vier Ebenen tief. Tief verschachtelte Typenhierarchien können schwer zu verfolgen, verstehen und verwalten sein. |
| [CA1502: Übermäßige Komplexität vermeiden.](ca1502.md) | Diese Regel ermöglicht Aussagen über die Anzahl linear unabhängiger Pfade in einer Methode, wobei die Anzahl der Pfade durch die Anzahl und Komplexität bedingter Branches bestimmt wird. |
| [CA1505: Nicht wartbaren Code vermeiden.](ca1505.md) | Ein Typ oder eine Methode verfügt über einen niedrigen Wartbarkeitsindexwert. Ein niedriger Wartbarkeitsindex zeigt an, dass ein Typ oder eine Methode wahrscheinlich schwer zu verwalten ist und geeignet für einen Neuentwurf wäre. |
| [CA1506: Übermäßige Klassenkopplungen vermeiden.](ca1506.md) | Durch diese Regel wird die Klassenkopplung gemessen, indem die eindeutigen Typverweise, die ein Typ oder eine Methode enthält, gezählt werden. |
| [CA1507: „nameof“ anstelle der Zeichenfolge verwenden](ca1507.md) | Ein Zeichenfolgenliterals wird als Argument verwendet, bei dem ein- `nameof` Ausdruck verwendet werden kann. |
| [CA1508: Toten Bedingungscode vermeiden](ca1508.md) | Eine Methode verfügt über bedingten Code, der immer zu oder zur Laufzeit ausgewertet wird `true` `false` . Dies führt zu einem unzustellbaren Code in der `false` Verzweigung der Bedingung. |
| [CA1509: Ungültiger Eintrag in der Konfigurationsdatei für die Codemetrik.](ca1509.md) | Code metrikregeln, wie z. b. [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) und [CA1506](ca1506.md), haben eine Konfigurationsdatei mit dem Namen mit `CodeMetricsConfig.txt` einem ungültigen Eintrag bereitgestellt. |

## <a name="see-also"></a>Siehe auch

- [Messen von Komplexität und Verwaltbarkeit von verwaltetem Code](/visualstudio/code-quality/code-metrics-values)
