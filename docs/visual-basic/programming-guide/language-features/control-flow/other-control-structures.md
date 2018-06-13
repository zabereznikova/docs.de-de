---
title: Weitere Steuerungsstrukturen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 272ebcf0639b83a51e87de5ebbf93d7e750c03a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654108"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="be9c8-102">Weitere Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be9c8-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="be9c8-103">Visual Basic bietet Steuerungsstrukturen, mit denen Sie eine Ressource freigeben oder Reduzieren der Anzahl der müssen Sie einen Objektverweis zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="be9c8-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="be9c8-104">Verwenden von... Beenden Sie die Konstruktion verwenden</span><span class="sxs-lookup"><span data-stu-id="be9c8-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="be9c8-105">Die `Using...End Using` -Konstruktion erstellt einen Anweisungsblock, anhand derer Sie stellen, eine Ressource, z. B. eine SQL-Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="be9c8-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="be9c8-106">Sie können auch die Ressource mit dem Abrufen der `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="be9c8-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="be9c8-107">Wenn Sie beenden die `Using` Visual Basic-Block wird automatisch der Ressource frei, damit es von anderem Code zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="be9c8-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="be9c8-108">Die Ressource muss es sich um lokale und verwerfbarer sein.</span><span class="sxs-lookup"><span data-stu-id="be9c8-108">The resource must be local and disposable.</span></span> <span data-ttu-id="be9c8-109">Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="be9c8-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="be9c8-110">Mit... Mit der Konstruktion enden</span><span class="sxs-lookup"><span data-stu-id="be9c8-110">With...End With Construction</span></span>  
 <span data-ttu-id="be9c8-111">Die `With...End With` Konstruktion können Sie einen Objektverweis einmal angegeben werden, und führen Sie dann eine Reihe von Anweisungen, die die Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="be9c8-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="be9c8-112">Ihren Code vereinfachen Sie können und Leistung verbessern, da Visual Basic nicht unbedingt den Verweis für jede Anweisung wiederherstellen können, die darauf zugreift.</span><span class="sxs-lookup"><span data-stu-id="be9c8-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="be9c8-113">Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="be9c8-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be9c8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be9c8-114">See Also</span></span>  
 [<span data-ttu-id="be9c8-115">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="be9c8-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="be9c8-116">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="be9c8-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="be9c8-117">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="be9c8-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="be9c8-118">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="be9c8-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="be9c8-119">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="be9c8-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [<span data-ttu-id="be9c8-120">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="be9c8-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
