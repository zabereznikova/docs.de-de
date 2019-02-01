---
title: 'Vorgehensweise: Protokollieren von Ausnahmen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: ea2cad121a6722b2cb59e29831f90648ad4cff78
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664693"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="a98fb-102">Vorgehensweise: Protokollieren von Ausnahmen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a98fb-102">How to: Log Exceptions in Visual Basic</span></span>
<span data-ttu-id="a98fb-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen zu Ausnahmen zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="a98fb-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="a98fb-104">In diesen Beispielen wird gezeigt, wie Sie die `My.Application.Log.WriteException`-Methode verwenden können, um Ausnahmen zu protokollieren, die Sie explizit abfangen bzw. die unbehandelt sind.</span><span class="sxs-lookup"><span data-stu-id="a98fb-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="a98fb-105">Verwenden Sie für die Protokollierung von Nachverfolgungsinformationen die Methode `My.Application.Log.WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="a98fb-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="a98fb-106">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="a98fb-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="a98fb-107">Protokollieren einer behandelten Ausnahme</span><span class="sxs-lookup"><span data-stu-id="a98fb-107">To log a handled exception</span></span>  
  
1.  <span data-ttu-id="a98fb-108">Erstellen Sie die Methode, die die Ausnahmeinformationen generiert.</span><span class="sxs-lookup"><span data-stu-id="a98fb-108">Create the method that will generate the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  <span data-ttu-id="a98fb-109">Verwenden Sie einen `Try...Catch`-Block, um die Ausnahme abzufangen.</span><span class="sxs-lookup"><span data-stu-id="a98fb-109">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  <span data-ttu-id="a98fb-110">Fügen Sie den Code, der eine Ausnahme generieren kann, in den `Try`-Block ein.</span><span class="sxs-lookup"><span data-stu-id="a98fb-110">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="a98fb-111">Heben Sie die Auskommentierung der Zeilen `Dim` und `MsgBox` auf, um eine <xref:System.NullReferenceException>-Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="a98fb-111">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  <span data-ttu-id="a98fb-112">Verwenden Sie im `Catch`-Block die `My.Application.Log.WriteException`-Methode, um die Ausnahmeinformationen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a98fb-112">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     <span data-ttu-id="a98fb-113">Das folgende Beispiel zeigt den vollständigen Code für das Protokollieren einer behandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a98fb-113">The following example shows the complete code for logging a handled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="a98fb-114">Protokollieren einer nicht behandelten Ausnahme</span><span class="sxs-lookup"><span data-stu-id="a98fb-114">To log an unhandled exception</span></span>  
  
1.  <span data-ttu-id="a98fb-115">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="a98fb-115">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a98fb-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a98fb-116">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="a98fb-117">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="a98fb-117">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="a98fb-118">Klicken Sie auf die Schaltfläche **Anwendungsereignisse anzeigen** um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a98fb-118">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="a98fb-119">Dadurch wird die Datei "ApplicationEvents.vb" geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a98fb-119">This opens the ApplicationEvents.vb file.</span></span>  
  
4.  <span data-ttu-id="a98fb-120">Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="a98fb-120">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="a98fb-121">Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.</span><span class="sxs-lookup"><span data-stu-id="a98fb-121">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5.  <span data-ttu-id="a98fb-122">Wählen Sie im Menü **Deklarationen** den Eintrag **UnhandledException** aus.</span><span class="sxs-lookup"><span data-stu-id="a98fb-122">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="a98fb-123">Die Anwendung löst das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> aus, bevor die Hauptanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a98fb-123">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6.  <span data-ttu-id="a98fb-124">Fügen Sie die Methode `My.Application.Log.WriteException` zum `UnhandledException` -Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="a98fb-124">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     <span data-ttu-id="a98fb-125">Das folgende Beispiel zeigt den vollständigen Code für das Protokollieren einer nicht behandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a98fb-125">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a98fb-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a98fb-126">See also</span></span>
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="a98fb-127">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="a98fb-127">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="a98fb-128">Vorgehensweise: Schreiben von Protokollmeldungen</span><span class="sxs-lookup"><span data-stu-id="a98fb-128">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [<span data-ttu-id="a98fb-129">Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="a98fb-129">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="a98fb-130">Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="a98fb-130">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
