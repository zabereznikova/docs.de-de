---
title: Return-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: 3ca705409bc8233bc2562c64b8e7704f08dd7641
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871810"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="89df4-102">Return-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89df4-102">Return Statement (Visual Basic)</span></span>

<span data-ttu-id="89df4-103">Gibt die Steuerung an den Code zurück, der die `Function` `Sub` Prozedur,, `Get` , oder aufgerufen hat `Set` `Operator` .</span><span class="sxs-lookup"><span data-stu-id="89df4-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89df4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89df4-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="89df4-105">Teil</span><span class="sxs-lookup"><span data-stu-id="89df4-105">Part</span></span>  

 `expression`  
 <span data-ttu-id="89df4-106">Erforderlich in einer- `Function` ,- `Get` oder- `Operator` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="89df4-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="89df4-107">Ein Ausdruck, der den Wert darstellt, der an den aufrufenden Code zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="89df4-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89df4-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="89df4-108">Remarks</span></span>  

 <span data-ttu-id="89df4-109">In einer- `Sub` oder `Set` -Prozedur `Return` entspricht die-Anweisung einer `Exit Sub` `Exit Property` -oder-Anweisung und `expression` darf nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="89df4-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="89df4-110">In einer- `Function` ,- `Get` oder `Operator` -Prozedur `Return` muss die-Anweisung enthalten `expression` und muss `expression` zu einem Datentyp ausgewertet werden, der in den Rückgabetyp der Prozedur konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="89df4-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="89df4-111">In einer- `Function` oder `Get` -Prozedur haben Sie auch die Alternative, dem Prozedur Namen einen Ausdruck zuzuweisen, der als Rückgabewert fungieren soll, und dann eine- `Exit Function` oder-Anweisung auszuführen `Exit Property` .</span><span class="sxs-lookup"><span data-stu-id="89df4-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="89df4-112">In einer `Operator` Prozedur müssen Sie verwenden `Return expression` .</span><span class="sxs-lookup"><span data-stu-id="89df4-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="89df4-113">Sie können beliebig viele- `Return` Anweisungen in der gleichen Prozedur einschließen.</span><span class="sxs-lookup"><span data-stu-id="89df4-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89df4-114">Der Code in einem- `Finally` Block `Return` wird ausgeführt, nachdem eine-Anweisung in einem- `Try` oder-Block gefunden `Catch` wurde, aber bevor diese `Return` Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89df4-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="89df4-115">Eine- `Return` Anweisung kann nicht in einen-Block eingeschlossen werden `Finally` .</span><span class="sxs-lookup"><span data-stu-id="89df4-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89df4-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89df4-116">Example</span></span>  

 <span data-ttu-id="89df4-117">Im folgenden Beispiel wird die- `Return` Anweisung mehrmals verwendet, um zum aufrufenden Code zurückzukehren, wenn die Prozedur keine andere Aktion ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="89df4-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="89df4-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89df4-118">See also</span></span>

- [<span data-ttu-id="89df4-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89df4-119">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="89df4-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89df4-120">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="89df4-121">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89df4-121">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="89df4-122">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89df4-122">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="89df4-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="89df4-123">Operator Statement</span></span>](operator-statement.md)
- [<span data-ttu-id="89df4-124">Property Statement</span><span class="sxs-lookup"><span data-stu-id="89df4-124">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="89df4-125">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89df4-125">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="89df4-126">Try... Catch... Abschließend-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89df4-126">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
