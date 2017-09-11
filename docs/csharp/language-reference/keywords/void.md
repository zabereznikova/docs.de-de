---
title: void (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
dev_langs:
- CSharp
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
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
ms.openlocfilehash: d1bd7ece5ce3b558c616a4eb3a4668c3c13eb1cb
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="void-c-reference"></a><span data-ttu-id="ef4bd-102">void (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ef4bd-102">void (C# Reference)</span></span>
<span data-ttu-id="ef4bd-103">Wenn `void` als Rückgabetyp für eine Methode verwendet wird, wird angegeben, dass die Methode keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ef4bd-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="ef4bd-104">`void` ist in der Parameterliste einer Methode unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ef4bd-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="ef4bd-105">Eine Methode, mit der keine Parameter übernommen und keine Werte zurückgegeben werden, wird wie folgt deklariert:</span><span class="sxs-lookup"><span data-stu-id="ef4bd-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="ef4bd-106">`void` wird auch in einem unsicheren Kontext verwendet, um einen Zeiger auf einen unbekannten Typ zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ef4bd-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="ef4bd-107">Weitere Informationen finden Sie unter [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="ef4bd-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="ef4bd-108">`void` ist ein Alias für den <xref:System.Void?displayProperty=fullName>-Typ aus dem .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef4bd-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=fullName> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ef4bd-109">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ef4bd-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ef4bd-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef4bd-110">See also</span></span>
 <span data-ttu-id="ef4bd-111">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef4bd-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ef4bd-112">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef4bd-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ef4bd-113">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef4bd-113">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ef4bd-114">[Verweistypen](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="ef4bd-114">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="ef4bd-115">[Werttypen](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="ef4bd-115">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="ef4bd-116">[Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="ef4bd-116">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 [<span data-ttu-id="ef4bd-117">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="ef4bd-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

