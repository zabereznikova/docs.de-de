---
title: Weitere Steuerungsstrukturen
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 8e7ca699e532ac7cfbe7918d850e7a28d1b27bcf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058611"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="f4472-102">Weitere Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4472-102">Other Control Structures (Visual Basic)</span></span>

<span data-ttu-id="f4472-103">Visual Basic bietet Steuerungsstrukturen, die Ihnen helfen, eine Ressource freizugeben, oder die Häufigkeit, mit der ein Objekt Verweis wiederholt werden muss.</span><span class="sxs-lookup"><span data-stu-id="f4472-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="f4472-104">Wird verwendet... Ende der Erstellung</span><span class="sxs-lookup"><span data-stu-id="f4472-104">Using...End Using Construction</span></span>  

 <span data-ttu-id="f4472-105">Bei der `Using...End Using` Erstellung wird ein Anweisungsblock erstellt, in dem Sie eine Ressource, z. b. eine SQL-Verbindung, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f4472-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="f4472-106">Optional können Sie die Ressource mit der- `Using` Anweisung abrufen.</span><span class="sxs-lookup"><span data-stu-id="f4472-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="f4472-107">Wenn Sie den- `Using` Block beenden, gibt Visual Basic die Ressource automatisch frei, sodass Sie für anderen zu verwendenden Code verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f4472-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="f4472-108">Die Ressource muss lokal und verwerfbar sein.</span><span class="sxs-lookup"><span data-stu-id="f4472-108">The resource must be local and disposable.</span></span> <span data-ttu-id="f4472-109">Weitere Informationen finden Sie unter [using-Anweisung](../../../language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4472-109">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="f4472-110">Mit... Mit Konstruktion beenden</span><span class="sxs-lookup"><span data-stu-id="f4472-110">With...End With Construction</span></span>  

 <span data-ttu-id="f4472-111">Mit der- `With...End With` Konstruktion können Sie einen Objekt Verweis einmal angeben und dann eine Reihe von-Anweisungen ausführen, die auf seine Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f4472-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="f4472-112">Dadurch können Sie Ihren Code vereinfachen und die Leistung verbessern, da Visual Basic den Verweis für jede Anweisung, die darauf zugreift, nicht erneut einrichten muss.</span><span class="sxs-lookup"><span data-stu-id="f4472-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="f4472-113">Weitere Informationen finden Sie unter [with... End with-Anweisung](../../../language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4472-113">For more information, see [With...End With Statement](../../../language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4472-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4472-114">See also</span></span>

- [<span data-ttu-id="f4472-115">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="f4472-115">Control Flow</span></span>](index.md)
- [<span data-ttu-id="f4472-116">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="f4472-116">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="f4472-117">Schleifenstrukturen</span><span class="sxs-lookup"><span data-stu-id="f4472-117">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="f4472-118">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="f4472-118">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="f4472-119">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f4472-119">Using Statement</span></span>](../../../language-reference/statements/using-statement.md)
- [<span data-ttu-id="f4472-120">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f4472-120">With...End With Statement</span></span>](../../../language-reference/statements/with-end-with-statement.md)
