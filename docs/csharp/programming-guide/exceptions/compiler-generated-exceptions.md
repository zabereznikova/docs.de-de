---
title: Vom Compiler generierte Ausnahmen – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 1d2d561df3e496893657b050fa93b44c56542d97
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84240731"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)

Einige Ausnahmen werden automatisch von der .NET Runtime ausgelöst, wenn grundlegende Operationen fehlschlagen. Diese Ausnahmen und die entsprechenden Fehlerbedingungen sind in der folgenden Tabellen aufgelistet.  
  
|Ausnahme|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|Eine Basisklasse für Ausnahmen (z.B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>), die während arithmetischer Operationen auftreten.|  
|<xref:System.ArrayTypeMismatchException>|Wird ausgelöst, wenn ein Array ein gegebenes Element nicht speichern kann, weil der tatsächliche Typ des Element mit dem tatsächlichen Typs des Arrays inkompatibel ist.|  
|<xref:System.DivideByZeroException>|Wird ausgelöst, wenn versucht wird, einen Integralwert durch null zu teilen.|  
|<xref:System.IndexOutOfRangeException>|Wird ausgelöst, wenn versucht wird, ein Array zu indizieren, während der Index weniger als null ist oder sich außerhalb der Arraygrenzen befindet.|  
|<xref:System.InvalidCastException>|Wird ausgelöst, wenn eine explizite Konvertierung eines Basistyps in eine Schnittstelle oder in einen abgeleiteten Typen zur Laufzeit fehlschlägt.|  
|<xref:System.NullReferenceException>|Wird ausgelöst, wenn versucht wird, auf ein Objekt zu verweisen, dessen Wert [NULL](../../language-reference/keywords/null.md) ist.|  
|<xref:System.OutOfMemoryException>|Wird ausgelöst, wenn der Versuch, Speicher mithilfe des Operators [new](../../language-reference/operators/new-operator.md) zuzuweisen, fehlschlägt. Dies weist darauf hin, dass der für die Common Language Runtime verfügbare Speicher ausgeschöpft ist.|  
|<xref:System.OverflowException>|Wird ausgelöst, wenn eine arithmetische Operation im Kontext `checked` überläuft.|  
|<xref:System.StackOverflowException>|Wird ausgelöst, wenn der Ausführungsstapel durch zu viele ausstehende Methodenaufrufe ausgeschöpft ist; weist für gewöhnlich auf eine tiefe oder unendliche Rekursion hin.|  
|<xref:System.TypeInitializationException>|Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst, und keine kompatiblen `catch`-Klausel vorhanden ist, die sie abfangen könnte.|  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Ausnahmen und Ausnahmebehandlung](./index.md)
- [Ausnahmebehandlung](./exception-handling.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
