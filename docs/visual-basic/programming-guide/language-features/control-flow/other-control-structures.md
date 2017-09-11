---
title: Weitere Steuerungsstrukturen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8f8bd57f193be0d7f410f7325355ffc47ab10e3f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="0d980-102">Weitere Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d980-102">Other Control Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0d980-103">bietet Steuerungsstrukturen, mit denen Sie eine Ressource freigeben oder Reduzieren der Anzahl der müssen Sie einen Objektverweis zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="0d980-103"> provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="0d980-104">Verwenden von... End Using-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="0d980-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="0d980-105">Die `Using...End Using` -Konstruktion erstellt einen Anweisungsblock, in dem Sie vornehmen, einer Ressource, z. B. eine SQL-Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d980-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="0d980-106">Sie können auch die Ressource mit dem Abrufen der `Using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0d980-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="0d980-107">Wenn Sie schließen die `Using` Block [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatisch gibt die Ressource frei, damit er für anderen Code für die Verwendung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0d980-107">When you exit the `Using` block, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="0d980-108">Die Ressource muss es sich um lokale und freigegeben sein.</span><span class="sxs-lookup"><span data-stu-id="0d980-108">The resource must be local and disposable.</span></span> <span data-ttu-id="0d980-109">Weitere Informationen finden Sie unter [Using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0d980-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="0d980-110">Mit... Endet mit der Konstruktion</span><span class="sxs-lookup"><span data-stu-id="0d980-110">With...End With Construction</span></span>  
 <span data-ttu-id="0d980-111">Die `With...End With` Konstruktion können Sie einmal einen Objektverweis angeben und führen Sie dann eine Reihe von Anweisungen, die auf Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0d980-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="0d980-112">Dies kann Ihren Code vereinfachen und Leistung verbessern, da [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keinen den Verweis für jede Anweisung, die darauf zugreift, erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d980-112">This can simplify your code and improve performance because [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="0d980-113">Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0d980-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d980-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d980-114">See Also</span></span>  
 <span data-ttu-id="0d980-115">[Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d980-115">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="0d980-116"> [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="0d980-116"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="0d980-117"> [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="0d980-117"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="0d980-118"> [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="0d980-118"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="0d980-119"> [Using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0d980-119"> [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md) </span></span>  
<span data-ttu-id="0d980-120"> [With...End With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="0d980-120"> [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>
