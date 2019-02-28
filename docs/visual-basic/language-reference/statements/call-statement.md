---
title: Call-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 6d8fd8060789c4035fd38e41c5de7e43f6330e64
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977018"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="8cc81-102">Call-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cc81-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="8cc81-103">Überträgt die Steuerung an eine `Function`, `Sub`, oder eine Dynamic Link Library (DLL)-Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8cc81-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8cc81-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8cc81-105">Teile</span><span class="sxs-lookup"><span data-stu-id="8cc81-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="8cc81-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8cc81-106">Required.</span></span> <span data-ttu-id="8cc81-107">Der Name der Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8cc81-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="8cc81-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8cc81-108">Optional.</span></span> <span data-ttu-id="8cc81-109">Liste der Variablen oder Ausdrücke zurück, die Argumente, die an die Prozedur übergeben werden, wenn sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8cc81-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="8cc81-110">Mehrere Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="8cc81-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="8cc81-111">Wenn Sie einschließen `argumentList`, müssen Sie es in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="8cc81-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="8cc81-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8cc81-112">Remarks</span></span>  
 <span data-ttu-id="8cc81-113">Sie können die `Call` -Schlüsselwort, wenn Sie eine Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8cc81-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="8cc81-114">Für die meisten Aufrufe von Prozeduren müssen Sie sich nicht auf dieses Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cc81-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="8cc81-115">In der Regel die `Call` -Schlüsselwort, wenn der aufgerufene Ausdruck nicht mit einer ID, startet.</span><span class="sxs-lookup"><span data-stu-id="8cc81-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="8cc81-116">Verwenden der `Call` Schlüsselwort für einen anderen Verwendungszweck wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="8cc81-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="8cc81-117">Wenn die Prozedur einen Wert zurückgibt, die `Call` Anweisung verworfen.</span><span class="sxs-lookup"><span data-stu-id="8cc81-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cc81-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8cc81-118">Example</span></span>  
 <span data-ttu-id="8cc81-119">Der folgende Code zeigt zwei Beispiele, in denen die `Call` Schlüsselwort ist erforderlich, um eine Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8cc81-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="8cc81-120">In beiden Beispielen beginnen nicht der aufgerufene Ausdruck mit einem Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="8cc81-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="8cc81-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cc81-121">See also</span></span>
- [<span data-ttu-id="8cc81-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8cc81-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="8cc81-123">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8cc81-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="8cc81-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8cc81-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="8cc81-125">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8cc81-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
