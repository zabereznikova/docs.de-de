---
title: 'Operatordeklaration muss eine der: +,-, *, /, ^, &amp;, Like, Mod, und, Or, Xor, nicht der Fall, <<>> ",", =, <>, <, < =, >, > =, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 4283547109ec312cc4fe07a054bbb8db3bff660f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299188"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="cf284-102">Operatordeklaration muss eine der: +,-, \*,\,/, ^, &amp;, Like, Mod, und, Or, Xor, nicht der Fall, \< \<, >>...</span><span class="sxs-lookup"><span data-stu-id="cf284-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="cf284-103">Sie können nur einen Operator deklarieren, der für überladen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="cf284-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="cf284-104">Die folgende Tabelle enthält die Operatoren, die Sie deklarieren können.</span><span class="sxs-lookup"><span data-stu-id="cf284-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="cf284-105">Typ</span><span class="sxs-lookup"><span data-stu-id="cf284-105">Type</span></span>|<span data-ttu-id="cf284-106">Operatoren</span><span class="sxs-lookup"><span data-stu-id="cf284-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="cf284-107">Unär</span><span class="sxs-lookup"><span data-stu-id="cf284-107">Unary</span></span>|<span data-ttu-id="cf284-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="cf284-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="cf284-109">Binär</span><span class="sxs-lookup"><span data-stu-id="cf284-109">Binary</span></span>|<span data-ttu-id="cf284-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="cf284-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="cf284-111">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="cf284-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="cf284-112">Beachten Sie, dass die `=` Operator in der binären Liste wird der Vergleichsoperator, der nicht der Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="cf284-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="cf284-113">**Fehler-ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="cf284-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf284-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cf284-114">To correct this error</span></span>  
  
1. <span data-ttu-id="cf284-115">Wählen Sie einen Operator aus der Gruppe der überladbaren Operatoren aus.</span><span class="sxs-lookup"><span data-stu-id="cf284-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="cf284-116">Wenn Sie die Funktionalität des Überladens eines Operators benötigen, der nicht direkt überladen werden kann, erstellen Sie eine `Function` -Prozedur, die die entsprechenden Parameter übernimmt und den entsprechenden Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="cf284-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf284-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf284-117">See also</span></span>

- [<span data-ttu-id="cf284-118">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cf284-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="cf284-119">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="cf284-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="cf284-120">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="cf284-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="cf284-121">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="cf284-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="cf284-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cf284-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
