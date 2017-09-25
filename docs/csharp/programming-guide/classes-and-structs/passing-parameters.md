---
title: "Übergeben von Parametern (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4b8c0c7f7b8c3820edbafbe90fb961c12da8fc84
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="passing-parameters-c-programming-guide"></a>Übergeben von Parametern (C#-Programmierhandbuch)
In C# können Argumente an Parameter entweder als Wert oder als Verweis übergeben werden. Durch die Übergabe als Verweis können Funktionsmember, Methoden, Eigenschaften, Indexer, Operatoren und Konstruktoren den Wert der Parameter ändern und behalten diese Änderung in der aufrufenden Umgebung bei. Verwenden Sie das Schlüsselwort `ref` oder `out`, um einen Parameter als Verweis zu übergeben. Der Einfachheit halber wird in den Beispielen in diesem Thema nur das Schlüsselwort `ref` verwendet. Weitere Informationen zu den Unterschieden zwischen `ref` und `out` finden Sie unter [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) sowie [Übergeben von Arrays mithilfe von „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Das folgende Beispiel veranschaulicht die Unterschiede zwischen Wert- und Verweisparametern.  
  
 [!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Übergeben von Werttypparametern](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [Übergeben von Verweistypparametern](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)

