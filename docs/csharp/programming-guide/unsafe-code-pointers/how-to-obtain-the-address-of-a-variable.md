---
title: 'Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
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
ms.openlocfilehash: 169f68cc80b7a27427a9987942e66e0ba9ed1a02
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="0ffef-102">Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0ffef-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="0ffef-103">Um die Adresse eines unären Ausdrucks abzurufen, der eine feste Variable ergibt, verwenden Sie den address-of-Operator:</span><span class="sxs-lookup"><span data-stu-id="0ffef-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="0ffef-104">Der address-of-Operator kann nur auf eine Variable angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ffef-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="0ffef-105">Wenn die Variable beweglich ist, können Sie eine [feste Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) verwenden, um die Variable vorübergehen zu befestigen, um ihre Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0ffef-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="0ffef-106">Sie müssen sicherstellen, dass die Variable initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0ffef-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="0ffef-107">Der Compiler gibt keine Fehlermeldung aus, wenn die Variable nicht initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="0ffef-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="0ffef-108">Sie können nicht die Adresse einer Konstanten oder eines Werts abrufen.</span><span class="sxs-lookup"><span data-stu-id="0ffef-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ffef-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ffef-109">Example</span></span>  
 <span data-ttu-id="0ffef-110">In diesem Beispiel wird ein Zeiger auf `int`, `p`, deklariert. Die Adresse einer ganzzahligen Variable, `number`, wird ihm zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0ffef-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="0ffef-111">Die Variable `number` wird als Ergebnis der Zuweisung zu *p initialisiert.</span><span class="sxs-lookup"><span data-stu-id="0ffef-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="0ffef-112">Wenn Sie diese Zuweisungsanweisung zu einem Kommentar machen, wird die Initialisierung der Variablen `number` entfernt, aber kein Kompilierzeitfehler ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="0ffef-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="0ffef-113">Beachten Sie den Gebrauch des [Memberzugriffsoperators](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` zum Abrufen und Anzeigen der Adresse, die im Zeiger gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="0ffef-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 <span data-ttu-id="0ffef-114">[!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0ffef-114">[!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="0ffef-115">[!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0ffef-115">[!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ffef-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ffef-116">See Also</span></span>  
 <span data-ttu-id="0ffef-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ffef-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0ffef-118">[Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="0ffef-118">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="0ffef-119">[Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="0ffef-119">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="0ffef-120">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="0ffef-120">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="0ffef-121">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="0ffef-121">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="0ffef-122">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0ffef-122">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="0ffef-123">stackalloc</span><span class="sxs-lookup"><span data-stu-id="0ffef-123">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

