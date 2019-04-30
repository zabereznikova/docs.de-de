---
title: Weitere Steuerungsstrukturen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c42070ce2ea866e59e1b2e190f7c05e1ee7cc922
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907841"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="c8930-102">Weitere Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8930-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="c8930-103">Visual Basic bietet Steuerungsstrukturen, die Ihnen helfen, einer Ressource zu verwerfen, oder verringern Sie die Anzahl wie oft Sie einen Objektverweis zu wiederholen müssen.</span><span class="sxs-lookup"><span data-stu-id="c8930-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="c8930-104">Verwenden von... Beenden Sie die Konstruktion verwenden</span><span class="sxs-lookup"><span data-stu-id="c8930-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="c8930-105">Die `Using...End Using` Konstruktion erstellt einen Anweisungsblock, die in dem Sie vornehmen einer Ressource, z. B. eine SQL-Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8930-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="c8930-106">Sie können auch die Ressource mit dem Abrufen der `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c8930-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="c8930-107">Wenn Sie beenden die `Using` Block, Visual Basic automatisch gibt die Ressource frei, damit es von anderem Code zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="c8930-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="c8930-108">Die Ressource muss es sich um lokale und verwerfbarer sein.</span><span class="sxs-lookup"><span data-stu-id="c8930-108">The resource must be local and disposable.</span></span> <span data-ttu-id="c8930-109">Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8930-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="c8930-110">Mit... Enden mit der Konstruktion</span><span class="sxs-lookup"><span data-stu-id="c8930-110">With...End With Construction</span></span>  
 <span data-ttu-id="c8930-111">Die `With...End With` Konstruktion können Sie einen Objektverweis einmal angeben und führen Sie dann eine Reihe von Anweisungen, die auf seine Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c8930-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="c8930-112">Ihren Code vereinfachen Sie können und Leistung verbessern, da Visual Basic nicht verfügt, um den Verweis für jede Anweisung wiederherzustellen, die darauf zugreift.</span><span class="sxs-lookup"><span data-stu-id="c8930-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="c8930-113">Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8930-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8930-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8930-114">See also</span></span>

- [<span data-ttu-id="c8930-115">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="c8930-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="c8930-116">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="c8930-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="c8930-117">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="c8930-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="c8930-118">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="c8930-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="c8930-119">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c8930-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
- [<span data-ttu-id="c8930-120">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c8930-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
