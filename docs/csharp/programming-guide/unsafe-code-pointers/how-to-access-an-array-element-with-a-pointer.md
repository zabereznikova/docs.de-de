---
title: 'Gewusst wie: Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 16
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
ms.openlocfilehash: 73f14aba63b7f7677a889f18cc1b410e3ecf1438
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="9d6bb-102">Gewusst wie: Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9d6bb-102">How to: Access an Array Element with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="9d6bb-103">In einem unsicheren Kontext können Sie mittels Zeigerelementzugriff auf ein Element im Speicher zugreifen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9d6bb-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 <span data-ttu-id="9d6bb-104">Der Ausdruck in eckigen Klammern muss implizit in `int`, `uint`, `long` oder `ulong` konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="9d6bb-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="9d6bb-105">Der Vorgang p[e] entspricht *(p+e).</span><span class="sxs-lookup"><span data-stu-id="9d6bb-105">The operation p[e] is equivalent to *(p+e).</span></span> <span data-ttu-id="9d6bb-106">Wie in C und C++ überprüft der Zeigerelementzugriff keine Fehler außerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="9d6bb-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d6bb-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d6bb-107">Example</span></span>  
 <span data-ttu-id="9d6bb-108">In diesem Beispiel werden einem Zeichenarray, `charPointer`, 123 Speicheradressen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9d6bb-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="9d6bb-109">Das Array wird verwendet, um die Klein- und Großbuchstaben in zwei [for](../../../csharp/language-reference/keywords/for.md)-Schleifen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d6bb-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>  
  
 <span data-ttu-id="9d6bb-110">Beachten Sie, dass der Ausdruck `charPointer[i]` und der Ausdruck `*(charPointer + i)` äquivalent sind. Sie erhalten dasselbe Ergebnis, unabhängig davon, welchen Ausdruck Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d6bb-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 <span data-ttu-id="9d6bb-111">[!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9d6bb-111">[!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]</span></span>  
  
 <span data-ttu-id="9d6bb-112">[!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9d6bb-112">[!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]</span></span>  
  
 <span data-ttu-id="9d6bb-113">**Großbuchstaben:**</span><span class="sxs-lookup"><span data-stu-id="9d6bb-113">**Uppercase letters:**</span></span>  
<span data-ttu-id="9d6bb-114">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="9d6bb-114">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="9d6bb-115">**Kleinbuchstaben:**</span><span class="sxs-lookup"><span data-stu-id="9d6bb-115">**Lowercase letters:**</span></span>  
<span data-ttu-id="9d6bb-116">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="9d6bb-116">**abcdefghijklmnopqrstuvwxyz**</span></span>   
## <a name="see-also"></a><span data-ttu-id="9d6bb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d6bb-117">See Also</span></span>  
 <span data-ttu-id="9d6bb-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9d6bb-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9d6bb-119">[Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="9d6bb-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="9d6bb-120">[Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="9d6bb-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="9d6bb-121">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="9d6bb-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="9d6bb-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="9d6bb-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="9d6bb-123">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9d6bb-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="9d6bb-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="9d6bb-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

