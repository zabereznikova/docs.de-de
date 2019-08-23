---
title: Return-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957676"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="3f927-102">Return-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f927-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="3f927-103">Gibt die Steuerung an den Code zurück, `Function`der `Sub`die `Get`Prozedur `Set`,, `Operator` , oder aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="3f927-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f927-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f927-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="3f927-105">Segment</span><span class="sxs-lookup"><span data-stu-id="3f927-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="3f927-106">Erforderlich in einer `Function`- `Get`,- `Operator` oder-Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3f927-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="3f927-107">Ein Ausdruck, der den Wert darstellt, der an den aufrufenden Code zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f927-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f927-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f927-108">Remarks</span></span>  
 <span data-ttu-id="3f927-109">In einer `Sub` - `Set` oder-Prozedur `Return` entspricht die-Anweisung einer `Exit Sub` - `Exit Property` oder-Anweisung `expression` und darf nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3f927-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="3f927-110">In einer `Function`- `Get`,- `Operator` oder-Prozedur `Return` muss die- `expression`Anweisung enthalten `expression` und muss zu einem Datentyp ausgewertet werden, der in den Rückgabetyp der Prozedur konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f927-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="3f927-111">In einer `Function` - `Get` oder-Prozedur haben Sie auch die Alternative, dem Prozedur Namen einen Ausdruck zuzuweisen, der als Rückgabewert fungieren soll, und dann eine `Exit Function` - `Exit Property` oder-Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3f927-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="3f927-112">In einer `Operator` Prozedur müssen Sie verwenden `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="3f927-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="3f927-113">Sie können beliebig viele `Return` -Anweisungen in der gleichen Prozedur einschließen.</span><span class="sxs-lookup"><span data-stu-id="3f927-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f927-114">Der Code in einem `Finally` -Block wird ausgeführt `Return` , nachdem eine `Try` - `Catch` Anweisung in einem-oder-Block `Return` gefunden wurde, aber bevor diese Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f927-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="3f927-115">Eine `Return` -Anweisung kann nicht in einen `Finally` -Block eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="3f927-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f927-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f927-116">Example</span></span>  
 <span data-ttu-id="3f927-117">Im folgenden Beispiel wird die `Return` -Anweisung mehrmals verwendet, um zum aufrufenden Code zurückzukehren, wenn die Prozedur keine andere Aktion ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="3f927-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="3f927-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f927-118">See also</span></span>

- [<span data-ttu-id="3f927-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3f927-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="3f927-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3f927-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="3f927-121">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3f927-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="3f927-122">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3f927-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="3f927-123">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3f927-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="3f927-124">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3f927-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="3f927-125">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3f927-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="3f927-126">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3f927-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
