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
ms.openlocfilehash: a04ebddc7db176188876da1082e1e6946e1e8eec
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005166"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="14f5a-102">Call-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14f5a-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="14f5a-103">Überträgt die Steuerung an eine `Function`-, `Sub`-oder DLL-Prozedur (Dynamic-Link Library).</span><span class="sxs-lookup"><span data-stu-id="14f5a-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14f5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14f5a-104">Syntax</span></span>  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="14f5a-105">Teile</span><span class="sxs-lookup"><span data-stu-id="14f5a-105">Parts</span></span>  

|||
|---|---|
|`procedureName`|<span data-ttu-id="14f5a-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14f5a-106">Required.</span></span> <span data-ttu-id="14f5a-107">Der Name der aufzurufenden Prozedur.</span><span class="sxs-lookup"><span data-stu-id="14f5a-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="14f5a-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="14f5a-108">Optional.</span></span> <span data-ttu-id="14f5a-109">Liste der Variablen oder Ausdrücke, die Argumente darstellen, die beim Aufrufen an die Prozedur übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="14f5a-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="14f5a-110">Mehrere Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="14f5a-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="14f5a-111">Wenn Sie `argumentList` einschließen, müssen Sie Sie in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="14f5a-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="14f5a-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14f5a-112">Remarks</span></span>

 <span data-ttu-id="14f5a-113">Sie können das Schlüsselwort `Call` verwenden, wenn Sie eine Prozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="14f5a-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="14f5a-114">Bei den meisten Prozedur aufrufen müssen Sie dieses Schlüsselwort nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="14f5a-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="14f5a-115">Normalerweise verwenden Sie das Schlüsselwort "`Call`", wenn der aufgerufene Ausdruck nicht mit einem Bezeichner beginnt.</span><span class="sxs-lookup"><span data-stu-id="14f5a-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="14f5a-116">Die Verwendung des Schlüssel Worts "`Call`" für andere Verwendungszwecke wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="14f5a-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="14f5a-117">Wenn die Prozedur einen Wert zurückgibt, wird Sie durch die `Call`-Anweisung verworfen.</span><span class="sxs-lookup"><span data-stu-id="14f5a-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="14f5a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14f5a-118">Example</span></span>

 <span data-ttu-id="14f5a-119">Der folgende Code zeigt zwei Beispiele, in denen das `Call`-Schlüsselwort erforderlich ist, um eine Prozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="14f5a-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="14f5a-120">In beiden Beispielen beginnt der aufgerufene Ausdruck nicht mit einem Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="14f5a-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="14f5a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14f5a-121">See also</span></span>

- [<span data-ttu-id="14f5a-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="14f5a-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="14f5a-123">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="14f5a-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="14f5a-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="14f5a-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="14f5a-125">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="14f5a-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
