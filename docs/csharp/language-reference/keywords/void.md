---
title: void – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: af79d39282ea38811777ea1f23054120afc39d2c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632956"
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

`void` wird auch in einem unsicheren Kontext verwendet, um einen Zeiger auf einen unbekannten Typ zu deklarieren. Weitere Informationen finden Sie unter [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md).

`void` ist ein Alias für den <xref:System.Void?displayProperty=nameWithType>-Typ aus dem .NET Framework.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Verweistypen](reference-types.md)
- [Werttypen](value-types.md)
- [Methoden](../../programming-guide/classes-and-structs/methods.md)
- [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md)
