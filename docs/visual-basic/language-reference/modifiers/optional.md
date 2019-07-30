---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 3758f17634395236abf2cd7059418bf6f8b6c062
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630922"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="7c42f-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c42f-102">Optional (Visual Basic)</span></span>

<span data-ttu-id="7c42f-103">Gibt an, dass ein Prozedur Argument beim Aufrufen der Prozedur ausgelassen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c42f-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c42f-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c42f-104">Remarks</span></span>

<span data-ttu-id="7c42f-105">Für jeden optionalen Parameter muss ein konstanter Ausdruck als Standardwert dieses Parameters angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7c42f-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="7c42f-106">Wenn der Ausdruck als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird der Standardwert des Value-Datentyps als Standardwert des-Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c42f-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>

<span data-ttu-id="7c42f-107">Wenn die Parameterliste einen optionalen Parameter enthält, muss jeder Parameter, der darauf folgt, ebenfalls optional sein.</span><span class="sxs-lookup"><span data-stu-id="7c42f-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>

<span data-ttu-id="7c42f-108">Der `Optional`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="7c42f-108">The `Optional` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="7c42f-109">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7c42f-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="7c42f-110">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7c42f-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="7c42f-111">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7c42f-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="7c42f-112">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7c42f-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

> [!NOTE]
> <span data-ttu-id="7c42f-113">Wenn Sie eine Prozedur mit oder ohne optionale Parameter aufrufen, können Sie Argumente anhand der Position oder des Namens übergeben.</span><span class="sxs-lookup"><span data-stu-id="7c42f-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="7c42f-114">Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="7c42f-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7c42f-115">Sie können auch eine Prozedur mit optionalen Parametern definieren, indem Sie überladen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c42f-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="7c42f-116">Wenn Sie über einen optionalen Parameter verfügen, können Sie zwei überladene Versionen der Prozedur definieren, eine, die den-Parameter annimmt, und eine, die nicht ist.</span><span class="sxs-lookup"><span data-stu-id="7c42f-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="7c42f-117">Weitere Informationen finden Sie unter [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="7c42f-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>

## <a name="example"></a><span data-ttu-id="7c42f-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c42f-118">Example</span></span>

<span data-ttu-id="7c42f-119">Im folgenden Beispiel wird eine Prozedur definiert, die über einen optionalen Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="7c42f-119">The following example defines a procedure that has an optional parameter.</span></span>

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a><span data-ttu-id="7c42f-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c42f-120">Example</span></span>

<span data-ttu-id="7c42f-121">Im folgenden Beispiel wird veranschaulicht, wie eine Prozedur mit Argumenten, die über die Position und mit den über den Namen übermittelt werden, aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7c42f-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="7c42f-122">Die Prozedur verfügt über zwei optionale Parameter.</span><span class="sxs-lookup"><span data-stu-id="7c42f-122">The procedure has two optional parameters.</span></span>

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a><span data-ttu-id="7c42f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c42f-123">See also</span></span>

- [<span data-ttu-id="7c42f-124">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="7c42f-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="7c42f-125">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="7c42f-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="7c42f-126">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7c42f-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
