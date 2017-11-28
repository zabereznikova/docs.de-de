---
title: Werttypen (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 281b811f2a8a1f2c364405b563f9f103899b492c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-c-reference"></a>Werttypen (C#-Referenz)
Die Werttypen sind in zwei Hauptkategorien unterteilt:  
  
-   [Strukturen](../../../csharp/language-reference/keywords/struct.md)  
  
-   [Enumerationen](../../../csharp/language-reference/keywords/enum.md)  
  
 Strukturen werden in diese Kategorien eingeteilt:  
  
-   Numerische Typen  
  
    -   [Integrale Typen](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [Gleitkommatypen](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [decimal](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   Benutzerdefinierte Strukturen  
  
## <a name="main-features-of-value-types"></a>Hauptfunktionen von Werttypen  
 Variablen, die auf Werttypen basieren, enthalten Werte direkt. Durch das Zuweisen einer Werttypvariablen zu einer anderen wird der enthaltene Wert kopiert. Dies unterscheidet sich von der Zuweisung von Verweistypvariablen. Dabei wird ein Verweis auf das Objekt, aber nicht das Objekt selbst kopiert.  
  
 Alle Werttypen werden implizit von <xref:System.ValueType?displayProperty=nameWithType> abgeleitet.  
  
 Im Gegensatz zu Verweistypen können Sie von Werttypen keinen neuen ableiten. Strukturen können aber wie Verweistypen Schnittstellen implementieren.  
  
 Im Gegensatz zu Verweistypen können Werttypen nicht den Wert `null` enthalten. Allerdings ermöglicht es die Funktion [Nullable-Typ](../../../csharp/programming-guide/nullable-types/index.md), dass Werttypen `null` zugewiesen werden können.  
  
 Jeder Werttyp hat einen impliziten Standardkonstruktor, der den Standardwert dieses Typs initialisiert. Informationen zu den Standardwerten von Werttypen finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## <a name="main-features-of-simple-types"></a>Hauptfunktionen von einfachen Typen  
 Alle einfachen Typen, die für C# wesentlichen Typen, sind Aliasse der Systemtypen aus dem .NET Framework. [int](../../../csharp/language-reference/keywords/int.md) ist z.B. ein Alias von <xref:System.Int32?displayProperty=nameWithType>. Eine vollständige Liste der Aliase finden Sie unter [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md).  
  
 Konstante Ausdrücke, deren Operanden alle einfache Typkonstanten sind, werden zur Kompilierzeit ausgewertet.  
  
 Einfache Typen können mithilfe von Literalen initialisiert werden. „A“ ist beispielsweise ein Literal vom Typ `char`, und 2001 ist ein Literal vom Typ `int`.  
  
## <a name="initializing-value-types"></a>Initialisieren von Werttypen  
 Lokale Variablen in C# müssen vor ihrer Verwendung initialisiert werden. Sie könnten eine lokale Variable beispielsweise ohne Initialisierung wie im folgenden Beispiel deklarieren:  
  
```  
int myInt;  
```  
  
 Sie können sie nicht verwenden, bis Sie sie initialisiert haben. Sie können sie mit der folgenden Anweisung initialisieren:  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 Diese Anweisung entspricht der folgenden Anweisung:  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 Natürlich können Sie sich die Deklaration und die Initialisierung in derselben Anweisung befinden, wie in den folgenden Beispielen dargestellt:  
  
```  
int myInt = new int();  
```  
  
 – oder –  
  
```  
int myInt = 0;  
```  
  
 Durch die Verwendung des Operators [new](../../../csharp/language-reference/keywords/new.md) wird der Standardkonstruktor des angegebenen Typs aufgerufen und der Variablen der Standardwert zugewiesen. Im vorherigen Beispiel hat der Standardkonstruktor `myInt` den Wert `0` zugewiesen. Weitere Informationen zu Werten, die durch Aufrufen von Standardkonstruktoren zugewiesen werden, finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Verwenden Sie bei benutzerdefinierten Typen [new](../../../csharp/language-reference/keywords/new.md) zum Aufrufen des Standardkonstruktors. Die folgende Anweisung ruft z.B. den Standardkonstruktor der `Point`-Struktur auf:  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 Nach diesem Aufruf gilt die Struktur als definitiv zugewiesen. Das bedeutet, dass alle ihre Member mit ihren Standardwerten initialisiert werden.  
  
 Weitere Informationen zum Operator „new“ finden Sie unter [new](../../../csharp/language-reference/keywords/new.md).  
  
 Informationen zum Formatieren der Ausgabe von numerischen Typen finden Sie unter [Tabelle zur Formatierung numerischer Ergebnisse](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Typen](../../../csharp/language-reference/keywords/types.md)  
 [Referenztabellen für Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)
