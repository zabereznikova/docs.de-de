---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: baf9303101eea9eed27e8a4eee9e04d255c798e9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867828"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="c6123-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6123-102">ParamArray (Visual Basic)</span></span>

<span data-ttu-id="c6123-103">Gibt an, dass ein Prozedur Parameter ein optionales Array von Elementen vom angegebenen Typ annimmt.</span><span class="sxs-lookup"><span data-stu-id="c6123-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="c6123-104">`ParamArray` kann nur für den letzten Parameter einer Parameterliste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6123-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6123-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c6123-105">Remarks</span></span>  

 <span data-ttu-id="c6123-106">`ParamArray` ermöglicht es Ihnen, eine beliebige Anzahl von Argumenten an die Prozedur zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c6123-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="c6123-107">Ein `ParamArray` Parameter wird immer mit [ByVal](byval.md)deklariert.</span><span class="sxs-lookup"><span data-stu-id="c6123-107">A `ParamArray` parameter is always declared using [ByVal](byval.md).</span></span>  
  
 <span data-ttu-id="c6123-108">Sie können ein oder mehrere Argumente für einen Parameter angeben, `ParamArray` indem Sie ein Array des entsprechenden Datentyps, eine durch Trennzeichen getrennte Liste von Werten oder überhaupt nichts übergeben.</span><span class="sxs-lookup"><span data-stu-id="c6123-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="c6123-109">Weitere Informationen finden Sie unter "Aufrufen eines ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="c6123-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c6123-110">Wenn Sie sich mit einem Array befassen, das unbegrenzt groß sein kann, besteht das Risiko, dass eine interne Kapazität der Anwendung überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="c6123-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="c6123-111">Wenn Sie ein Parameter Array aus dem aufrufenden Code akzeptieren, sollten Sie seine Länge testen und entsprechende Schritte ausführen, wenn es für Ihre Anwendung zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="c6123-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="c6123-112">Der `ParamArray`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c6123-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c6123-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="c6123-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="c6123-114">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c6123-114">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="c6123-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="c6123-115">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="c6123-116">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c6123-116">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c6123-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6123-117">See also</span></span>

- [<span data-ttu-id="c6123-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c6123-118">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="c6123-119">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="c6123-119">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
