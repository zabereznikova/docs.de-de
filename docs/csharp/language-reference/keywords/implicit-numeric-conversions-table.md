---
title: "Tabelle f&#252;r implizite numerische Konvertierungen (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Konvertierungen [C#], Implizit numerisch"
  - "Implizite numerische Konvertierungen [C#]"
  - "Numerische Konvertierungen [C#], Implizite"
  - "Typen [C#], Implizite numerische Konvertierungen"
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Tabelle f&#252;r implizite numerische Konvertierungen (C#-Referenz)
In der folgenden Tabelle sehen Sie implizite numerische Konvertierungen, die vordefiniert sind.  Implizite Konvertierungen können in zahlreichen Situationen auftreten, z. B. in Methodenaufrufen und Zuweisungsanweisungen.  
  
|Von|To|  
|---------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`short`, `int`, `long`, `float`, `double` oder `decimal`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`int`, `long`, `float`, `double` oder `decimal`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`long`, `float`, `double` oder `decimal`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`long`, `ulong`, `float`, `double` oder `decimal`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`float`, `double` oder `decimal`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`ushort`, `int`,  `uint`,  `long`, `ulong`,  `float`,  `double` oder `decimal`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`,  `double` oder `decimal`|  
  
## Hinweise  
  
-   Genauigkeit, jedoch nicht die Helligkeit verloren in die Konvertierung von `int`, `uint`, `long`, oder `ulong` , `float` und von `long` oder `ulong` , `double`.  
  
-   Es finden keine impliziten Konvertierungen in den `char`\-Typ statt.  
  
-   Es gibt keine impliziten Konvertierungen zwischen Gleitkommatypen und dem `decimal`\-Typ.  
  
-   Ein konstanter Ausdruck vom Typ `int` kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, vorausgesetzt, der Wert des konstanten Ausdrucks liegt innerhalb des für den Zieltyp gültigen Wertebereichs.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)