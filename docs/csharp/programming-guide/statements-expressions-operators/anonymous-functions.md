---
title: Anonyme Funktionen (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 51a3c2e8399fdaae19ebe33f0d9ecc4bfd598799
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="anonymous-functions-c-programming-guide"></a>Anonyme Funktionen (C#-Programmierhandbuch)
Eine anonyme Funktion ist eine „Inline“-Anweisung oder ein „Inline“-Ausdruck, der überall dort verwendet werden kann, wo ein Delegattyp erwartet wird. Sie können sie zum Initialisieren eines benannten Delegaten verwenden oder anstelle eines benannten Delegattypen als Methodenparameter übergeben.  
  
 Es gibt zwei Arten von anonymen Funktionen, die in den folgenden Themen einzeln erläutert werden:  
  
-   [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Lambdaausdrücke können an Ausdrucksstrukturen und an Delegaten gebunden werden.  
  
## <a name="the-evolution-of-delegates-in-c"></a>Entwicklung von Delegaten in C#  
 In C# 1.0 haben Sie eine Instanz eines Delegaten durch explizites Initialisieren mit einer Methode erstellt, die an anderer Stelle im Code definiert wurde. C# 2.0 führte das Konzept anonymer Methoden ein, als eine Möglichkeit, unbenannte Inline-Anweisungsblöcke zu schreiben, die in einem Delegataufruf ausgeführt werden können. C# 3.0 führte Lambdaausdrücke ein, die anonymen Methoden ähneln, jedoch aussagekräftiger und präziser sind. Diese beiden Funktionen werden zusammenfassend als *anonyme Funktionen* bezeichnet. In der Regel sollten Anwendungen, die für [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Version 3.5 und höher gedacht sind, Lambdaausdrücke verwenden.  
  
 Das folgende Beispiel zeigt die Entwicklung der Delegaterstellung von C# 1.0 zu C# 3.0:  
  
 [!code-csharp[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen, Ausdrücke und Operatoren](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
 [Lambda-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)  
 [Ausdrucksbaumstrukturen](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)
