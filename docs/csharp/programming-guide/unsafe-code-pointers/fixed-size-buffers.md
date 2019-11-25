---
title: Puffer fester Größe – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 33af43a69587ffaadd7fcb42fa1d30ee9fc41989
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429400"
---
# <a name="fixed-size-buffers-c-programming-guide"></a>Puffer fester Größe (C#-Programmierhandbuch)

In C# können Sie die [fixed](../../language-reference/keywords/fixed-statement.md)-Anweisung verwenden, um einen Puffer mit einem Array fester Größe in einer Datenstruktur zu erstellen. Puffer mit fester Größe sind nützlich, wenn Sie Methoden schreiben, die mit Datenquellen aus anderen Sprachen oder Plattformen zusammenarbeiten. Das Array fester Größe kann sämtliche Attribute und Modifizierer, die für reguläre Strukturmember zulässig sind, in Anspruch nehmen. Die einzige Einschränkung besteht darin, dass der Arraytyp `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` oder `double` sein muss.

```csharp
private fixed char name[30];
```

## <a name="remarks"></a>Hinweise

Eine C#-Struktur in sicherem Code, die ein Array enthält, enthält nicht die Elemente des Arrays. Stattdessen enthält die Struktur einen Verweis auf die Elemente. Sie können ein Array mit einer festen Größe in eine [Struktur](../../language-reference/keywords/struct.md) einbetten, wenn es in einem [unsicheren](../../language-reference/keywords/unsafe.md) Codeblock verwendet wird.

Das folgende `struct` ist 8 Byte groß. Das `pathName`-Array ist ein Verweis:

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

Ein `struct` kann ein eingebettetes Array in unsicheren Code enthalten. Im folgenden Beispiel verfügt das `fixedBuffer`-Array über eine feste Größe. Sie können eine `fixed`-Anweisung verwenden, um einen Zeiger auf das erste Element festzulegen. Über diesen Zeiger können Sie auf die Elemente des Arrays zugreifen. Die `fixed`-Anweisung fixiert das Instanzenfeld `fixedBuffer` an einem bestimmten Speicherort im Arbeitsspeicher.

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

Die Größe des 128-Element-`char`-Arrays beträgt 256 Bytes. [Char](../../language-reference/builtin-types/char.md)-Puffer mit fester Größe verwenden immer zwei Bytes pro Zeichen, unabhängig von der Codierung. Dies gilt auch, wenn Char-Puffer zu API-Methoden oder Strukturen mit `CharSet = CharSet.Auto` oder `CharSet = CharSet.Ansi` gemarshallt werden. Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.CharSet>.

Im obigen Beispiel wird der Zugriff auf `fixed`-Felder ohne Anheften dargestellt – diese Funktionalität ist ab C# 7.3 verfügbar.

Ein anderes häufiges Array mit fester Größe ist das [bool](../../language-reference/keywords/bool.md)-Array. Die Elemente in einem `bool`-Array sind immer ein Byte groß. `bool`-Arrays eignen sich nicht zum Erstellen von Bitarrays oder Puffern.

> [!NOTE]
> Mit Ausnahme von Arbeitsspeicher, der mithilfe von [stackalloc](../../language-reference/operators/stackalloc.md) erstellt wurde, führen der C#-Compiler und die Common Language Runtime (CLR) keine Sicherheitsüberprüfungen für Pufferüberlauf aus. Lassen Sie, wie bei jedem unsicheren Code, Vorsicht walten.

Unsichere Puffer unterscheiden sich folgendermaßen von normalen Arrays:

- Sie können nur in einem unsicheren Kontext unsichere Puffer verwenden.
- Unsichere Puffer sind immer Vektoren oder eindimensionale Arrays.
- Die Deklaration des Arrays muss eine Anzahl enthalten, z.B. `char id[8]`. Sie können `char id[]` nicht verwenden.
- Unsichere Puffer können nur Instanzfelder von Strukturen in einem unsicheren Kontext sein.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Unsicherer Code und Zeiger](index.md)
- [fixed-Anweisung](../../language-reference/keywords/fixed-statement.md)
- [Interoperabilität](../interop/index.md)
