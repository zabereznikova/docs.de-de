---
title: Was ist neu in c# 7.2
description: "Eine Übersicht über neue Funktionen in c# 7.2."
keywords: C#-Sprachentwurf 7.2, Visual Studio-2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a>Was ist neu in c# 7.2

C#-7.2 ist einem anderen Punkt-Version, die eine Reihe nützlicher Features hinzugefügt.
Ein Design für diese Version ist effizienter Werttypen arbeitet, indem Sie unnötige Kopien oder Zuordnungen zu vermeiden. 

Die übrigen Funktionen sind kleine, nice ist-Funktionen.

C#-7.2 verwendet die [Version Sprachauswahl](csharp-7-1.md#language-version-selection) Konfigurationselement, wählen Sie die Sprachversion der Compiler.

Die neuen Sprachfeatures in dieser Version sind:

* [Verweissemantik mit Werttypen](#reference-semantics-with-value-types)
  - Eine Kombination von Syntax Verbesserungen, die Arbeit mit Werttypen mit Verweissemantik zu ermöglichen.
* [Nachfolgende auf nicht benannte Argumente](#non-trailing-named-arguments)
  - Benannte Argumente können Positionsargumente folgen.
* [Führende Unterstriche in numerische Literale](#leading-underscores-in-numeric-literals)
  - Numerische Literale können jetzt führende Unterstriche, bevor Sie alle gedruckten Ziffern haben.
* [`private protected`Zugriffsmodifizierer](#private-protected)
  - Die `private protected` Zugriffsmodifizierer ermöglicht den Zugriff für abgeleitete Klassen in derselben Assembly.

## <a name="reference-semantics-with-value-types"></a>Verweissemantik mit Werttypen

7.2 eingeführte Sprachfunktionen können Sie die mit Verweissemantik mit Werttypen arbeiten. Sie dienen zum Erhöhen der Leistung durch Minimierung von Werttypen ohne die speicherbelegungen zugeordneten mit Referenztypen. Die Features umfassen:

 - Die `in` Modifizierer auf Parametern, um anzugeben, dass ein Argument als Verweis wird übergeben jedoch nicht von der aufgerufenen Methode geändert wird.
 - Die `ref readonly` Methode zurückgegeben wird, um anzugeben, dass eine Methode als Verweis den Wert zurückgibt, sondern schreibt, der diesem Objekt kann keine-Modifizierer.
 - Die `readonly struct` Deklaration, um anzugeben, dass eine Struktur unveränderlich ist und sollte, als übergeben werden ein `in` Parameter an die Membermethoden.
 - Die `ref struct` Deklaration, um anzugeben, dass ein Strukturtyp greift direkt auf verwalteten Speicher und immer Stapel zugeordnet werden muss.

Erfahren Sie mehr über diese Änderungen in [Verweissemantik Werttypen mit](../reference-semantics-with-value-types.md).

## <a name="non-trailing-named-arguments"></a>Nachfolgende auf nicht benannte Argumente

Methodenaufrufe können jetzt benannte Argumente, die Positionsargumente vorausgehen, wenn dieser benannten Argumenten in den korrekten Positionen befinden. Weitere Informationen finden Sie unter [benannte und optionale Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Führende Unterstriche in numerische Literale

Die Implementierung der Unterstützung für Trennzeichen für Ziffern in c# 7.0 nicht zulassen der `_` auf das erste Zeichen Literalwert sein. Hex und binäre numerische Literale beginnt nun mit einem `_`. 

Zum Beispiel:

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

Schließlich, einen neuen zusammengesetzten Zugriffsmodifizierer: `private protected` gibt an, dass ein Member von abgeleiteten Klassen zugegriffen werden kann, die in der gleichen Assembly deklariert werden. Während `protected internal` ermöglicht den Zugriff von abgeleiteten Klassen oder Klassen, die in der gleichen Assembly `private protected` schränkt den Zugriff auf abgeleitete Typen, die in der gleichen Assembly deklariert.

Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../language-reference/keywords/access-modifiers.md) in der Sprachreferenz.
