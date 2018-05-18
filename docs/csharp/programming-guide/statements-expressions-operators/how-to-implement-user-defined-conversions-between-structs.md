---
title: 'Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: 178d9e2f92c5c1989253a16d866052a1fc42c10e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch)
Dieses Beispiel definiert zwei Strukturen, `RomanNumeral` und `BinaryNumeral`, und zeigt Konvertierungen zwischen diesen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
-   Im vorherigen Beispiel führt die Anweisung  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     führt eine Konvertierung von `RomanNumeral` zu `BinaryNumeral` durch. Da es keine direkte Konvertierung von `RomanNumeral` zu `BinaryNumeral` gibt, wird eine Umwandlung für die Konvertierung von `RomanNumeral` zu `int` verwendet, und eine weitere Umwandlung zum Konvertieren von `int` zu `BinaryNumeral`.  
  
-   Die Anweisung  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     führt eine Konvertierung von `BinaryNumeral` zu `RomanNumeral` durch. Da `RomanNumeral` eine implizierte Konvertierung von `BinaryNumeral` definiert, ist keine Umwandlung erforderlich.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
