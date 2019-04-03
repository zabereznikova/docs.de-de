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
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832644"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="a3d39-102">Call-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3d39-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="a3d39-103">Überträgt die Steuerung an eine `Function`, `Sub`, oder eine Dynamic Link Library (DLL)-Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a3d39-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3d39-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="a3d39-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a3d39-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="a3d39-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3d39-106">Required.</span></span> <span data-ttu-id="a3d39-107">Der Name der Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a3d39-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="a3d39-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a3d39-108">Optional.</span></span> <span data-ttu-id="a3d39-109">Liste der Variablen oder Ausdrücke zurück, die Argumente, die an die Prozedur übergeben werden, wenn sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a3d39-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="a3d39-110">Mehrere Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="a3d39-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="a3d39-111">Wenn Sie einschließen `argumentList`, müssen Sie es in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="a3d39-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="a3d39-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3d39-112">Remarks</span></span>  
 <span data-ttu-id="a3d39-113">Sie können die `Call` -Schlüsselwort, wenn Sie eine Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a3d39-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="a3d39-114">Für die meisten Aufrufe von Prozeduren müssen Sie sich nicht auf dieses Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3d39-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="a3d39-115">In der Regel die `Call` -Schlüsselwort, wenn der aufgerufene Ausdruck nicht mit einer ID, startet.</span><span class="sxs-lookup"><span data-stu-id="a3d39-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="a3d39-116">Verwenden der `Call` Schlüsselwort für einen anderen Verwendungszweck wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a3d39-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="a3d39-117">Wenn die Prozedur einen Wert zurückgibt, die `Call` Anweisung verworfen.</span><span class="sxs-lookup"><span data-stu-id="a3d39-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3d39-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3d39-118">Example</span></span>  
 <span data-ttu-id="a3d39-119">Der folgende Code zeigt zwei Beispiele, in denen die `Call` Schlüsselwort ist erforderlich, um eine Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a3d39-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="a3d39-120">In beiden Beispielen beginnen nicht der aufgerufene Ausdruck mit einem Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="a3d39-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="a3d39-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3d39-121">See also</span></span>

- [<span data-ttu-id="a3d39-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a3d39-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="a3d39-123">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a3d39-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="a3d39-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a3d39-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="a3d39-125">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="a3d39-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
