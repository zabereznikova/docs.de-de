---
title: Weitere Steuerungsstrukturen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09e59d25b3b2fc89026295e8500c30dad7b75086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="41936-102">Weitere Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41936-102">Other Control Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="41936-103">bietet Steuerungsstrukturen, mit denen Sie eine Ressource freigeben oder Reduzieren der Anzahl der müssen Sie einen Objektverweis zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="41936-103"> provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="41936-104">Verwenden von... Beenden Sie die Konstruktion verwenden</span><span class="sxs-lookup"><span data-stu-id="41936-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="41936-105">Die `Using...End Using` -Konstruktion erstellt einen Anweisungsblock, anhand derer Sie stellen, eine Ressource, z. B. eine SQL-Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="41936-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="41936-106">Sie können auch die Ressource mit dem Abrufen der `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="41936-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="41936-107">Wenn Sie beenden die `Using` Block [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwirft automatisch der Ressource, sodass sie von anderem Code zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="41936-107">When you exit the `Using` block, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="41936-108">Die Ressource muss es sich um lokale und verwerfbarer sein.</span><span class="sxs-lookup"><span data-stu-id="41936-108">The resource must be local and disposable.</span></span> <span data-ttu-id="41936-109">Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="41936-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="41936-110">Mit... Mit der Konstruktion enden</span><span class="sxs-lookup"><span data-stu-id="41936-110">With...End With Construction</span></span>  
 <span data-ttu-id="41936-111">Die `With...End With` Konstruktion können Sie einen Objektverweis einmal angegeben werden, und führen Sie dann eine Reihe von Anweisungen, die die Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="41936-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="41936-112">Dies kann Ihren Code vereinfachen und Leistung verbessern, da [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] muss nicht in der Referenz für jede Anweisung wiederherstellen können, die darauf zugreift.</span><span class="sxs-lookup"><span data-stu-id="41936-112">This can simplify your code and improve performance because [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="41936-113">Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="41936-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41936-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41936-114">See Also</span></span>  
 [<span data-ttu-id="41936-115">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="41936-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="41936-116">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="41936-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="41936-117">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="41936-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="41936-118">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="41936-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="41936-119">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="41936-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [<span data-ttu-id="41936-120">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="41936-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
