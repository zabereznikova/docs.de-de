---
title: 'Gewusst wie: Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 6d334459b0d530ec37925c98abfd061c04ce1290
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485650"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a>Gewusst wie: Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)
In einem unsicheren Kontext können Sie mittels Zeigerelementzugriff auf ein Element im Speicher zugreifen, wie im folgenden Beispiel gezeigt:  
  
```csharp  
char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 Der Ausdruck in eckigen Klammern muss implizit in `int`, `uint`, `long` oder `ulong` konvertierbar sein. Der Vorgang p[e] entspricht *(p+e). Wie in C und C++ überprüft der Zeigerelementzugriff keine Fehler außerhalb des gültigen Bereichs.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden einem Zeichenarray, `charPointer`, 123 Speicheradressen zugeordnet. Das Array wird verwendet, um die Klein- und Großbuchstaben in zwei [for](../../../csharp/language-reference/keywords/for.md)-Schleifen anzuzeigen.  
  
 Beachten Sie, dass der Ausdruck `charPointer[i]` und der Ausdruck `*(charPointer + i)` äquivalent sind. Sie erhalten dasselbe Ergebnis, unabhängig davon, welchen Ausdruck Sie verwenden.  
  
 [!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
 **Großbuchstaben:**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**Kleinbuchstaben:**  
**abcdefghijklmnopqrstuvwxyz**   
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Typen](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
