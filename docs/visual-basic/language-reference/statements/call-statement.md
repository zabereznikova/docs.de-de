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
ms.openlocfilehash: af0b62d6cfacbcf94f527e049e07e51bf496a6cf
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392758"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="d0b95-102">Call-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0b95-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="d0b95-103">Überträgt die Steuerung an eine `Function`-, `Sub`-oder DLL-Prozedur (Dynamic-Link Library).</span><span class="sxs-lookup"><span data-stu-id="d0b95-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0b95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0b95-104">Syntax</span></span>

```vb
[ Call ] procedureName [ (argumentList) ]
```

## <a name="parts"></a><span data-ttu-id="d0b95-105">Teile</span><span class="sxs-lookup"><span data-stu-id="d0b95-105">Parts</span></span>

|||
|---|---|
|`procedureName`|<span data-ttu-id="d0b95-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d0b95-106">Required.</span></span> <span data-ttu-id="d0b95-107">Der Name der aufzurufenden Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d0b95-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="d0b95-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="d0b95-108">Optional.</span></span> <span data-ttu-id="d0b95-109">Liste der Variablen oder Ausdrücke, die Argumente darstellen, die beim Aufrufen an die Prozedur übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="d0b95-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="d0b95-110">Mehrere Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="d0b95-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="d0b95-111">Wenn Sie `argumentList` einschließen, müssen Sie Sie in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="d0b95-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="d0b95-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0b95-112">Remarks</span></span>

 <span data-ttu-id="d0b95-113">Sie können das Schlüsselwort `Call` verwenden, wenn Sie eine Prozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d0b95-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="d0b95-114">Bei den meisten Prozedur aufrufen müssen Sie dieses Schlüsselwort nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0b95-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="d0b95-115">Normalerweise verwenden Sie das Schlüsselwort "`Call`", wenn der aufgerufene Ausdruck nicht mit einem Bezeichner beginnt.</span><span class="sxs-lookup"><span data-stu-id="d0b95-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="d0b95-116">Die Verwendung des Schlüssel Worts "`Call`" für andere Verwendungszwecke wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d0b95-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="d0b95-117">Wenn die Prozedur einen Wert zurückgibt, wird Sie durch die `Call`-Anweisung verworfen.</span><span class="sxs-lookup"><span data-stu-id="d0b95-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="d0b95-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0b95-118">Example</span></span>

 <span data-ttu-id="d0b95-119">Der folgende Code zeigt zwei Beispiele, in denen das `Call`-Schlüsselwort erforderlich ist, um eine Prozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d0b95-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="d0b95-120">In beiden Beispielen beginnt der aufgerufene Ausdruck nicht mit einem Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="d0b95-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="d0b95-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0b95-121">See also</span></span>

- [<span data-ttu-id="d0b95-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d0b95-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="d0b95-123">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d0b95-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="d0b95-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d0b95-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="d0b95-125">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="d0b95-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
