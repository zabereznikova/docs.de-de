---
title: 'Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is" (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
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
ms.openlocfilehash: c5daa8525f45c123dabb0f59dfd29385b9e50354
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a>Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is" (C#-Programmierhandbuch)
Da Objekte polymorph sind, ist es möglich, dass eine Variable eines Basisklassentyps einen abgeleiteten Typ enthalten kann. Um auf die Methode des abgeleiteten Typ zuzugreifen, ist es erforderlich, dass Sie den Wert wieder in den abgeleiteten Typ umwandeln. Wenn Sie allerdings in diesen Fällen eine Umwandlung durchführen, besteht das Risiko, dass Sie eine <xref:System.InvalidCastException> auslösen. Deshalb bietet C# die Operatoren [is](../../../csharp/language-reference/keywords/is.md) und [as](../../../csharp/language-reference/keywords/as.md). Sie können diese Operatoren verwenden, um zu prüfen, ob eine Umwandlung erfolgreich durchgeführt werden kann, ohne dass eine Ausnahme ausgelöst wird. Für gewöhnlich ist der `as`-Operator effizienter, da er den Umwandlungswert zurückgibt, wenn die Umwandlung erfolgreich durchgeführt werden kann. Der `is`-Operator gibt einen booleschen Wert zurück. Er kann deshalb verwendet werden, wenn Sie nur den Typ eines Objekts bestimmen wollen, ihn aber nicht tatsächlich umwandeln müssen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie die Operatoren `is` und `as` verwenden können, um einen Verweistyp in einen anderen umzuwandeln, ohne dass das Risiko besteht, dass eine Ausnahme ausgelöst wird. In diesem Beispiel wird auch gezeigt, wie Sie den `as`-Operator mit einem auf NULL festlegbaren Werttyp verwenden können.  
  
 [!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typen](../../../csharp/programming-guide/types/index.md)   
 [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Typen mit Nullwert](../../../csharp/programming-guide/nullable-types/index.md)

