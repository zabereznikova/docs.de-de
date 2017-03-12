---
title: "Verweistypen (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.referencetypes"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Verweistypen"
  - "Verweistypen [C#]"
  - "Typen [C#], Verweistypen"
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Verweistypen (C#-Referenz)
Es gibt zwei Arten von Typen in C\#: Verweistypen und Werttypen.  Variablen von Verweistypen speichern Verweise auf ihre Daten \(Objekte\), während Variablen von Werttypen ihre Daten direkt enthalten.  Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.  Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen \(außer im Fall von ref\-Parametervariablen und out\-Parametervariablen, siehe [ref](../../../csharp/language-reference/keywords/ref.md) und [Modifizierer für out\-Parameter](../../../csharp/language-reference/keywords/out-parameter-modifier.md)\).  
  
 Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:  
  
-   [class](../../../csharp/language-reference/keywords/class.md)  
  
-   [interface](../../../csharp/language-reference/keywords/interface.md)  
  
-   [delegate](../../../csharp/language-reference/keywords/delegate.md)  
  
 C\# enthält auch die folgenden integrierten Referenztypen:  
  
-   [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [object](../../../csharp/language-reference/keywords/object.md)  
  
-   [string](../../../csharp/language-reference/keywords/string.md)  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [Werttypen](../../../csharp/language-reference/keywords/value-types.md)