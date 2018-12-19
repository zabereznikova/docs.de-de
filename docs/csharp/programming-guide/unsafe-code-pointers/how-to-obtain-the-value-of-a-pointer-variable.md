---
title: 'Vorgehensweise: Abrufen des Werts einer Zeigervariablen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: b20642344b34b5426512ef64bde2ab33d55136b9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236634"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="07d15-102">Vorgehensweise: Abrufen des Werts einer Zeigervariablen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="07d15-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="07d15-103">Verwenden Sie den Zeigerdereferenzierungsoperator, um die Variable aus dem Speicherort abzurufen, auf den von einem Zeiger gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="07d15-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="07d15-104">Der Ausdruck hat das folgende Format, wobei `p` ein Zeigertyp ist:</span><span class="sxs-lookup"><span data-stu-id="07d15-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="07d15-105">Sie können den unären Dereferenzierungsoperator nicht auf einen Ausdruck anwenden, der nicht dem Zeigertyp entspricht.</span><span class="sxs-lookup"><span data-stu-id="07d15-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="07d15-106">Zudem können Sie ihn nicht auf einen [leeren](../../../csharp/language-reference/keywords/void.md) Zeiger anwenden.</span><span class="sxs-lookup"><span data-stu-id="07d15-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="07d15-107">Wenn Sie den Dereferenzierungsoperator auf einen [NULL](../../../csharp/language-reference/keywords/null.md)-Zeiger anwenden, ist das Ergebnis von der Implementierung abhängig.</span><span class="sxs-lookup"><span data-stu-id="07d15-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07d15-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d15-108">Example</span></span>  
 <span data-ttu-id="07d15-109">In folgendem Beispiel wird auf eine Variable des Typs `char` mithilfe eines Zeigers eines anderen Typs zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="07d15-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="07d15-110">Beachten Sie, dass die Adresse von `theChar` je nach Ausführung variiert, da sich die physische Adresse ändern kann, die der Variable zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="07d15-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
<span data-ttu-id="07d15-111">**Value of theChar = Z**
**Address of theChar = 12F718**
**Value of pChar = Z**
**Value of pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="07d15-111">**Value of theChar = Z**
**Address of theChar = 12F718**
**Value of pChar = Z**
**Value of pInt = 90**</span></span>

## <a name="see-also"></a><span data-ttu-id="07d15-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07d15-112">See Also</span></span>

- [<span data-ttu-id="07d15-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="07d15-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="07d15-114">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="07d15-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="07d15-115">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="07d15-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="07d15-116">Typen</span><span class="sxs-lookup"><span data-stu-id="07d15-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="07d15-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="07d15-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="07d15-118">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="07d15-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="07d15-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="07d15-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
