---
title: sizeof – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: a00c4f96e62f7fd7d7c352aece097acd5b600ae2
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422394"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="25ed2-102">sizeof (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="25ed2-102">sizeof (C# Reference)</span></span>

<span data-ttu-id="25ed2-103">Wird verwendet, um die Größe eines nicht verwalteten Typs in Bytes abzurufen.</span><span class="sxs-lookup"><span data-stu-id="25ed2-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="25ed2-104">Zu nicht verwalteten Typen zählen die folgenden:</span><span class="sxs-lookup"><span data-stu-id="25ed2-104">Unmanaged types include:</span></span>

- <span data-ttu-id="25ed2-105">Die einfachen Typen, die in der folgenden Tabelle aufgelistet werden:</span><span class="sxs-lookup"><span data-stu-id="25ed2-105">The simple types that are listed in the following table:</span></span>

   |<span data-ttu-id="25ed2-106">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="25ed2-106">Expression</span></span>|<span data-ttu-id="25ed2-107">Konstanter Wert</span><span class="sxs-lookup"><span data-stu-id="25ed2-107">Constant value</span></span>|
   |----------------|--------------------|
   |`sizeof(sbyte)`|<span data-ttu-id="25ed2-108">1</span><span class="sxs-lookup"><span data-stu-id="25ed2-108">1</span></span>|
   |`sizeof(byte)`|<span data-ttu-id="25ed2-109">1</span><span class="sxs-lookup"><span data-stu-id="25ed2-109">1</span></span>|
   |`sizeof(short)`|<span data-ttu-id="25ed2-110">2</span><span class="sxs-lookup"><span data-stu-id="25ed2-110">2</span></span>|
   |`sizeof(ushort)`|<span data-ttu-id="25ed2-111">2</span><span class="sxs-lookup"><span data-stu-id="25ed2-111">2</span></span>|
   |`sizeof(int)`|<span data-ttu-id="25ed2-112">4</span><span class="sxs-lookup"><span data-stu-id="25ed2-112">4</span></span>|
   |`sizeof(uint)`|<span data-ttu-id="25ed2-113">4</span><span class="sxs-lookup"><span data-stu-id="25ed2-113">4</span></span>|
   |`sizeof(long)`|<span data-ttu-id="25ed2-114">8</span><span class="sxs-lookup"><span data-stu-id="25ed2-114">8</span></span>|
   |`sizeof(ulong)`|<span data-ttu-id="25ed2-115">8</span><span class="sxs-lookup"><span data-stu-id="25ed2-115">8</span></span>|
   |`sizeof(char)`|<span data-ttu-id="25ed2-116">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="25ed2-116">2 (Unicode)</span></span>|
   |`sizeof(float)`|<span data-ttu-id="25ed2-117">4</span><span class="sxs-lookup"><span data-stu-id="25ed2-117">4</span></span>|
   |`sizeof(double)`|<span data-ttu-id="25ed2-118">8</span><span class="sxs-lookup"><span data-stu-id="25ed2-118">8</span></span>|
   |`sizeof(decimal)`|<span data-ttu-id="25ed2-119">16</span><span class="sxs-lookup"><span data-stu-id="25ed2-119">16</span></span>|
   |`sizeof(bool)`|<span data-ttu-id="25ed2-120">1</span><span class="sxs-lookup"><span data-stu-id="25ed2-120">1</span></span>|

- <span data-ttu-id="25ed2-121">Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="25ed2-121">Enum types.</span></span>

- <span data-ttu-id="25ed2-122">Zeigertypen.</span><span class="sxs-lookup"><span data-stu-id="25ed2-122">Pointer types.</span></span>

- <span data-ttu-id="25ed2-123">Benutzerdefinierte Strukturen, die keine Instanzenfelder oder automatisch implementierten Instanzeigenschaften enthalten, bei denen es sich um Verweistypen oder konstruierte Typen handelt.</span><span class="sxs-lookup"><span data-stu-id="25ed2-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>

<span data-ttu-id="25ed2-124">Im folgenden Beispiel wird gezeigt, wie Sie die Größe von `int` abrufen:</span><span class="sxs-lookup"><span data-stu-id="25ed2-124">The following example shows how to retrieve the size of an `int`:</span></span>

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a><span data-ttu-id="25ed2-125">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="25ed2-125">Remarks</span></span>

<span data-ttu-id="25ed2-126">Ab C# Version 2.0 ist für die Anwendung von `sizeof` auf einfache Typen oder Enumerationstypen nicht mehr erforderlich, dass Code in [unsicherem](unsafe.md) Kontext kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="25ed2-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>

<span data-ttu-id="25ed2-127">Operator `sizeof` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="25ed2-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="25ed2-128">Die Rückgabewerte des Operators `sizeof` sind vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="25ed2-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="25ed2-129">Die vorherige Tabelle zeigt die konstanten Werte, die als Ersatz für `sizeof`-Ausdrücke dienen, die über bestimmte einfache Typen als Operanden verfügen.</span><span class="sxs-lookup"><span data-stu-id="25ed2-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>

<span data-ttu-id="25ed2-130">Bei allen anderen Typen, darunter Strukturen, kann der Operator `sizeof` nur in unsicheren Codeblöcken zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="25ed2-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="25ed2-131">Sie können die Methode <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> zwar verwenden, der von dieser Methode zurückgegebene Wert entspricht allerdings nicht immer dem von `sizeof` zurückgegeben Wert.</span><span class="sxs-lookup"><span data-stu-id="25ed2-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="25ed2-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> gibt die Größe nach dem Marshalling des Typs zurück, während `sizeof` die Größe inklusive Abständen zurückgibt, die von der Common Language Runtime zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="25ed2-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>

## <a name="example"></a><span data-ttu-id="25ed2-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25ed2-133">Example</span></span>

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a><span data-ttu-id="25ed2-134">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="25ed2-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="25ed2-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25ed2-135">See also</span></span>

- [<span data-ttu-id="25ed2-136">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="25ed2-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="25ed2-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="25ed2-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="25ed2-138">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25ed2-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="25ed2-139">enum</span><span class="sxs-lookup"><span data-stu-id="25ed2-139">enum</span></span>](enum.md)
- [<span data-ttu-id="25ed2-140">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="25ed2-140">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="25ed2-141">Strukturen</span><span class="sxs-lookup"><span data-stu-id="25ed2-141">Structs</span></span>](../../programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="25ed2-142">Konstanten</span><span class="sxs-lookup"><span data-stu-id="25ed2-142">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)
