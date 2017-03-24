---
title: "Tabelle f&#252;r explizite numerische Konvertierungen (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Konvertierungen [C#], Explizit numerisch"
  - "Explizite numerische Konvertierung [C#]"
  - "Numerische Konvertierungen [C#], Explizit"
  - "Numerische Datentypen [C#]"
  - "Typkonvertierung [C#], Explizit numerisch"
  - "Typen [C#], Explizite numerische Konvertierungen"
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Tabelle f&#252;r explizite numerische Konvertierungen (C#-Referenz)
Die explizite numerische Konvertierung wird verwendet, um einen beliebigen numerischen Typ unter Verwendung eines Ausdrucks für die Typumwandlung in einen anderen numerischen Typ zu konvertieren, für den keine implizite Konvertierung stattfindet.  Diese Konvertierungen sind in der folgenden Tabelle zusammengefasst.  
  
 Weitere Informationen über Konvertierungen finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
|Von|To|  
|---------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`byte`, `ushort`, `uint`, `ulong` oder `char`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`Sbyte` oder `char`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`sbyte`,  `byte`,  `ushort`,  `uint`,  `ulong` oder  `char`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`sbyte`,  `byte`,  `short` oder  `char`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` `` oder `char`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`sbyte`, `byte`,  `short`,  `ushort`,  `int` oder  `char`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`sbyte`,  `byte`,  `short`,  `ushort`,  `int`,  `uint`,  `ulong` oder  `char`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`sbyte`,  `byte`,  `short`,  `ushort`,  `int`,  `uint`,  `long` oder  `char`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`sbyte`, `byte` oder  `short`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` `` oder `decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` `` oder `decimal`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`sbyte`,  `byte`,  `short`,  `ushort`,  `int`,  `uint`,  `long`,  `ulong`,  `char`,  `float` oder  `double`|  
  
## Hinweise  
  
-   Explizite numerische Konvertierungen können zu einem Genauigkeitsverlust oder zur Auslösung von Ausnahmen führen.  
  
-   Wenn Sie einen Wert vom Typ `decimal` in einen ganzzahligen Typ konvertieren, wird dieser auf den nächsten ganzzahligen Wert gegen 0 \(null\) gerundet.  Wenn sich der resultierende ganzzahlige Wert außerhalb des für den Zieltyp gültigen Bereichs befindet, wird eine <xref:System.OverflowException> ausgelöst.  
  
-   Bei der Konvertierung eines `double`\-Werts oder `float`\-Werts in einen ganzzahligen Typ wird der Wert abgeschnitten.  Befindet sich der resultierende Ganzzahlwert außerhalb des Zieltypbereichs, hängt das Ergebnis vom Kontext mit Überlaufprüfung ab.  In einem aktivierten Kontext wird eine `OverflowException` ausgelöst, während in einem nicht aktivierten Kontext das Ergebnis ein unspezifischer Wert des Zieltyps ist.  
  
-   Wenn Sie `double` in `float` konvertieren, wird der `double`\-Wert zum nächsten `float`\-Wert gerundet.  Wenn der `double`\-Wert zu klein bzw. zu groß für den Bereich des Zieltyps ist, ist das Ergebnis gleich null oder unendlich.  
  
-   Bei der Konvertierung von `float` oder `double` in `decimal` wird der Quellwert in die `decimal`\-Darstellung konvertiert und gegebenenfalls auf die nächste Zahl hinter der 28. Dezimalstelle gerundet.  Abhängig vom Ausgangswert können folgende Ergebnisse auftreten:  
  
    -   Wenn der Quellwert zu klein für die `decimal`\-Darstellung ist, ist das Ergebnis gleich null.  
  
    -   Wenn der Quellwert ein nicht numerischer Wert, unendlich oder zu groß für die `decimal`\-Darstellung ist, wird eine `OverflowException` ausgelöst.  
  
-   Wenn Sie `decimal` in `float` oder `double` konvertieren, wird der `decimal`\-Wert zum nächsten `double`\-Wert oder `float`\-Wert gerundet.  
  
 Weitere Informationen über explizite Konvertierung finden Sie unter Explicit in der C\#\-Sprachenspezifikation.  Informationen zum Zugriff auf die Spezifikation finden Sie unter [C\#\-Sprachspezifikation](../../../csharp/language-reference/language-specification.md).  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Operator \(\)](../../../csharp/language-reference/operators/invocation-operator.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)