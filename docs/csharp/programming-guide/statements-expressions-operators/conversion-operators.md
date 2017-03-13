---
title: "Konvertierungsoperatoren (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Konvertierungsoperatoren"
  - "Konvertierungsoperatoren [C#]"
  - "Operatoren [C#], Konvertierung"
  - "Benutzerdefinierte Konvertierungen [C#]"
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# Konvertierungsoperatoren (C#-Programmierhandbuch)
C\# bietet Programmierern die Möglichkeit, Konvertierungen für Klassen oder Strukturen zu deklarieren, sodass diese in andere bzw. aus anderen Klassen, Strukturen oder Basistypen konvertiert werden können.  Konvertierungen werden wie Operatoren definiert und nach dem Typ benannt, in den sie konvertiert werden.  Entweder das zu konvertierende Typargument oder der Typ des Ergebnisses der Konvertierung – nicht beides – muss der enthaltende Typ sein.  
  
 [!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## Übersicht über Konvertierungsoperatoren  
 Konvertierungsoperatoren verfügen über die folgenden Eigenschaften:  
  
-   Als `implicit` deklarierte Konvertierungen werden bei Bedarf automatisch vorgenommen.  
  
-   Als `explicit` deklarierte Konvertierungen werden nur bei einer Typumwandlung aufgerufen.  
  
-   Alle Konvertierungen müssen als `static` deklariert werden.  
  
## Verwandte Abschnitte  
 Weitere Informationen:  
  
-   [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [Explizit](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [Implizite](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [Statische](../../../csharp/language-reference/keywords/static.md)  
  
## Siehe auch  
 <xref:System.Convert>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Verkettete benutzerdefinierte explizite Konvertierungen in C\#](http://go.microsoft.com/fwlink/?LinkId=112384)