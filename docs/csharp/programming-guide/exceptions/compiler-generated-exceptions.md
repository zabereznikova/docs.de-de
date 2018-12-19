---
title: Vom Compiler generierte Ausnahmen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: e21b75e5b7e338bda54ca00abaa733775865fdb9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238389"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)
Einige Ausnahmen werden automatisch von der Common Language Runtime (CLR) von .NET Framework ausgelöst, wenn grundlegende Operationen fehlschlagen. Diese Ausnahmen und die entsprechenden Fehlerbedingungen sind in der folgenden Tabellen aufgelistet.  
  
|Ausnahme|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|Eine Basisklasse für Ausnahmen (z.B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>), die während arithmetischer Operationen auftreten.|  
|<xref:System.ArrayTypeMismatchException>|Wird ausgelöst, wenn ein Array ein gegebenes Element nicht speichern kann, weil der tatsächliche Typ des Element mit dem tatsächlichen Typs des Arrays inkompatibel ist.|  
|<xref:System.DivideByZeroException>|Wird ausgelöst, wenn versucht wird, einen Integralwert durch null zu teilen.|  
|<xref:System.IndexOutOfRangeException>|Wird ausgelöst, wenn versucht wird, ein Array zu indizieren, während der Index weniger als null ist oder sich außerhalb der Arraygrenzen befindet.|  
|<xref:System.InvalidCastException>|Wird ausgelöst, wenn eine explizite Konvertierung eines Basistyps in eine Schnittstelle oder in einen abgeleiteten Typen zur Laufzeit fehlschlägt.|  
|<xref:System.NullReferenceException>|Wird ausgelöst, wenn versucht wird, auf ein Objekt zu verweisen, dessen Wert [NULL](../../../csharp/language-reference/keywords/null.md) ist.|  
|<xref:System.OutOfMemoryException>|Wird ausgelöst, wenn der Versuch, Speicher mithilfe des Operators [new](../../../csharp/language-reference/keywords/new-operator.md) zuzuweisen, fehlschlägt. Dies weist darauf hin, dass der für die Common Language Runtime verfügbare Speicher ausgeschöpft ist.|  
|<xref:System.OverflowException>|Wird ausgelöst, wenn eine arithmetische Operation im Kontext `checked` überläuft.|  
|<xref:System.StackOverflowException>|Wird ausgelöst, wenn der Ausführungsstapel durch zu viele ausstehende Methodenaufrufe ausgeschöpft ist; weist für gewöhnlich auf eine tiefe oder unendliche Rekursion hin.|  
|<xref:System.TypeInitializationException>|Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst, und keine kompatiblen `catch`-Klausel vorhanden ist, die sie abfangen könnte.|  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md)  
- [Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md)  
- [try-catch](../../../csharp/language-reference/keywords/try-catch.md)  
- [try-finally](../../../csharp/language-reference/keywords/try-finally.md)  
- [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)
