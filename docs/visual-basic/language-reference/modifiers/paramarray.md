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
ms.openlocfilehash: be8ddb7f9ba08535d12890d1c5c82a9b7b485f3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597359"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="aef27-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aef27-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="aef27-103">Gibt an, dass ein Prozedurparameter, ein optionales Array von Elementen des angegebenen Typs akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="aef27-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="aef27-104">`ParamArray` kann nur für den letzten Parameter einer Parameterliste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aef27-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aef27-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aef27-105">Remarks</span></span>  
 <span data-ttu-id="aef27-106">`ParamArray` können Sie eine beliebige Anzahl von Argumenten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="aef27-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="aef27-107">Ein `ParamArray` Parameter ist immer mit deklarierten [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="aef27-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="aef27-108">Sie können angeben, dass ein oder mehrere Argumente an eine `ParamArray` Parameter durch Übergeben eines Arrays der entsprechenden Daten eingeben, eine durch Trennzeichen getrennte Liste von Werten oder nichts an.</span><span class="sxs-lookup"><span data-stu-id="aef27-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="aef27-109">Weitere Informationen finden Sie unter "ParamArray aufrufen" in [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="aef27-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aef27-110">Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass einige interne Kapazität der Anwendung überschritten.</span><span class="sxs-lookup"><span data-stu-id="aef27-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="aef27-111">Wenn Sie ein Parameterarray des aufrufenden Codes akzeptieren, sollten Sie seine Länge testen und entsprechende Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="aef27-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="aef27-112">Der `ParamArray`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="aef27-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="aef27-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aef27-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="aef27-114">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aef27-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="aef27-115">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aef27-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="aef27-116">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aef27-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="aef27-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aef27-117">See Also</span></span>  
 [<span data-ttu-id="aef27-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="aef27-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="aef27-119">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="aef27-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
