---
title: Puffer fester Größe – C#-Programmierhandbuch
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 932ff3d57995ce47c4b74e8e888a479f0d09d0ed
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397427"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="fc410-102">Puffer fester Größe (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fc410-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="fc410-103">In C# können Sie die [fixed](../../language-reference/keywords/fixed-statement.md)-Anweisung verwenden, um einen Puffer mit einem Array fester Größe in einer Datenstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc410-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="fc410-104">Puffer mit fester Größe sind nützlich, wenn Sie Methoden schreiben, die mit Datenquellen aus anderen Sprachen oder Plattformen zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fc410-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="fc410-105">Das Array fester Größe kann sämtliche Attribute und Modifizierer, die für reguläre Strukturmember zulässig sind, in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="fc410-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="fc410-106">Die einzige Einschränkung besteht darin, dass der Arraytyp `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` oder `double` sein muss.</span><span class="sxs-lookup"><span data-stu-id="fc410-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="fc410-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc410-107">Remarks</span></span>

<span data-ttu-id="fc410-108">Eine C#-Struktur in sicherem Code, die ein Array enthält, enthält nicht die Elemente des Arrays.</span><span class="sxs-lookup"><span data-stu-id="fc410-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="fc410-109">Stattdessen enthält die Struktur einen Verweis auf die Elemente.</span><span class="sxs-lookup"><span data-stu-id="fc410-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="fc410-110">Sie können ein Array mit einer festen Größe in eine [Struktur](../../language-reference/builtin-types/struct.md) einbetten, wenn es in einem [unsicheren](../../language-reference/keywords/unsafe.md) Codeblock verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc410-110">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="fc410-111">Die Größe der folgenden `struct` hängt nicht von der Anzahl der Elemente im Array ab, da `pathName` ein Verweis ist:</span><span class="sxs-lookup"><span data-stu-id="fc410-111">Size of the following `struct` doesn't depend on the number of elements in the array, since `pathName` is a reference:</span></span>

[!code-csharp[Struct with embedded array](snippets/FixedKeywordExamples.cs#6)]

<span data-ttu-id="fc410-112">Ein `struct` kann ein eingebettetes Array in unsicheren Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc410-112">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="fc410-113">Im folgenden Beispiel verfügt das `fixedBuffer`-Array über eine feste Größe.</span><span class="sxs-lookup"><span data-stu-id="fc410-113">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="fc410-114">Sie können eine `fixed`-Anweisung verwenden, um einen Zeiger auf das erste Element festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fc410-114">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="fc410-115">Über diesen Zeiger können Sie auf die Elemente des Arrays zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fc410-115">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="fc410-116">Die `fixed`-Anweisung fixiert das Instanzenfeld `fixedBuffer` an einem bestimmten Speicherort im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="fc410-116">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#7)]

<span data-ttu-id="fc410-117">Die Größe des 128-Element-`char`-Arrays beträgt 256 Bytes.</span><span class="sxs-lookup"><span data-stu-id="fc410-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="fc410-118">[Char](../../language-reference/builtin-types/char.md)-Puffer mit fester Größe verwenden immer zwei Bytes pro Zeichen, unabhängig von der Codierung.</span><span class="sxs-lookup"><span data-stu-id="fc410-118">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="fc410-119">Dies gilt auch, wenn Char-Puffer zu API-Methoden oder Strukturen mit `CharSet = CharSet.Auto` oder `CharSet = CharSet.Ansi` gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="fc410-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="fc410-120">Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="fc410-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="fc410-121">Im obigen Beispiel wird der Zugriff auf `fixed`-Felder ohne Anheften dargestellt – diese Funktionalität ist ab C# 7.3 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fc410-121">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="fc410-122">Ein anderes häufiges Array mit fester Größe ist das [bool](../../language-reference/builtin-types/bool.md)-Array.</span><span class="sxs-lookup"><span data-stu-id="fc410-122">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="fc410-123">Die Elemente in einem `bool`-Array sind immer ein Byte groß.</span><span class="sxs-lookup"><span data-stu-id="fc410-123">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="fc410-124">`bool`-Arrays eignen sich nicht zum Erstellen von Bitarrays oder Puffern.</span><span class="sxs-lookup"><span data-stu-id="fc410-124">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

<span data-ttu-id="fc410-125">Puffer fester Größe werden mit der <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>-Klasse kompiliert, die die Common Language Runtime (CLR) anweist, dass ein Typ ein nicht verwaltetes Array enthält, das potenziell überlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="fc410-125">Fixed size buffers are compiled with the <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, which instructs the common language runtime (CLR) that a type contains an unmanaged array that can potentially overflow.</span></span> <span data-ttu-id="fc410-126">Dies ähnelt der Erstellung von Speicher mithilfe des [stackalloc](../../language-reference/operators/stackalloc.md)-Ausdrucks, der in der CLR automatisch Funktionen zur Pufferüberlauferkennung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fc410-126">This is similar to memory created using [stackalloc](../../language-reference/operators/stackalloc.md), which automatically enables buffer overrun detection features in the CLR.</span></span> <span data-ttu-id="fc410-127">Im vorherigen Beispiel wird gezeigt, wie ein Puffer fester Größe in einer `unsafe struct`vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="fc410-127">The previous example shows how a fixed size buffer could exist in an `unsafe struct`.</span></span>

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

<span data-ttu-id="fc410-128">Der vom Compiler für `Buffer` generierte C#-Code wird wie folgt attributiert:</span><span class="sxs-lookup"><span data-stu-id="fc410-128">The compiler generated C# for `Buffer`, is attributed as follows:</span></span>

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

<span data-ttu-id="fc410-129">Puffer fester Größe unterscheiden sich folgendermaßen von normalen Arrays:</span><span class="sxs-lookup"><span data-stu-id="fc410-129">Fixed size buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="fc410-130">Können nur in einem [unsicheren](../../language-reference/keywords/unsafe.md) Kontext verwendet werden</span><span class="sxs-lookup"><span data-stu-id="fc410-130">May only be used in an [unsafe](../../language-reference/keywords/unsafe.md) context.</span></span>
- <span data-ttu-id="fc410-131">Können nur Instanzfelder von Strukturen sein</span><span class="sxs-lookup"><span data-stu-id="fc410-131">May only be instance fields of structs.</span></span>
- <span data-ttu-id="fc410-132">Sie sind immer Vektoren oder eindimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="fc410-132">They're always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="fc410-133">Die Deklaration sollte die Länge enthalten, z. B. `fixed char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="fc410-133">The declaration should include the length, such as `fixed char id[8]`.</span></span> <span data-ttu-id="fc410-134">Sie können `fixed char id[]` nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc410-134">You cannot use `fixed char id[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc410-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc410-135">See also</span></span>

- [<span data-ttu-id="fc410-136">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fc410-136">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fc410-137">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="fc410-137">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="fc410-138">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fc410-138">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="fc410-139">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="fc410-139">Interoperability</span></span>](../interop/index.md)
