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
ms.openlocfilehash: 8fc5d1afd9e9723e6b3c58e100b0519ef8fdfab4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968360"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="a8525-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8525-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="a8525-103">Gibt an, dass ein Prozedur Parameter ein optionales Array von Elementen vom angegebenen Typ annimmt.</span><span class="sxs-lookup"><span data-stu-id="a8525-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="a8525-104">`ParamArray`kann nur für den letzten Parameter einer Parameterliste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8525-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8525-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8525-105">Remarks</span></span>  
 <span data-ttu-id="a8525-106">`ParamArray`ermöglicht es Ihnen, eine beliebige Anzahl von Argumenten an die Prozedur zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="a8525-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="a8525-107">Ein `ParamArray` Parameter wird immer mit [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)deklariert.</span><span class="sxs-lookup"><span data-stu-id="a8525-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="a8525-108">Sie können ein oder mehrere Argumente für einen `ParamArray` Parameter angeben, indem Sie ein Array des entsprechenden Datentyps, eine durch Trennzeichen getrennte Liste von Werten oder überhaupt nichts übergeben.</span><span class="sxs-lookup"><span data-stu-id="a8525-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="a8525-109">Weitere Informationen finden Sie unter "Aufrufen eines ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="a8525-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a8525-110">Wenn Sie sich mit einem Array befassen, das unbegrenzt groß sein kann, besteht das Risiko, dass eine interne Kapazität der Anwendung überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="a8525-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="a8525-111">Wenn Sie ein Parameter Array aus dem aufrufenden Code akzeptieren, sollten Sie seine Länge testen und entsprechende Schritte ausführen, wenn es für Ihre Anwendung zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="a8525-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="a8525-112">Der `ParamArray`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a8525-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a8525-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8525-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="a8525-114">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8525-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a8525-115">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8525-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a8525-116">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8525-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8525-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8525-117">See also</span></span>

- [<span data-ttu-id="a8525-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a8525-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="a8525-119">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="a8525-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
