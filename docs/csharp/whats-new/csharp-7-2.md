---
title: Neues in C# 7.2
description: "Eine Übersicht der neuen Funktionen in C# 7.2"
keywords: C#-Sprachentwurf, 7.2, Visual Studio 2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 9e7fefde6763dbd5c73c01e45e5652d9f207c213
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="whats-new-in-c-72"></a>Neues in C# 7.2

C# 7.2 ist ein weiteres Release einer Unterversion, das eine Reihe nützlicher Funktionen ergänzt.
Ein Aspekt für diesen Release ist die effizientere Arbeit mit Werttypen durch Vermeiden unnötiger Kopien oder Zuweisungen. 

Die restlichen Funktionen sind kleine Features, die den Komfort steigern.

C# 7.2 verwendet das Konfigurationselement [Sprachversionsauswahl](csharp-7-1.md#language-version-selection), um die Version der Compilersprache auszuwählen.

Die neuen Sprachfeatures in diesem Release umfassen:

* [Verweissemantik mit Werttypen](#reference-semantics-with-value-types)
  - Eine Kombination aus Verbesserungen der Syntax, die das Arbeiten mit Werttypen mithilfe von Verweissemantik ermöglichen.
* [Nicht schließende benannte Argumente](#non-trailing-named-arguments)
  - Positionelle Argumente können auf benannte Argumente folgen.
* [Führende Unterstriche in numerischen Literalen](#leading-underscores-in-numeric-literals)
  - Numerische Literale dürfen jetzt führende Unterstriche vor aufgeführten Stellen aufweisen.
* [`private protected`-Zugriffsmodifizierer](#private-protected)
  - Der `private protected`-Zugriffsmodifizierer ermöglicht den Zugriff für abgeleitete Klassen innerhalb der gleichen Assembly.

## <a name="reference-semantics-with-value-types"></a>Verweissemantik mit Werttypen

In 7.2 eingeführte Sprachfeatures ermöglichen das Arbeiten mit Werttypen bei Verwendung der Verweissemantik. Sie dienen dazu, die Leistung durch Minimieren des Kopierens von Werttypen zu steigern, ohne die Speicherzuweisungen nach sich zu ziehen, die eine Verwendung von Verweistypen mit sich bringen würde. Das Feature beinhaltet:

 - Den `in`-Modifizierer für Parameter zur Angabe, dass ein Argument durch Verweis übergeben, von der aufgerufenen Methode aber nicht verändert wird.
 - Der `ref readonly`-Modifizierer für die Methodenrückgabe, um anzugeben, dass eine Methode ihren Wert als Verweis zurückgibt und keinen Schreibzugriff auf dieses Objekt zulässt.
 - Die `readonly struct`-Deklaration, um anzugeben, dass eine Struktur unveränderlich ist und ihren Membermethoden als `in`-Parameter übergeben werden sollte.
 - Die `ref struct`-Deklaration, um anzugeben, dass ein Strukturtyp direkt auf verwalteten Arbeitsspeicher zugreift und immer per Stapel zugeordnet werden muss.

Weitere Informationen zu allen diesen Änderungen finden Sie unter [Verwenden von Werttypen mit Verweissemantik](../reference-semantics-with-value-types.md).

## <a name="non-trailing-named-arguments"></a>Nicht schließende benannte Argumente

Methodenaufrufe dürfen jetzt benannte Argumente verwenden, die positionellen Argumenten vorstehen, wenn diese benannten Argumente in der richtigen Position verwendet werden. Weitere Informationen finden Sie unter [Benannte und optionale Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Führende Unterstriche in numerischen Literalen

Die Implementierung der Unterstützung für Stellentrennzeichen in C# 7.0 ließ den Unterstrich `_` nicht als erstes Zeichen von Literalwerten zu. Hexadezimale und binäre numerische Literale dürfen jetzt mit einem `_` beginnen. 

Zum Beispiel:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>Zugriffsmodifizierer _private protected_

Schließlich zeigt der neue, zusammengesetzte Zugriffsmodifizierer `private protected` an, dass auf ein Element durch eine es enthaltende Klasse oder durch innerhalb der gleichen Assembly deklarierte abgeleitete Klassen zugegriffen werden darf. Während `protected internal` den Zugriff durch abgeleitete Klassen oder Klassen, die sich in der gleichen Assembly befinden, erlaubt, schränkt `private protected` den Zugriff auf innerhalb der gleichen Assembly deklarierte abgeleitete Typen ein.

Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../language-reference/keywords/access-modifiers.md) in der Sprachreferenz.
