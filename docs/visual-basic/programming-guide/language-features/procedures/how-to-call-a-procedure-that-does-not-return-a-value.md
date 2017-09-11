---
title: "Gewusst wie: Aufrufen einer Prozedur, die keinen Wert (Visual Basic) zurückgibt | Microsoft-Dokumentation"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
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
ms.openlocfilehash: 26120b763d2ecedb3aa43adb08e4c87c2b1e0be1
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="8b3fc-102">Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b3fc-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="8b3fc-103">Ein `Sub` -Prozedur gibt keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="8b3fc-104">Sie rufen es explizit mit einer eigenständigen aufrufenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="8b3fc-105">Sie können nicht sie aufrufen, indem Sie einfach den Namen in einen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="8b3fc-106">Eine Subprozedur aufrufen</span><span class="sxs-lookup"><span data-stu-id="8b3fc-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="8b3fc-107">Geben Sie den Namen der `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="8b3fc-108">Führen Sie den Namen der Prozedur mit Klammern um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="8b3fc-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="8b3fc-110">Allerdings vereinfacht die Verwendung der Klammern Code leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="8b3fc-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="8b3fc-112">Stellen Sie sicher, geben Sie die Argumente in der gleichen Reihenfolge, die `Sub` -Prozedur die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="8b3fc-113">Im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>Funktion, um ein Anwendungsfenster aktiviert.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="8b3fc-113">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="8b3fc-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>erfordert den Fenstertitel als einziges Argument.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="8b3fc-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="8b3fc-115">Es keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="8b3fc-116">Wenn kein Editor-Prozess nicht ausgeführt wird, löst das Beispiel eine <xref:System.ArgumentException>.</xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="8b3fc-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="8b3fc-117">Die `Shell` Verfahren wird davon ausgegangen, die in den Pfaden angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     <span data-ttu-id="8b3fc-118">[!code-vb[VbVbalrCatRef&#11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b3fc-118">[!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3fc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b3fc-119">See Also</span></span>  
 <span data-ttu-id="8b3fc-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A></span><span class="sxs-lookup"><span data-stu-id="8b3fc-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></span></span>   
 <span data-ttu-id="8b3fc-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="8b3fc-121"><xref:System.ArgumentException></span></span>   
<span data-ttu-id="8b3fc-122"> [Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="8b3fc-122"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="8b3fc-123"> [Sub-Prozeduren](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8b3fc-123"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="8b3fc-124"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="8b3fc-124"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="8b3fc-125"> [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8b3fc-125"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="8b3fc-126"> [Gewusst wie: Erstellen einer Prozedur](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="8b3fc-126"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="8b3fc-127"> [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="8b3fc-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="8b3fc-128"> [Gewusst wie: Aufrufen von einem Ereignishandler in Visual Basic](./how-to-call-an-event-handler.md)</span><span class="sxs-lookup"><span data-stu-id="8b3fc-128"> [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)</span></span>
