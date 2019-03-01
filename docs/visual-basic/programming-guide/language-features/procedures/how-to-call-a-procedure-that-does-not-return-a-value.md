---
title: 'Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert (Visual Basic) zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 899c33e6615e2979ba7abe0f537dbe05fd104beb
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965565"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="5cca0-102">Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert (Visual Basic) zurückgibt</span><span class="sxs-lookup"><span data-stu-id="5cca0-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="5cca0-103">Ein `Sub` -Prozedur gibt keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="5cca0-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="5cca0-104">Sie rufen es explizit mit einer eigenständigen aufrufenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5cca0-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="5cca0-105">Sie können nicht sie aufrufen, indem Sie einfach den Namen in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5cca0-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="5cca0-106">Eine Sub-Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5cca0-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="5cca0-107">Geben Sie den Namen des der `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="5cca0-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="5cca0-108">Führen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="5cca0-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="5cca0-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="5cca0-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="5cca0-110">Allerdings wird bei der Klammern verwenden die Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="5cca0-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="5cca0-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="5cca0-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="5cca0-112">Werden Sie sicher, dass Sie die Argumente in der gleichen Reihenfolge angeben, die die `Sub` Prozedur definiert, die entsprechenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="5cca0-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="5cca0-113">Im folgenden Beispiel wird die Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Funktion, um ein Anwendungsfenster aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5cca0-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="5cca0-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> wird den Titel des Fensters als einziges Argument.</span><span class="sxs-lookup"><span data-stu-id="5cca0-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="5cca0-115">Es gibt einen Wert nicht an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="5cca0-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="5cca0-116">Wenn kein Editor-Prozess nicht ausgeführt wird, löst das Beispiel einer <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="5cca0-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="5cca0-117">Die `Shell` Verfahren wird davon ausgegangen, die Anwendungen, die in den Pfaden, die angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5cca0-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="5cca0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cca0-118">See also</span></span>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="5cca0-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="5cca0-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5cca0-120">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5cca0-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="5cca0-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5cca0-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5cca0-122">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5cca0-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5cca0-123">Vorgehensweise: Erstellen Sie eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="5cca0-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="5cca0-124">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5cca0-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="5cca0-125">Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5cca0-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
