---
title: Division durch null (Visual Basic-Laufzeitfehler)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID11
ms.assetid: 5b9bc5d6-792e-48bc-a974-012e07ad95f3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9a913e3b55b38430c0908f77aac79cb342e78719
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="division-by-zero-visual-basic-run-time-error"></a><span data-ttu-id="ce780-102">Division durch null (Visual Basic-Laufzeitfehler)</span><span class="sxs-lookup"><span data-stu-id="ce780-102">Division by zero (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="ce780-103">Ein Ausdruck, der als Divisor verwendet wird, weist den Wert null auf.</span><span class="sxs-lookup"><span data-stu-id="ce780-103">An expression being used as a divisor has a value of zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce780-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ce780-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="ce780-105">Überprüfen Sie die Schreibweise der Variablen im Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ce780-105">Check the spelling of variables in the expression.</span></span> <span data-ttu-id="ce780-106">Ein falsch geschriebener Variablenname kann implizit eine numerische Variable erstellen, die mit 0 (null) initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="ce780-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
2.  <span data-ttu-id="ce780-107">Überprüfen Sie vorherige Vorgänge für Variablen im Ausdruck, insbesondere solche, die als Argumente aus anderen Prozeduren an die Prozedur übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ce780-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce780-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce780-108">See Also</span></span>  
 [<span data-ttu-id="ce780-109">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="ce780-109">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="ce780-110">Parameterübergabe Mechanismus Änderungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce780-110">Parameter Passing Mechanism Changes in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/0fa2b0dc-aa1c-4797-bbd6-aa13c611cab2)
