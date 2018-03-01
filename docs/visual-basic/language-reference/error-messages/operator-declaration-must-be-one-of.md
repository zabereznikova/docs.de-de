---
title: 'Operatordeklaration muss einer der: +,-, *,-, -, ^, &amp;, Like, Mod, und, oder Xor, nicht der Fall, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;= &gt; , &gt;= CType, IsTrue, IsFalse'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="5d29e-102">Operatordeklaration muss einer der: +,-, \*,\,/, ^, &amp;, Like, Mod, und, oder Xor, nicht der Fall, &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="5d29e-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="5d29e-103">Sie können nur einen Operator deklarieren, der für überladen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="5d29e-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="5d29e-104">Die folgende Tabelle enthält die Operatoren, die Sie deklarieren können.</span><span class="sxs-lookup"><span data-stu-id="5d29e-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="5d29e-105">Typ</span><span class="sxs-lookup"><span data-stu-id="5d29e-105">Type</span></span>|<span data-ttu-id="5d29e-106">Operatoren</span><span class="sxs-lookup"><span data-stu-id="5d29e-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="5d29e-107">Unär</span><span class="sxs-lookup"><span data-stu-id="5d29e-107">Unary</span></span>|<span data-ttu-id="5d29e-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="5d29e-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="5d29e-109">Binär</span><span class="sxs-lookup"><span data-stu-id="5d29e-109">Binary</span></span>|<span data-ttu-id="5d29e-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="5d29e-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="5d29e-111">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="5d29e-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="5d29e-112">Beachten Sie, dass die `=` in der Liste binärer Operator wird der Vergleichsoperator, der nicht der Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="5d29e-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="5d29e-113">**Fehler-ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="5d29e-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5d29e-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5d29e-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="5d29e-115">Wählen Sie einen Operator aus der Gruppe der überladbaren Operatoren aus.</span><span class="sxs-lookup"><span data-stu-id="5d29e-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="5d29e-116">Wenn Sie die Funktionalität des Überladens eines Operators benötigen, der nicht direkt überladen werden kann, erstellen Sie eine `Function` -Prozedur, die die entsprechenden Parameter übernimmt und den entsprechenden Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5d29e-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d29e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d29e-117">See Also</span></span>  
 [<span data-ttu-id="5d29e-118">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5d29e-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="5d29e-119">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="5d29e-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="5d29e-120">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="5d29e-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="5d29e-121">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="5d29e-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="5d29e-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5d29e-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
