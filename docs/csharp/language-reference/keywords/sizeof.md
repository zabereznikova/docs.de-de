---
title: sizeof (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: f2507dd8528e2e66016524873ada890227a74ed8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43487194"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="ddd32-102">sizeof (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ddd32-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="ddd32-103">Wird verwendet, um die Größe eines nicht verwalteten Typs in Bytes abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ddd32-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="ddd32-104">Zu nicht verwalteten Typen zählen die folgenden:</span><span class="sxs-lookup"><span data-stu-id="ddd32-104">Unmanaged types include:</span></span>

-   <span data-ttu-id="ddd32-105">Die einfachen Typen, die in der folgenden Tabelle aufgelistet werden:</span><span class="sxs-lookup"><span data-stu-id="ddd32-105">The simple types that are listed in the following table:</span></span>
  
   |<span data-ttu-id="ddd32-106">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="ddd32-106">Expression</span></span>|<span data-ttu-id="ddd32-107">Konstanter Wert</span><span class="sxs-lookup"><span data-stu-id="ddd32-107">Constant value</span></span>|  
   |----------------|--------------------|  
   |`sizeof(sbyte)`|<span data-ttu-id="ddd32-108">1</span><span class="sxs-lookup"><span data-stu-id="ddd32-108">1</span></span>|  
   |`sizeof(byte)`|<span data-ttu-id="ddd32-109">1</span><span class="sxs-lookup"><span data-stu-id="ddd32-109">1</span></span>|  
   |`sizeof(short)`|<span data-ttu-id="ddd32-110">2</span><span class="sxs-lookup"><span data-stu-id="ddd32-110">2</span></span>|  
   |`sizeof(ushort)`|<span data-ttu-id="ddd32-111">2</span><span class="sxs-lookup"><span data-stu-id="ddd32-111">2</span></span>|  
   |`sizeof(int)`|<span data-ttu-id="ddd32-112">4</span><span class="sxs-lookup"><span data-stu-id="ddd32-112">4</span></span>|  
   |`sizeof(uint)`|<span data-ttu-id="ddd32-113">4</span><span class="sxs-lookup"><span data-stu-id="ddd32-113">4</span></span>|  
   |`sizeof(long)`|<span data-ttu-id="ddd32-114">8</span><span class="sxs-lookup"><span data-stu-id="ddd32-114">8</span></span>|  
   |`sizeof(ulong)`|<span data-ttu-id="ddd32-115">8</span><span class="sxs-lookup"><span data-stu-id="ddd32-115">8</span></span>|  
   |`sizeof(char)`|<span data-ttu-id="ddd32-116">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="ddd32-116">2 (Unicode)</span></span>|  
   |`sizeof(float)`|<span data-ttu-id="ddd32-117">4</span><span class="sxs-lookup"><span data-stu-id="ddd32-117">4</span></span>|  
   |`sizeof(double)`|<span data-ttu-id="ddd32-118">8</span><span class="sxs-lookup"><span data-stu-id="ddd32-118">8</span></span>|  
   |`sizeof(decimal)`|<span data-ttu-id="ddd32-119">16</span><span class="sxs-lookup"><span data-stu-id="ddd32-119">16</span></span>|  
   |`sizeof(bool)`|<span data-ttu-id="ddd32-120">1</span><span class="sxs-lookup"><span data-stu-id="ddd32-120">1</span></span>| 
  
-   <span data-ttu-id="ddd32-121">Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="ddd32-121">Enum types.</span></span>
  
-   <span data-ttu-id="ddd32-122">Zeigertypen.</span><span class="sxs-lookup"><span data-stu-id="ddd32-122">Pointer types.</span></span>
  
-   <span data-ttu-id="ddd32-123">Benutzerdefinierte Strukturen, die keine Instanzenfelder oder automatisch implementierten Instanzeigenschaften enthalten, bei denen es sich um Verweistypen oder konstruierte Typen handelt.</span><span class="sxs-lookup"><span data-stu-id="ddd32-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>
  
 <span data-ttu-id="ddd32-124">Im folgenden Beispiel wird gezeigt, wie Sie die Größe von `int` abrufen:</span><span class="sxs-lookup"><span data-stu-id="ddd32-124">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="ddd32-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ddd32-125">Remarks</span></span>  
 <span data-ttu-id="ddd32-126">Ab C# Version 2.0 ist für die Anwendung von `sizeof` auf einfache Typen oder Enumerationstypen nicht mehr erforderlich, dass Code in [unsicherem](unsafe.md) Kontext kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="ddd32-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>
  
 <span data-ttu-id="ddd32-127">Operator `sizeof` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="ddd32-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="ddd32-128">Die Rückgabewerte des Operators `sizeof` sind vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="ddd32-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="ddd32-129">Die vorherige Tabelle zeigt die konstanten Werte, die als Ersatz für `sizeof`-Ausdrücke dienen, die über bestimmte einfache Typen als Operanden verfügen.</span><span class="sxs-lookup"><span data-stu-id="ddd32-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>  
    
 <span data-ttu-id="ddd32-130">Bei allen anderen Typen, darunter Strukturen, kann der Operator `sizeof` nur in unsicheren Codeblöcken zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="ddd32-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="ddd32-131">Sie können die Methode <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> zwar verwenden, der von dieser Methode zurückgegebene Wert entspricht allerdings nicht immer dem von `sizeof` zurückgegeben Wert.</span><span class="sxs-lookup"><span data-stu-id="ddd32-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="ddd32-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> gibt die Größe nach dem Marshalling des Typs zurück, während `sizeof` die Größe inklusive Abständen zurückgibt, die von der Common Language Runtime zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="ddd32-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddd32-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ddd32-133">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ddd32-134">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ddd32-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ddd32-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddd32-135">See Also</span></span>

- [<span data-ttu-id="ddd32-136">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ddd32-136">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ddd32-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ddd32-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ddd32-138">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ddd32-138">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ddd32-139">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ddd32-139">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
- [<span data-ttu-id="ddd32-140">enum</span><span class="sxs-lookup"><span data-stu-id="ddd32-140">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
- [<span data-ttu-id="ddd32-141">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="ddd32-141">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="ddd32-142">Strukturen</span><span class="sxs-lookup"><span data-stu-id="ddd32-142">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
- [<span data-ttu-id="ddd32-143">Konstanten</span><span class="sxs-lookup"><span data-stu-id="ddd32-143">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)
