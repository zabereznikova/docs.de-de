---
title: unsafe-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: ef98809eae0329c028dfb318c4a437aae4736db1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712987"
---
# <a name="unsafe-c-reference"></a>unsafe (C#-Referenz)

Das Schlüsselwort `unsafe` kennzeichnet einen unsicheren Kontext, der für alle Zeigeroperationen erforderlich ist. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).

Sie können bei der Deklaration eines Typs oder Members den Modifizierer `unsafe` verwenden. Daraufhin wird der gesamte Text des Typs oder Members als unsicherer Kontext angesehen. Hier sehen Sie eine Methode, die mit dem Modifizierer `unsafe` deklariert wurde:

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

Der unsichere Kontext erstreckt sich von der Parameterliste bis zum Ende der Methode, weshalb in der Parameterliste auch Zeiger verwendet werden können:

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

Sie können auch einen unsafe-Block verwenden, um die Verwendung von unsicherem Code in diesem Block zu aktivieren. Beispiel:

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

Um unsicheren Code kompilieren zu können, müssen Sie die Compileroption [`-unsafe`](../compiler-options/unsafe-compiler-option.md) angeben. Unsicherer Code kann nicht von der Common Language Runtime überprüft werden.

## <a name="example"></a>Beispiel

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [Unsafe-Code](~/_csharplang/spec/unsafe-code.md) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [fixed-Anweisung](fixed-statement.md)
- [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md)
- [Puffer fester Größe](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
