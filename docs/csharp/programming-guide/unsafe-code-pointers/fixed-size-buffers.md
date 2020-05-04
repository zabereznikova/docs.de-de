---
title: Puffer fester Größe – C#-Programmierhandbuch
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 5920dd125ded34969d60feb299568b56402056ab
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140543"
---
# <a name="fixed-size-buffers-c-programming-guide"></a>Puffer fester Größe (C#-Programmierhandbuch)

In C# können Sie die [fixed](../../language-reference/keywords/fixed-statement.md)-Anweisung verwenden, um einen Puffer mit einem Array fester Größe in einer Datenstruktur zu erstellen. Puffer mit fester Größe sind nützlich, wenn Sie Methoden schreiben, die mit Datenquellen aus anderen Sprachen oder Plattformen zusammenarbeiten. Das Array fester Größe kann sämtliche Attribute und Modifizierer, die für reguläre Strukturmember zulässig sind, in Anspruch nehmen. Die einzige Einschränkung besteht darin, dass der Arraytyp `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` oder `double` sein muss.

```csharp
private fixed char name[30];
```

## <a name="remarks"></a>Hinweise

Eine C#-Struktur in sicherem Code, die ein Array enthält, enthält nicht die Elemente des Arrays. Stattdessen enthält die Struktur einen Verweis auf die Elemente. Sie können ein Array mit einer festen Größe in eine [Struktur](../../language-reference/builtin-types/struct.md) einbetten, wenn es in einem [unsicheren](../../language-reference/keywords/unsafe.md) Codeblock verwendet wird.

Die Größe der folgenden `struct` hängt nicht von der Anzahl der Elemente im Array ab, da `pathName` ein Verweis ist:

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

Ein `struct` kann ein eingebettetes Array in unsicheren Code enthalten. Im folgenden Beispiel verfügt das `fixedBuffer`-Array über eine feste Größe. Sie können eine `fixed`-Anweisung verwenden, um einen Zeiger auf das erste Element festzulegen. Über diesen Zeiger können Sie auf die Elemente des Arrays zugreifen. Die `fixed`-Anweisung fixiert das Instanzenfeld `fixedBuffer` an einem bestimmten Speicherort im Arbeitsspeicher.

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

Die Größe des 128-Element-`char`-Arrays beträgt 256 Bytes. [Char](../../language-reference/builtin-types/char.md)-Puffer mit fester Größe verwenden immer zwei Bytes pro Zeichen, unabhängig von der Codierung. Dies gilt auch, wenn Char-Puffer zu API-Methoden oder Strukturen mit `CharSet = CharSet.Auto` oder `CharSet = CharSet.Ansi` gemarshallt werden. Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.CharSet>.

Im obigen Beispiel wird der Zugriff auf `fixed`-Felder ohne Anheften dargestellt – diese Funktionalität ist ab C# 7.3 verfügbar.

Ein anderes häufiges Array mit fester Größe ist das [bool](../../language-reference/builtin-types/bool.md)-Array. Die Elemente in einem `bool`-Array sind immer ein Byte groß. `bool`-Arrays eignen sich nicht zum Erstellen von Bitarrays oder Puffern.

Puffer fester Größe werden mit der <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>-Klasse kompiliert, die die Common Language Runtime (CLR) anweist, dass ein Typ ein nicht verwaltetes Array enthält, das potenziell überlaufen kann. Dies ähnelt der Erstellung von Speicher mithilfe des [stackalloc](../../language-reference/operators/stackalloc.md)-Ausdrucks, der in der CLR automatisch Funktionen zur Pufferüberlauferkennung aktiviert. Im vorherigen Beispiel wird gezeigt, wie ein Puffer fester Größe in einer `unsafe struct`vorhanden sein kann.

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

Der vom Compiler für `Buffer` generierte C#-Code wird wie folgt attributiert:

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

Puffer fester Größe unterscheiden sich folgendermaßen von normalen Arrays:

- Können nur in einem [unsicheren](../../language-reference/keywords/unsafe.md) Kontext verwendet werden
- Können nur Instanzfelder von Strukturen sein
- Sie sind immer Vektoren oder eindimensionale Arrays.
- Die Deklaration sollte die Länge enthalten, z. B. `fixed char id[8]`. Sie können `fixed char id[]` nicht verwenden.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Unsicherer Code und Zeiger](index.md)
- [fixed-Anweisung](../../language-reference/keywords/fixed-statement.md)
- [Interoperabilität](../interop/index.md)
