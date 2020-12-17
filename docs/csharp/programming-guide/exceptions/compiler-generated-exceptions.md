---
title: Vom Compiler generierte Ausnahmen – C#-Programmierhandbuch
description: Erfahren Sie mehr über vom Compiler generierte Ausnahmen. Hier finden Sie eine Liste mit automatisch ausgelösten Ausnahmen und den zugehörigen Fehlerbedingungen.
ms.date: 12/09/2020
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 43bacbb1025bc0af3a5f21979315b3d1b0d61066
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110350"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)

Einige Ausnahmen werden automatisch von der .NET Runtime ausgelöst, wenn grundlegende Operationen fehlschlagen. Diese Ausnahmen und die entsprechenden Fehlerbedingungen sind in der folgenden Tabellen aufgelistet.

|Ausnahme|Beschreibung|
|---------------|-----------------|
|<xref:System.ArithmeticException>|Eine Basisklasse für Ausnahmen (z.B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>), die während arithmetischer Operationen auftreten.|
|<xref:System.ArrayTypeMismatchException>|Diese Ausnahme wird ausgelöst, wenn ein Array ein gegebenes Element nicht speichern kann, weil der tatsächliche Typ des Elements mit dem tatsächlichen Typs des Arrays inkompatibel ist.|
|<xref:System.DivideByZeroException>|Wird ausgelöst, wenn versucht wird, einen Integralwert durch null zu teilen.|
|<xref:System.IndexOutOfRangeException>|Wird ausgelöst, wenn versucht wird, ein Array zu indizieren, während der Index weniger als null ist oder sich außerhalb der Arraygrenzen befindet.|
|<xref:System.InvalidCastException>|Wird ausgelöst, wenn eine explizite Konvertierung eines Basistyps in eine Schnittstelle oder in einen abgeleiteten Typen zur Laufzeit fehlschlägt.|
|<xref:System.NullReferenceException>|Wird ausgelöst, wenn versucht wird, auf ein Objekt zu verweisen, dessen Wert [NULL](../../language-reference/keywords/null.md) ist.|
|<xref:System.OutOfMemoryException>|Wird ausgelöst, wenn der Versuch, Speicher mithilfe des Operators [new](../../language-reference/operators/new-operator.md) zuzuweisen, fehlschlägt. Diese Ausnahme weist darauf hin, dass der für die Common Language Runtime verfügbare Arbeitsspeicher aufgebraucht wurde.|
|<xref:System.OverflowException>|Wird ausgelöst, wenn eine arithmetische Operation im Kontext `checked` überläuft.|
|<xref:System.StackOverflowException>|Wird ausgelöst, wenn der Ausführungsstapel durch zu viele ausstehende Methodenaufrufe ausgeschöpft ist; weist für gewöhnlich auf eine tiefe oder unendliche Rekursion hin.|
|<xref:System.TypeInitializationException>|Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst, und keine kompatiblen `catch`-Klausel vorhanden ist, die sie abfangen könnte.|

## <a name="see-also"></a>Siehe auch

- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
