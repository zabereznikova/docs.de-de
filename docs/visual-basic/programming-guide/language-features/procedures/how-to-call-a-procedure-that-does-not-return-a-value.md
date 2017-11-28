---
title: "Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bbea50132d1110b38bf9b01397795a2cd51f86d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="8e417-102">Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e417-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="8e417-103">Ein `Sub` Prozedur wird einen Wert nicht an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8e417-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="8e417-104">Sie rufen es explizit mit einer eigenständigen aufrufende Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8e417-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="8e417-105">Sie können keine es einfach mit seinen Namen innerhalb eines Ausdrucks aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8e417-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="8e417-106">Zum Aufrufen einer Subprozedur</span><span class="sxs-lookup"><span data-stu-id="8e417-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="8e417-107">Geben Sie den Namen des der `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8e417-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="8e417-108">Führen Sie den Namen der Prozedur mit Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="8e417-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="8e417-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="8e417-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="8e417-110">Allerdings besser mit den Klammern Code lesen.</span><span class="sxs-lookup"><span data-stu-id="8e417-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="8e417-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="8e417-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="8e417-112">Achten Sie darauf geben Sie die Argumente in der gleichen Reihenfolge, die die `Sub` Prozedur definiert, die entsprechenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="8e417-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="8e417-113">Im folgenden Beispiel wird die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Funktion, um ein Anwendungsfenster aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8e417-113">The following example calls the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="8e417-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>wird den Titel des Fensters als einziges Argument.</span><span class="sxs-lookup"><span data-stu-id="8e417-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="8e417-115">Es gibt einen Wert nicht an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="8e417-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="8e417-116">Wenn kein Editor-Prozess nicht ausgeführt wird, löst das Beispiel ein <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="8e417-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="8e417-117">Die `Shell` Verfahren wird davon ausgegangen, die Anwendungen, die in den Pfaden, die angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8e417-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8e417-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e417-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [<span data-ttu-id="8e417-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8e417-119">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8e417-120">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="8e417-120">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="8e417-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="8e417-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8e417-122">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8e417-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="8e417-123">Gewusst wie: Erstellen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="8e417-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="8e417-124">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="8e417-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="8e417-125">Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e417-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
