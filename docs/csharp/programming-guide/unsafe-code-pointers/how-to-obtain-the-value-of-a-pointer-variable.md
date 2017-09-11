---
title: 'Gewusst wie: Abrufen des Werts einer Zeigervariablen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
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
ms.openlocfilehash: 4cff42de07f2edb279ddd1cafefe9f4b67a38ce1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="c127c-102">Gewusst wie: Abrufen des Werts einer Zeigervariablen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c127c-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="c127c-103">Verwenden Sie den Zeigerdereferenzierungsoperator, um die Variable aus dem Speicherort abzurufen, auf den von einem Zeiger gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c127c-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="c127c-104">Der Ausdruck hat das folgende Format, wobei `p` ein Zeigertyp ist:</span><span class="sxs-lookup"><span data-stu-id="c127c-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="c127c-105">Sie können den unären Dereferenzierungsoperator nicht auf einen Ausdruck anwenden, der nicht dem Zeigertyp entspricht.</span><span class="sxs-lookup"><span data-stu-id="c127c-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="c127c-106">Zudem können Sie ihn nicht auf einen [leeren](../../../csharp/language-reference/keywords/void.md) Zeiger anwenden.</span><span class="sxs-lookup"><span data-stu-id="c127c-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="c127c-107">Wenn Sie den Dereferenzierungsoperator auf einen [NULL](../../../csharp/language-reference/keywords/null.md)-Zeiger anwenden, ist das Ergebnis von der Implementierung abhängig.</span><span class="sxs-lookup"><span data-stu-id="c127c-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c127c-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c127c-108">Example</span></span>  
 <span data-ttu-id="c127c-109">In folgendem Beispiel wird auf eine Variable des Typs `char` mithilfe eines Zeigers eines anderen Typs zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="c127c-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="c127c-110">Beachten Sie, dass die Adresse von `theChar` je nach Ausführung variiert, da sich die physische Adresse ändern kann, die der Variable zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c127c-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 <span data-ttu-id="c127c-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c127c-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="c127c-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c127c-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span></span>  
  
 <span data-ttu-id="c127c-113">**Wert von theChar = Z** </span><span class="sxs-lookup"><span data-stu-id="c127c-113">**Value of theChar = Z** </span></span>  
<span data-ttu-id="c127c-114">**Adresse von theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="c127c-114">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="c127c-115">**Wert von pChar = Z** </span><span class="sxs-lookup"><span data-stu-id="c127c-115">**Value of pChar = Z** </span></span>  
<span data-ttu-id="c127c-116">**Wert von pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="c127c-116">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="c127c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c127c-117">See Also</span></span>  
 <span data-ttu-id="c127c-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c127c-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c127c-119">[Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="c127c-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="c127c-120">[Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="c127c-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="c127c-121">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="c127c-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="c127c-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="c127c-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="c127c-123">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c127c-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="c127c-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="c127c-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

