---
title: 'Gewusst wie: Abrufen des Werts einer Zeigervariablen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 288d8cb2d286f55cc9a162614d45ef7b298f79f1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974483"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="6eb86-102">Gewusst wie: Abrufen des Werts einer Zeigervariablen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6eb86-102">How to: obtain the value of a pointer variable (C# Programming Guide)</span></span>

<span data-ttu-id="6eb86-103">Verwenden Sie den Zeigerdereferenzierungsoperator, um die Variable aus dem Speicherort abzurufen, auf den von einem Zeiger gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6eb86-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="6eb86-104">Der Ausdruck hat das folgende Format, wobei `p` ein Zeigertyp ist:</span><span class="sxs-lookup"><span data-stu-id="6eb86-104">The expression takes the following form, where `p` is a pointer type:</span></span>  

```csharp
*p;  
```

<span data-ttu-id="6eb86-105">Sie können den unären Dereferenzierungsoperator nicht auf einen Ausdruck anwenden, der nicht dem Zeigertyp entspricht.</span><span class="sxs-lookup"><span data-stu-id="6eb86-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="6eb86-106">Zudem können Sie ihn nicht auf einen [leeren](../../../csharp/language-reference/keywords/void.md) Zeiger anwenden.</span><span class="sxs-lookup"><span data-stu-id="6eb86-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  

<span data-ttu-id="6eb86-107">Wenn Sie den Dereferenzierungsoperator auf einen [NULL](../../../csharp/language-reference/keywords/null.md)-Zeiger anwenden, ist das Ergebnis von der Implementierung abhängig.</span><span class="sxs-lookup"><span data-stu-id="6eb86-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  

## <a name="example"></a><span data-ttu-id="6eb86-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6eb86-108">Example</span></span>

<span data-ttu-id="6eb86-109">In folgendem Beispiel wird auf eine Variable des Typs `char` mithilfe eines Zeigers eines anderen Typs zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="6eb86-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="6eb86-110">Beachten Sie, dass die Adresse von `theChar` je nach Ausführung variiert, da sich die physische Adresse ändern kann, die der Variable zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6eb86-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  

 [!code-csharp[csProgGuidePointers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#5)]  

 [!code-csharp[csProgGuidePointers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#6)]  
  
<span data-ttu-id="6eb86-111">**Wert von theChar = Z**</span><span class="sxs-lookup"><span data-stu-id="6eb86-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="6eb86-112">**Adresse von theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="6eb86-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="6eb86-113">**Wert von pChar = Z**</span><span class="sxs-lookup"><span data-stu-id="6eb86-113">**Value of pChar = Z**</span></span>  
<span data-ttu-id="6eb86-114">**Wert von pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="6eb86-114">**Value of pInt = 90**</span></span>  

## <a name="see-also"></a><span data-ttu-id="6eb86-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eb86-115">See also</span></span>

- [<span data-ttu-id="6eb86-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6eb86-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6eb86-117">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="6eb86-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="6eb86-118">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="6eb86-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="6eb86-119">Typen</span><span class="sxs-lookup"><span data-stu-id="6eb86-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="6eb86-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="6eb86-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="6eb86-121">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6eb86-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="6eb86-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="6eb86-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
