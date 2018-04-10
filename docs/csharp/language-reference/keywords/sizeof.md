---
title: sizeof (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0148ae8381804ca9286315251582c8ab40778369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="9c26e-102">sizeof (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9c26e-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="9c26e-103">Wird verwendet, um die Größe eines nicht verwalteten Typs in Bytes abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9c26e-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="9c26e-104">Nicht verwaltete Typen umfassen die in der unteren Tabelle aufgelisteten integrierten Typen sowie folgende Typen:</span><span class="sxs-lookup"><span data-stu-id="9c26e-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="9c26e-105">Enumerationstypen</span><span class="sxs-lookup"><span data-stu-id="9c26e-105">Enum types</span></span>  
  
-   <span data-ttu-id="9c26e-106">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="9c26e-106">Pointer types</span></span>  
  
-   <span data-ttu-id="9c26e-107">Benutzerdefinierte Strukturen, die keine Felder oder Eigenschaften enthalten, die Verweistypen sind</span><span class="sxs-lookup"><span data-stu-id="9c26e-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="9c26e-108">Im folgenden Beispiel wird gezeigt, wie Sie die Größe von `int` abrufen:</span><span class="sxs-lookup"><span data-stu-id="9c26e-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="9c26e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c26e-109">Remarks</span></span>  
 <span data-ttu-id="9c26e-110">Ab C# Version 2.0 muss für das Anwenden von `sizeof` auf integrierte Typen nicht länger der Modus [unsafe](../../../csharp/language-reference/keywords/unsafe.md) (unsicher) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c26e-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="9c26e-111">Der Operator `sizeof` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="9c26e-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="9c26e-112">Die Rückgabewerte des Operators `sizeof` sind vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="9c26e-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="9c26e-113">Die folgende Tabelle zeigt die konstanten Werte, die als Ersatz für `sizeof`-Ausdrücke dienen, die über bestimmte integrierte Typen als Operanden verfügen.</span><span class="sxs-lookup"><span data-stu-id="9c26e-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="9c26e-114">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="9c26e-114">Expression</span></span>|<span data-ttu-id="9c26e-115">Konstanter Wert</span><span class="sxs-lookup"><span data-stu-id="9c26e-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="9c26e-116">1</span><span class="sxs-lookup"><span data-stu-id="9c26e-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="9c26e-117">1</span><span class="sxs-lookup"><span data-stu-id="9c26e-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="9c26e-118">2</span><span class="sxs-lookup"><span data-stu-id="9c26e-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="9c26e-119">2</span><span class="sxs-lookup"><span data-stu-id="9c26e-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="9c26e-120">4</span><span class="sxs-lookup"><span data-stu-id="9c26e-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="9c26e-121">4</span><span class="sxs-lookup"><span data-stu-id="9c26e-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="9c26e-122">8</span><span class="sxs-lookup"><span data-stu-id="9c26e-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="9c26e-123">8</span><span class="sxs-lookup"><span data-stu-id="9c26e-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="9c26e-124">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="9c26e-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="9c26e-125">4</span><span class="sxs-lookup"><span data-stu-id="9c26e-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="9c26e-126">8</span><span class="sxs-lookup"><span data-stu-id="9c26e-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="9c26e-127">16</span><span class="sxs-lookup"><span data-stu-id="9c26e-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="9c26e-128">1</span><span class="sxs-lookup"><span data-stu-id="9c26e-128">1</span></span>|  
  
 <span data-ttu-id="9c26e-129">Bei allen anderen Typen, darunter Strukturen, kann der Operator `sizeof` nur in unsicheren Codeblöcken zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="9c26e-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="9c26e-130">Sie können die Methode <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> zwar verwenden, der von dieser Methode zurückgegebene Wert entspricht allerdings nicht immer dem von `sizeof` zurückgegeben Wert.</span><span class="sxs-lookup"><span data-stu-id="9c26e-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="9c26e-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> gibt die Größe nach dem Marshalling des Typs zurück, während `sizeof` die Größe inklusive Abständen zurückgibt, die von der Common Language Runtime zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="9c26e-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c26e-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c26e-132">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="9c26e-133">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9c26e-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9c26e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c26e-134">See Also</span></span>  
 [<span data-ttu-id="9c26e-135">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9c26e-135">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9c26e-136">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9c26e-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9c26e-137">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9c26e-137">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9c26e-138">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9c26e-138">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="9c26e-139">enum</span><span class="sxs-lookup"><span data-stu-id="9c26e-139">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
 [<span data-ttu-id="9c26e-140">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="9c26e-140">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="9c26e-141">Strukturen</span><span class="sxs-lookup"><span data-stu-id="9c26e-141">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [<span data-ttu-id="9c26e-142">Konstanten</span><span class="sxs-lookup"><span data-stu-id="9c26e-142">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)
