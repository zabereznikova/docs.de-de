---
title: Neues in C# 7.2
description: Eine Übersicht der neuen Funktionen in C# 7.2
ms.date: 08/16/2017
ms.openlocfilehash: 7febefb81bbea6f24690adb05488ad6a18bbf552
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75694594"
---
# <a name="whats-new-in-c-72"></a>Neues in C# 7.2

C# 7.2 ist ein weiteres Release einer Unterversion, das eine Reihe nützlicher Funktionen ergänzt.
Ein Aspekt für diesen Release ist die effizientere Arbeit mit Werttypen durch Vermeiden unnötiger Kopien oder Zuweisungen.

Die restlichen Funktionen sind kleine Features, die den Komfort steigern.

C# 7.2 verwendet das Konfigurationselement [Sprachversionsauswahl](../language-reference/configure-language-version.md), um die Version der Compilersprache auszuwählen.

Die neuen Sprachfeatures in diesem Release umfassen:

- [Techniken zum Schreiben von sicherem, effizientem Code](#safe-efficient-code-enhancements)
  - Eine Kombination aus Verbesserungen der Syntax, die das Arbeiten mit Werttypen mithilfe von Verweissemantik ermöglichen.
- [Nicht schließende benannte Argumente](#non-trailing-named-arguments)
  - Positionelle Argumente können auf benannte Argumente folgen.
- [Führende Unterstriche in numerischen Literalen](#leading-underscores-in-numeric-literals)
  - Numerische Literale dürfen jetzt führende Unterstriche vor aufgeführten Stellen aufweisen.
- [`private protected`-Zugriffsmodifizierer](#private-protected-access-modifier)
  - Der `private protected`-Zugriffsmodifizierer ermöglicht den Zugriff für abgeleitete Klassen innerhalb der gleichen Assembly.
- [Bedingte`ref` Ausdrücke](#conditional-ref-expressions)
  - Das Ergebnis eines bedingten Ausdrucks (`?:`) kann jetzt ein Verweis sein.

Dieser Artikel enthält im Folgenden eine Übersicht über die einzelnen Funktionen. Sie werden die Hintergründe jeder einzelnen Funktion erfahren. Sie werden die Syntax erlernen. Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:

1. Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.
1. Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.
1. Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.
1. Führen Sie aus `dotnet try`.

## <a name="safe-efficient-code-enhancements"></a>Erweiterungen von sicherem, effizientem Code

In 7.2 eingeführte Sprachfeatures ermöglichen das Arbeiten mit Werttypen bei Verwendung der Verweissemantik. Sie dienen dazu, die Leistung durch Minimieren des Kopierens von Werttypen zu steigern, ohne die Speicherzuweisungen nach sich zu ziehen, die eine Verwendung von Verweistypen mit sich bringen würde. Das Feature beinhaltet:

- Den `in`-Modifizierer für Parameter zur Angabe, dass ein Argument durch Verweis übergeben, von der aufgerufenen Methode aber nicht verändert wird. Das Hinzufügen des Modifizierers `in` zu einem Argument ist eine [quellkompatible Änderung](version-update-considerations.md#source-compatible-changes).
- Der `ref readonly`-Modifizierer für die Methodenrückgabe, um anzugeben, dass eine Methode ihren Wert als Verweis zurückgibt und keinen Schreibzugriff auf dieses Objekt zulässt. Das Hinzufügen des Modifizierers `ref readonly` ist eine [quellkompatible Änderung](version-update-considerations.md#source-compatible-changes), wenn die Rückgabe einem Wert zugewiesen wird. Das Hinzufügen des Modifizierers `readonly` zu einer vorhandenen `ref`-Rückgabeanweisung ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes). Es verlangt von Aufrufern das Aktualisieren der lokalen `ref`-Variablen, um den `readonly`-Modifizierer einzuschließen.
- Die `readonly struct`-Deklaration, um anzugeben, dass eine Struktur unveränderlich ist und ihren Membermethoden als `in`-Parameter übergeben werden sollte. Das Hinzufügen des Modifizierers `readonly` zu einer vorhandenen Strukturdeklaration ist eine [binärkompatible Änderung](version-update-considerations.md#binary-compatible-changes).
- Die `ref struct`-Deklaration, um anzugeben, dass ein Strukturtyp direkt auf verwalteten Arbeitsspeicher zugreift und immer per Stapel zugeordnet werden muss. Das Hinzufügen des Modifizierers `ref` zu einer vorhandenen `struct`-Deklaration ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes). Ein `ref struct` kann kein Mitglied einer Klasse sein oder an anderen Stellen verwendet werden, wo es auf dem Heap zugewiesen werden könnte.

Weitere Informationen zu all diesen Änderungen finden Sie unter [Schreiben von sicherem und effizientem Code](../write-safe-efficient-code.md).

## <a name="non-trailing-named-arguments"></a>Nicht schließende benannte Argumente

Methodenaufrufe dürfen jetzt benannte Argumente verwenden, die positionellen Argumenten vorstehen, wenn diese benannten Argumente in der richtigen Position verwendet werden. Weitere Informationen finden Sie unter [Benannte und optionale Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Führende Unterstriche in numerischen Literalen

Die Implementierung der Unterstützung für Stellentrennzeichen in C# 7.0 ließ den Unterstrich `_` nicht als erstes Zeichen von Literalwerten zu. Hexadezimale und binäre numerische Literale dürfen jetzt mit einem `_` beginnen.

Zum Beispiel:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>Zugriffsmodifizierer *private protected*

Ein neuer zusammengesetzter Zugriffsmodifizierer: `private protected` zeigt an, dass auf ein Element durch eine es enthaltende Klasse oder durch innerhalb der gleichen Assembly deklarierte abgeleitete Klassen zugegriffen werden darf. Während `protected internal` den Zugriff durch abgeleitete Klassen oder Klassen, die sich in der gleichen Assembly befinden, erlaubt, schränkt `private protected` den Zugriff auf innerhalb der gleichen Assembly deklarierte abgeleitete Typen ein.

Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../language-reference/keywords/access-modifiers.md) in der Sprachreferenz.

## <a name="conditional-ref-expressions"></a>Bedingte `ref` Ausdrücke

Schließlich kann ein bedingter Ausdruck als Ergebnis einen Verweis anstatt eines Werts erzeugen. Beispielsweise würden Sie folgendes schreiben, um einen Verweis auf das erste Element in einem von zwei Arrays abzurufen:

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

Die Variable `r` ist ein Verweis auf den ersten Wert in `arr` oder `otherArr`.

Weitere Informationen finden Sie unter [conditional-Operator (?:)](../language-reference/operators/conditional-operator.md) in der Sprachreferenz.
