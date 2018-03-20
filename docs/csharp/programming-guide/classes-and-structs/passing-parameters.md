---
title: "Übergeben von Parametern (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 34746c83f54ecc2f6e8125bcff1464a89f853e09
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="passing-parameters-c-programming-guide"></a>Übergeben von Parametern (C#-Programmierhandbuch)
In C# können Argumente an Parameter entweder als Wert oder als Verweis übergeben werden. Durch die Übergabe als Verweis können Funktionsmember, Methoden, Eigenschaften, Indexer, Operatoren und Konstruktoren den Wert der Parameter ändern und behalten diese Änderung in der aufrufenden Umgebung bei. Wenn Sie den Wert ändern und darum den Parameter pro Verweis übergeben möchten, verwenden Sie die Schlüsselwörter `ref` oder `out`. Wenn Sie den Wert zwar ändern, aber keine Kopie erstellen möchten, und darum den Parameter pro Verweis übergeben möchten, verwenden Sie den Modifizierer `in`. Der Einfachheit halber wird in den Beispielen in diesem Thema nur das Schlüsselwort `ref` verwendet. Weitere Informationen zu den Unterschieden zwischen `in`, `ref` und `out` finden Sie unter [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) und [Übergeben von Arrays mithilfe von „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Das folgende Beispiel veranschaulicht die Unterschiede zwischen Wert- und Verweisparametern.  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Übergeben von Werttypparametern](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [Übergeben von Verweistypparametern](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)
