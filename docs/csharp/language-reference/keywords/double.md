---
title: "double (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "double"
  - "double_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "double-Datentyp [C#]"
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# double (C#-Referenz)
Das Schlüsselwort `double` kennzeichnet einen einfachen Typ, in dem 64\-Bit\-Gleitkommawerte gespeichert werden.  Der folgenden Tabelle können Sie die Genauigkeit und den ungefähren Bereich des `double`\-Typs entnehmen.  
  
|Typ|Ungefährer Bereich|Genauigkeit|.NET Framework\-Typ|  
|---------|------------------------|-----------------|-------------------------|  
|`double`|±5.0 × 10<sup>−324</sup> bis ±1.7 × 10<sup>308</sup>|15\-16 Stellen|<xref:System.Double?displayProperty=fullName>|  
  
## Literale  
 Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird standardmäßig als `double`\-Typ behandelt.  Wenn dagegen eine ganze Zahl als `double` behandelt werden soll, verwenden Sie das Suffix d oder D. Beispiel:  
  
```  
  
double x = 3D;  
```  
  
## Konvertierungen  
 Numerische ganzzahlige Typen und Gleitkommatypen können zusammen in einem Ausdruck verwendet werden.  In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.  Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:  
  
-   Wenn einer der Gleitkommatypen `double` lautet, wird der Ausdruck als `double` bzw. bei relationalen oder booleschen Ausdrücken als [bool](../../../csharp/language-reference/keywords/bool.md) ausgewertet.  
  
-   Wenn der Ausdruck keinen `double`\-Typ enthält, wird er als [float](../../../csharp/language-reference/keywords/float.md) \(bzw. im Fall relationaler oder boolescher Ausdrücke als [bool](../../../csharp/language-reference/keywords/bool.md)\) ausgewertet.  
  
 Ein Gleitkommaausdruck kann die folgenden Wertgruppen enthalten:  
  
-   Positive und negative Null.  
  
-   Positive und negative Unendlichkeit.  
  
-   Nicht numerischer Wert \(NaN, Not a Number\).  
  
-   Endliche Menge von Werten ungleich 0 \(null\).  
  
 Weitere Informationen zu diesen Werten finden Sie im IEEE\-Standard für binäre Gleitkommaarithmetik auf der Website .  
  
## Beispiel  
 Im folgenden Beispiel werden die Typen [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) und `double` addiert, was zu einem `double`\-Ergebnis führt.  
  
 [!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/csharp/double_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für Gleitkommatypen](../../../csharp/language-reference/keywords/floating-point-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)