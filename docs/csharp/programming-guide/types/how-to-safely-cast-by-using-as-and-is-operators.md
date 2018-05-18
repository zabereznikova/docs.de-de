---
title: 'Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is" (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
ms.openlocfilehash: 6e02675a2a895add245d3c2e40305a0417fdf429
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a>Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is" (C#-Programmierhandbuch)
Da Objekte polymorph sind, ist es möglich, dass eine Variable eines Basisklassentyps einen abgeleiteten Typ enthalten kann. Um auf die Methode des abgeleiteten Typ zuzugreifen, ist es erforderlich, dass Sie den Wert wieder in den abgeleiteten Typ umwandeln. Wenn Sie allerdings in diesen Fällen eine Umwandlung durchführen, besteht das Risiko, dass Sie eine <xref:System.InvalidCastException> auslösen. Deshalb bietet C# die Operatoren [is](../../../csharp/language-reference/keywords/is.md) und [as](../../../csharp/language-reference/keywords/as.md). Sie können diese Operatoren verwenden, um zu prüfen, ob eine Umwandlung erfolgreich durchgeführt werden kann, ohne dass eine Ausnahme ausgelöst wird. Für gewöhnlich ist der `as`-Operator effizienter, da er den Umwandlungswert zurückgibt, wenn die Umwandlung erfolgreich durchgeführt werden kann. Der `is`-Operator gibt einen booleschen Wert zurück. Er kann deshalb verwendet werden, wenn Sie nur den Typ eines Objekts bestimmen wollen, ihn aber nicht tatsächlich umwandeln müssen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie die Operatoren `is` und `as` verwenden können, um einen Verweistyp in einen anderen umzuwandeln, ohne dass das Risiko besteht, dass eine Ausnahme ausgelöst wird. In diesem Beispiel wird auch gezeigt, wie Sie den `as`-Operator mit einem auf NULL festlegbaren Werttyp verwenden können.  
  
 [!code-csharp[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typen](../../../csharp/programming-guide/types/index.md)  
 [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [Typen mit Nullwert](../../../csharp/programming-guide/nullable-types/index.md)
