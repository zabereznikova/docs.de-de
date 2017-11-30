---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="4557c-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4557c-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="4557c-103">Gibt an, dass ein Prozedurparameter, ein optionales Array von Elementen des angegebenen Typs akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4557c-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="4557c-104">`ParamArray`kann nur für den letzten Parameter einer Parameterliste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4557c-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4557c-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4557c-105">Remarks</span></span>  
 <span data-ttu-id="4557c-106">`ParamArray`können Sie eine beliebige Anzahl von Argumenten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="4557c-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="4557c-107">Ein `ParamArray` Parameter ist immer mit deklarierten [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="4557c-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="4557c-108">Sie können angeben, dass ein oder mehrere Argumente an eine `ParamArray` Parameter durch Übergeben eines Arrays der entsprechenden Daten eingeben, eine durch Trennzeichen getrennte Liste von Werten oder nichts an.</span><span class="sxs-lookup"><span data-stu-id="4557c-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="4557c-109">Weitere Informationen finden Sie unter "ParamArray aufrufen" in [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="4557c-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4557c-110">Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass einige interne Kapazität der Anwendung überschritten.</span><span class="sxs-lookup"><span data-stu-id="4557c-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="4557c-111">Wenn Sie ein Parameterarray des aufrufenden Codes akzeptieren, sollten Sie seine Länge testen und entsprechende Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="4557c-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="4557c-112">Der `ParamArray`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4557c-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4557c-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4557c-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="4557c-114">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4557c-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="4557c-115">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4557c-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="4557c-116">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4557c-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4557c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4557c-117">See Also</span></span>  
 [<span data-ttu-id="4557c-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4557c-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="4557c-119">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="4557c-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
