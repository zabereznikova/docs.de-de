---
title: 'Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 2686a4d9dc10cde209f558771feeb5ba4f4ccb21
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075004"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="be821-102">Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be821-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>

<span data-ttu-id="be821-103">Eine `Sub` Prozedur gibt keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="be821-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="be821-104">Sie rufen Sie explizit mit einer eigenständigen aufrufenden Anweisung auf.</span><span class="sxs-lookup"><span data-stu-id="be821-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="be821-105">Sie können ihn nicht durch einfaches Verwenden des Namens innerhalb eines Ausdrucks abrufen.</span><span class="sxs-lookup"><span data-stu-id="be821-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="be821-106">So wenden Sie eine unter Prozedur an</span><span class="sxs-lookup"><span data-stu-id="be821-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="be821-107">Geben Sie den Namen der `Sub` Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="be821-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="be821-108">Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="be821-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="be821-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="be821-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="be821-110">Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="be821-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="be821-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="be821-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="be821-112">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Sub` Prozedur die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="be821-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="be821-113">Im folgenden Beispiel wird die Visual Basic- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Funktion aufgerufen, um ein Anwendungsfenster zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="be821-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="be821-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> nimmt den Fenstertitel als einziges Argument an.</span><span class="sxs-lookup"><span data-stu-id="be821-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="be821-115">Er gibt keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="be821-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="be821-116">Wenn ein Notepad-Prozess nicht ausgeführt wird, wird im Beispiel eine ausgelöst <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="be821-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="be821-117">Die `Shell` Prozedur geht davon aus, dass sich die Anwendungen in den angegebenen Pfaden befinden.</span><span class="sxs-lookup"><span data-stu-id="be821-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="be821-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be821-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="be821-119">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="be821-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="be821-120">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="be821-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="be821-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="be821-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="be821-122">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="be821-122">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="be821-123">Vorgehensweise: Erstellen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="be821-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="be821-124">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="be821-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="be821-125">Gewusst wie: Aufrufen eines Ereignishandlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be821-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
