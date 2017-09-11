---
title: "Puffer fester Größe (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e1a3dcf953cb56fc3436fdd5e7ecb60478a12922
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="7cea7-102">Puffer fester Größe (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7cea7-102">Fixed Size Buffers (C# Programming Guide)</span></span>
<span data-ttu-id="7cea7-103">In C# können Sie die [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)-Anweisung verwenden, um einen Puffer mit einem Array fester Größe in einer Datenstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7cea7-103">In C#, you can use the [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="7cea7-104">Dies ist hilfreich, wenn Sie mit vorhandenem Code, z.B. Code in anderen Sprachen, bereits vorhandenen DLLs oder COM-Projekten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7cea7-104">This is useful when you are working with existing code, such as code written in other languages, pre-existing DLLs or COM projects.</span></span> <span data-ttu-id="7cea7-105">Das Array fester Größe kann sämtliche Attribute und Modifizierer, die für reguläre Strukturmember zulässig sind, in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="7cea7-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="7cea7-106">Die einzige Einschränkung besteht darin, dass der Arraytyp `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` oder `double` sein muss.</span><span class="sxs-lookup"><span data-stu-id="7cea7-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a><span data-ttu-id="7cea7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cea7-107">Remarks</span></span>  
 <span data-ttu-id="7cea7-108">In frühen Versionen von C# war das Deklarieren einer C++-Struktur mit fester Größe schwierig, da eine C#-Struktur, die ein Array enthält, keine Elemente des Arrays enthält.</span><span class="sxs-lookup"><span data-stu-id="7cea7-108">In early versions of C#, declaring a C++ style fixed-size structure was difficult because a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="7cea7-109">Stattdessen enthält die Struktur einen Verweis auf die Elemente.</span><span class="sxs-lookup"><span data-stu-id="7cea7-109">Instead, the struct contains a reference to the elements.</span></span>  
  
 <span data-ttu-id="7cea7-110">C# 2.0 hat die Möglichkeit hinzugefügt, ein Array fester Größe in ein [struct](../../../csharp/language-reference/keywords/struct.md) einzubetten, wenn es in einem [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Codeblock verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7cea7-110">C# 2.0 added the ability to embed an array of fixed size in a [struct](../../../csharp/language-reference/keywords/struct.md) when it is used in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) code block.</span></span>  
  
 <span data-ttu-id="7cea7-111">Vor C# 2.0 wäre das folgende `struct` z.B. 8 Bytes groß.</span><span class="sxs-lookup"><span data-stu-id="7cea7-111">For example, before C# 2.0, the following `struct` would be 8 bytes in size.</span></span> <span data-ttu-id="7cea7-112">Das `pathName`-Array ist ein Verweis auf das Heap zugeordnete Array:</span><span class="sxs-lookup"><span data-stu-id="7cea7-112">The `pathName` array is a reference to the heap-allocated array:</span></span>  
  
 <span data-ttu-id="7cea7-113">[!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7cea7-113">[!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]</span></span>  
  
 <span data-ttu-id="7cea7-114">Beginnend mit C# 2.0 kann ein `struct` ein eingebettetes Array enthalten.</span><span class="sxs-lookup"><span data-stu-id="7cea7-114">Beginning with C# 2.0, a `struct` can contain an embedded array.</span></span> <span data-ttu-id="7cea7-115">Im folgenden Beispiel verfügt das `fixedBuffer`-Array über eine feste Größe.</span><span class="sxs-lookup"><span data-stu-id="7cea7-115">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="7cea7-116">Um auf die Elemente des Arrays zuzugreifen, verwenden Sie eine `fixed`-Anweisung, um einen Zeiger auf das erste Element festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7cea7-116">To access the elements of the array, you use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="7cea7-117">Die `fixed`-Anweisung fixiert eine Instanz von `fixedBuffer` an einem bestimmten Speicherort im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="7cea7-117">The `fixed` statement pins an instance of `fixedBuffer` to a specific location in memory.</span></span>  
  
 <span data-ttu-id="7cea7-118">[!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7cea7-118">[!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]</span></span>  
  
 <span data-ttu-id="7cea7-119">Die Größe des 128-Element-`char`-Arrays beträgt 256 Bytes.</span><span class="sxs-lookup"><span data-stu-id="7cea7-119">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="7cea7-120">[Char](../../../csharp/language-reference/keywords/char.md)-Puffer mit fester Größe verwenden immer zwei Bytes pro Zeichen, unabhängig von der Codierung.</span><span class="sxs-lookup"><span data-stu-id="7cea7-120">Fixed size [char](../../../csharp/language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="7cea7-121">Dies gilt auch, wenn Char-Puffer zu API-Methoden oder Strukturen mit `CharSet = CharSet.Auto` oder `CharSet = CharSet.Ansi` gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="7cea7-121">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="7cea7-122">Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="7cea7-122">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>  
  
 <span data-ttu-id="7cea7-123">Ein anderes häufiges Array mit fester Größe ist das [bool](../../../csharp/language-reference/keywords/bool.md)-Array.</span><span class="sxs-lookup"><span data-stu-id="7cea7-123">Another common fixed-size array is the [bool](../../../csharp/language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="7cea7-124">Die Elemente in einem `bool`-Array sind immer ein Byte groß.</span><span class="sxs-lookup"><span data-stu-id="7cea7-124">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="7cea7-125">`bool`-Arrays eignen sich nicht zum Erstellen von Bitarrays oder Puffern.</span><span class="sxs-lookup"><span data-stu-id="7cea7-125">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cea7-126">Mit Ausnahme von Arbeitsspeicher, der mithilfe von [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md) erstellt wurde, führen der C#-Compiler und die Common Language Runtime (CLR) keine Sicherheitsüberprüfungen für Pufferüberlauf aus.</span><span class="sxs-lookup"><span data-stu-id="7cea7-126">Except for memory created by using [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="7cea7-127">Lassen Sie, wie bei jedem unsicheren Code, Vorsicht walten.</span><span class="sxs-lookup"><span data-stu-id="7cea7-127">As with all unsafe code, use caution.</span></span>  
  
 <span data-ttu-id="7cea7-128">Unsichere Puffer unterscheiden sich folgendermaßen von normalen Arrays:</span><span class="sxs-lookup"><span data-stu-id="7cea7-128">Unsafe buffers differ from regular arrays in the following ways:</span></span>  
  
-   <span data-ttu-id="7cea7-129">Sie können nur in einem unsicheren Kontext unsichere Puffer verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cea7-129">You can only use unsafe buffers in an unsafe context.</span></span>  
  
-   <span data-ttu-id="7cea7-130">Unsichere Puffer sind immer Vektoren oder eindimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="7cea7-130">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>  
  
-   <span data-ttu-id="7cea7-131">Die Deklaration des Arrays muss eine Anzahl enthalten, z.B. `char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="7cea7-131">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="7cea7-132">Sie können stattdessen nicht `char id[]` verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cea7-132">You cannot use `char id[]` instead.</span></span>  
  
-   <span data-ttu-id="7cea7-133">Unsichere Puffer können nur Instanzfelder von Strukturen in einem unsicheren Kontext sein.</span><span class="sxs-lookup"><span data-stu-id="7cea7-133">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cea7-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cea7-134">See Also</span></span>  
 <span data-ttu-id="7cea7-135">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7cea7-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7cea7-136">[Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="7cea7-136">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="7cea7-137">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7cea7-137">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="7cea7-138">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="7cea7-138">Interoperability</span></span>](../../../csharp/programming-guide/interop/index.md)

