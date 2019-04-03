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
ms.openlocfilehash: 67ceedffecdfba8ec0c2829a3af31d194f18bd88
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820788"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="0a719-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a719-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="0a719-103">Gibt an, dass ein Prozedurargument beim Aufrufen der Prozedur ausgelassen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0a719-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a719-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a719-104">Remarks</span></span>  
 <span data-ttu-id="0a719-105">Für jeden optionalen Parameter verwenden müssen Sie einen konstanten Ausdruck als Standardwert dieses Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="0a719-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="0a719-106">Wenn der Ausdruck ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird der Standardwert des Datentyps Wert als den Standardwert des Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a719-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="0a719-107">Wenn die Parameterliste einen optionalen Parameter enthält, muss jeder Parameter, die darauf folgt ebenfalls optional sein.</span><span class="sxs-lookup"><span data-stu-id="0a719-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="0a719-108">Der `Optional`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0a719-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="0a719-109">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0a719-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="0a719-110">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0a719-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="0a719-111">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0a719-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="0a719-112">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0a719-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="0a719-113">Beim Aufrufen einer Prozedur mit oder ohne optionale Parameter können Sie die Argumente nach Position oder anhand des Namens übergeben.</span><span class="sxs-lookup"><span data-stu-id="0a719-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="0a719-114">Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="0a719-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a719-115">Sie können auch eine Prozedur mit optionalen Parametern definieren, indem mithilfe der Überladung.</span><span class="sxs-lookup"><span data-stu-id="0a719-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="0a719-116">Wenn Sie einen optionalen Parameter verfügen, können Sie zwei überladene Versionen der Prozedur, eines, das der Parameter akzeptiert und eine, die nicht definieren.</span><span class="sxs-lookup"><span data-stu-id="0a719-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="0a719-117">Weitere Informationen finden Sie unter [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="0a719-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a719-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a719-118">Example</span></span>  
 <span data-ttu-id="0a719-119">Das folgende Beispiel definiert eine Prozedur mit einem optionalen Parameter.</span><span class="sxs-lookup"><span data-stu-id="0a719-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
```  
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
  
## <a name="example"></a><span data-ttu-id="0a719-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a719-120">Example</span></span>  
 <span data-ttu-id="0a719-121">Im folgenden Beispiel wird veranschaulicht, wie eine Prozedur mit Argumenten, die mit Ihrer Position übergeben und nach Namen übergebenen Argumenten aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0a719-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="0a719-122">Die Prozedur besitzt zwei optionale Parameter.</span><span class="sxs-lookup"><span data-stu-id="0a719-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="0a719-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a719-123">See also</span></span>

- [<span data-ttu-id="0a719-124">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="0a719-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="0a719-125">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="0a719-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="0a719-126">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0a719-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
