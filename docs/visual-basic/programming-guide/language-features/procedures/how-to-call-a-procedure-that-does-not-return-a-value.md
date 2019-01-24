---
title: 'Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert (Visual Basic) zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: f85c7a7edf4d05dc50166ad4f30080c2e595cf65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590642"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="7a316-102">Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert (Visual Basic) zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7a316-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="7a316-103">Ein `Sub` -Prozedur gibt keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="7a316-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="7a316-104">Sie rufen es explizit mit einer eigenständigen aufrufenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7a316-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="7a316-105">Sie können nicht sie aufrufen, indem Sie einfach den Namen in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7a316-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="7a316-106">Eine Sub-Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7a316-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="7a316-107">Geben Sie den Namen des der `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="7a316-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="7a316-108">Führen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="7a316-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7a316-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="7a316-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="7a316-110">Allerdings wird bei der Klammern verwenden die Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="7a316-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="7a316-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="7a316-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7a316-112">Werden Sie sicher, dass Sie die Argumente in der gleichen Reihenfolge angeben, die die `Sub` Prozedur definiert, die entsprechenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="7a316-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="7a316-113">Im folgenden Beispiel wird die Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Funktion, um ein Anwendungsfenster aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7a316-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="7a316-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> wird den Titel des Fensters als einziges Argument.</span><span class="sxs-lookup"><span data-stu-id="7a316-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="7a316-115">Es gibt einen Wert nicht an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="7a316-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="7a316-116">Wenn kein Editor-Prozess nicht ausgeführt wird, löst das Beispiel einer <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="7a316-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="7a316-117">Die `Shell` Verfahren wird davon ausgegangen, die Anwendungen, die in den Pfaden, die angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7a316-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7a316-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a316-118">See also</span></span>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="7a316-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7a316-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="7a316-120">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="7a316-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="7a316-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="7a316-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7a316-122">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7a316-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="7a316-123">Vorgehensweise: Erstellen Sie eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="7a316-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="7a316-124">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7a316-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="7a316-125">Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a316-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
