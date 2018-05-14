---
title: void (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: e66efc287fc3ed0fcc15963a827fccb788c38753
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="void-c-reference"></a>void (C#-Referenz)
Wenn `void` als Rückgabetyp für eine Methode verwendet wird, wird angegeben, dass die Methode keinen Wert zurückgibt.

`void` ist in der Parameterliste einer Methode unzulässig. Eine Methode, mit der keine Parameter übernommen und keine Werte zurückgegeben werden, wird wie folgt deklariert:

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

`void` wird auch in einem unsicheren Kontext verwendet, um einen Zeiger auf einen unbekannten Typ zu deklarieren. Weitere Informationen finden Sie unter [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).

`void` ist ein Alias für den <xref:System.Void?displayProperty=nameWithType>-Typ aus dem .NET Framework.

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)  
 [Werttypen](../../../csharp/language-reference/keywords/value-types.md)  
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
