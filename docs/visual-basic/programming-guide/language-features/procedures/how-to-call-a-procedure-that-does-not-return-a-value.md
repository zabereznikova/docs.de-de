---
title: 'Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 3a5de98c6edf795a11bd9f0465aa6919f09eebfa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340962"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="0c7a1-102">Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c7a1-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="0c7a1-103">Eine `Sub` Prozedur gibt keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="0c7a1-104">Sie rufen Sie explizit mit einer eigenständigen aufrufenden Anweisung auf.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="0c7a1-105">Sie können ihn nicht durch einfaches Verwenden des Namens innerhalb eines Ausdrucks abrufen.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="0c7a1-106">So wenden Sie eine unter Prozedur an</span><span class="sxs-lookup"><span data-stu-id="0c7a1-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="0c7a1-107">Geben Sie den Namen der `Sub` Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="0c7a1-108">Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="0c7a1-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="0c7a1-110">Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="0c7a1-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="0c7a1-112">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Sub` Prozedur die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="0c7a1-113">Im folgenden Beispiel wird die Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>-Funktion aufgerufen, um ein Anwendungsfenster zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="0c7a1-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> nimmt den Fenstertitel als einziges Argument an.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="0c7a1-115">Er gibt keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="0c7a1-116">Wenn ein Notepad-Prozess nicht ausgeführt wird, löst das Beispiel eine <xref:System.ArgumentException>aus.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="0c7a1-117">Bei der `Shell` Prozedur wird davon ausgegangen, dass sich die Anwendungen in den angegebenen Pfaden befinden.</span><span class="sxs-lookup"><span data-stu-id="0c7a1-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="0c7a1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c7a1-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="0c7a1-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0c7a1-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="0c7a1-120">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0c7a1-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="0c7a1-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0c7a1-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0c7a1-122">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0c7a1-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="0c7a1-123">Gewusst wie: Erstellen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="0c7a1-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="0c7a1-124">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="0c7a1-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="0c7a1-125">Gewusst wie: Abrufen eines Ereignis Handlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c7a1-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
