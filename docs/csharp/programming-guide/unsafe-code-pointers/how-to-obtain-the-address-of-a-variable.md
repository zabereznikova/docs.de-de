---
title: 'Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="822dd-102">Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="822dd-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="822dd-103">Um die Adresse eines unären Ausdrucks abzurufen, der eine feste Variable ergibt, verwenden Sie den address-of-Operator:</span><span class="sxs-lookup"><span data-stu-id="822dd-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="822dd-104">Der address-of-Operator kann nur auf eine Variable angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="822dd-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="822dd-105">Wenn die Variable beweglich ist, können Sie eine [feste Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) verwenden, um die Variable vorübergehen zu befestigen, um ihre Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="822dd-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="822dd-106">Sie müssen sicherstellen, dass die Variable initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="822dd-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="822dd-107">Der Compiler gibt keine Fehlermeldung aus, wenn die Variable nicht initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="822dd-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="822dd-108">Sie können nicht die Adresse einer Konstanten oder eines Werts abrufen.</span><span class="sxs-lookup"><span data-stu-id="822dd-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="822dd-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="822dd-109">Example</span></span>  
 <span data-ttu-id="822dd-110">In diesem Beispiel wird ein Zeiger auf `int`, `p`, deklariert. Die Adresse einer ganzzahligen Variable, `number`, wird ihm zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="822dd-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="822dd-111">Die Variable `number` wird als Ergebnis der Zuweisung zu *p initialisiert.</span><span class="sxs-lookup"><span data-stu-id="822dd-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="822dd-112">Wenn Sie diese Zuweisungsanweisung zu einem Kommentar machen, wird die Initialisierung der Variablen `number` entfernt, aber kein Kompilierzeitfehler ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="822dd-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="822dd-113">Beachten Sie den Gebrauch des [Memberzugriffsoperators](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` zum Abrufen und Anzeigen der Adresse, die im Zeiger gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="822dd-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="822dd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="822dd-114">See Also</span></span>  
 [<span data-ttu-id="822dd-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="822dd-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="822dd-116">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="822dd-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="822dd-117">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="822dd-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="822dd-118">Typen</span><span class="sxs-lookup"><span data-stu-id="822dd-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="822dd-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="822dd-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="822dd-120">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="822dd-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="822dd-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="822dd-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
