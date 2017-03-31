---
title: Anonyme Funktionen (C#-Programmierhandbuch) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 465097f9e7024ecfa96ecacb3f4377f3e6a44d13
ms.lasthandoff: 03/13/2017

---
# <a name="anonymous-functions-c-programming-guide"></a>Anonyme Funktionen (C#-Programmierhandbuch)
Eine anonyme Funktion ist eine „Inline“-Anweisung oder ein „Inline“-Ausdruck, der überall dort verwendet werden kann, wo ein Delegattyp erwartet wird. Sie können sie zum Initialisieren eines benannten Delegaten verwenden oder anstelle eines benannten Delegattypen als Methodenparameter übergeben.  
  
 Es gibt zwei Arten von anonymen Funktionen, die in den folgenden Themen einzeln erläutert werden:  
  
-   [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Lambdaausdrücke können an Ausdrucksstrukturen und an Delegaten gebunden werden.  
  
## <a name="the-evolution-of-delegates-in-c"></a>Die Entwicklung von Delegaten in C#  
 In C# 1.0 haben Sie eine Instanz eines Delegaten durch explizites Initialisieren mit einer Methode erstellt, die an anderer Stelle im Code definiert wurde. C# 2.0 führte das Konzept anonymer Methoden ein, als eine Möglichkeit, unbenannte Inline-Anweisungsblöcke zu schreiben, die in einem Delegataufruf ausgeführt werden können. C# 3.0 führte Lambdaausdrücke ein, die anonymen Methoden ähneln, jedoch aussagekräftiger und präziser sind. Diese beiden Funktionen werden zusammenfassend als *anonyme Funktionen* bezeichnet. In der Regel sollten Anwendungen, die für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]-Version 3.5 und höher gedacht sind, Lambdaausdrücke verwenden.  
  
 Das folgende Beispiel zeigt die Entwicklung der Delegaterstellung von C# 1.0 zu C# 3.0:  
  
 [!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen, Ausdrücke und Operatoren](../../../csharp/programming-guide/statements-expressions-operators/index.md)   
 [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Ausdrucksbaumstrukturen](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)
