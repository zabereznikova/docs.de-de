---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: 16a69e547d14c619d427aa8860e9bf4002b6db04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703600"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="20977-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20977-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="20977-103">Gibt an, dass ein Prozedurparameter ein optionales Array von Elementen des angegebenen Typs akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="20977-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="20977-104">`ParamArray` kann nur auf einer Parameterliste der letzte Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20977-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20977-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20977-105">Remarks</span></span>  
 <span data-ttu-id="20977-106">`ParamArray` können Sie eine beliebige Anzahl von Argumenten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="20977-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="20977-107">Ein `ParamArray` Parameter wird immer mit deklariert [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="20977-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="20977-108">Sie können angeben, dass eine oder mehrere Argumente für eine `ParamArray` durch Übergeben eines Arrays des entsprechenden Typparameter, eine durch Trennzeichen getrennte Liste von Werten oder "nothing" überhaupt.</span><span class="sxs-lookup"><span data-stu-id="20977-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="20977-109">Weitere Informationen finden Sie unter "ParamArray aufrufen" in [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="20977-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20977-110">Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass die interne Kapazität der Anwendung überschritten.</span><span class="sxs-lookup"><span data-stu-id="20977-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="20977-111">Wenn Sie ein Parameterarray vom aufrufenden Code akzeptieren, sollten Sie testen ihre Länge und geeignete Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="20977-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="20977-112">Der `ParamArray`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="20977-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="20977-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20977-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="20977-114">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20977-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="20977-115">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20977-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="20977-116">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20977-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="20977-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20977-117">See also</span></span>
- [<span data-ttu-id="20977-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="20977-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="20977-119">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="20977-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
