---
title: "float (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "float"
  - "float_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "float-Schlüsselwort [C#]"
  - "Gleitkommazahlen [C#], float-Schlüsselwort"
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# float (C#-Referenz)
Das Schlüsselwort `float` kennzeichnet einen einfachen Typ, in dem 32\-Bit\-Gleitkommawerte gespeichert werden.  Der folgenden Tabelle können Sie die Genauigkeit und den ungefähren Bereich des `float`\-Typs entnehmen.  
  
|Typ|Ungefährer Bereich|Genauigkeit|.NET Framework\-Typ|  
|---------|------------------------|-----------------|-------------------------|  
|`float`|\-3.4 × 10<sup>38</sup>bis \+3.4 × 10<sup>38</sup>|7 Stellen|<xref:System.Single?displayProperty=fullName>|  
  
## Literale  
 Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird als [double](../../../csharp/language-reference/keywords/double.md)\-Typ behandelt.  Verwenden Sie daher zum Initialisieren einer float\-Variablen das Suffix `f` oder `F`, wie im folgenden Beispiel gezeigt:  
  
```  
  
float x = 3.5F;  
```  
  
 Wenn Sie in der vorherigen Deklaration das Suffix nicht verwenden, tritt ein Kompilierungsfehler auf, da Sie versuchen, einen [double](../../../csharp/language-reference/keywords/double.md)\-Wert in einer `float`\-Variablen zu speichern.  
  
## Konvertierungen  
 Numerische ganzzahlige Typen und Gleitkommatypen können zusammen in einem Ausdruck verwendet werden.  In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.  Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:  
  
-   Wenn einer der Gleitkommatypen [double](../../../csharp/language-reference/keywords/double.md) lautet, wird der Ausdruck als [double](../../../csharp/language-reference/keywords/double.md) bzw. bei relationalen oder booleschen Ausdrücken als [bool](../../../csharp/language-reference/keywords/bool.md) ausgewertet.  
  
-   Wenn der Ausdruck keinen [double](../../../csharp/language-reference/keywords/double.md)\-Typ enthält, wird er als `float` bzw. bei relationalen oder booleschen Ausdrücken als [bool](../../../csharp/language-reference/keywords/bool.md) ausgewertet.  
  
 Ein Gleitkommaausdruck kann die folgenden Wertgruppen enthalten:  
  
-   Positive und negative 0 \(Null\)  
  
-   Positive und negative Unendlichkeit  
  
-   NaN \(Not a Number\)\-Wert  
  
-   Endliche Gruppe von Werten ungleich null  
  
 Weitere Informationen zu diesen Werten finden Sie im IEEE\-Standard für binäre Gleitkommaarithmetik auf der Website .  
  
## Beispiel  
 Im folgenden Beispiel enthält der mathematische Ausdruck, der ein `float`\-Ergebnis liefert, einen [int](../../../csharp/language-reference/keywords/int.md)\-Wert, einen [short](../../../csharp/language-reference/keywords/short.md)\-Wert und einen `float`\-Wert.  \(Beachten Sie, dass `float` ein Alias für den <xref:System.Single?displayProperty=fullName>\-Typ ist.\) Beachten Sie, dass kein [double](../../../csharp/language-reference/keywords/double.md)\-Wert im Ausdruck enthalten ist.  
  
 [!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Single>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)