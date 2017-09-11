---
title: 'Gewusst wie: Protokollieren von Ausnahmen in Visual Basic'
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
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: adf2dc683a139d21f24379efc779d4510a2057eb
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="9cfd3-102">Gewusst wie: Protokollieren von Ausnahmen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9cfd3-102">How to: Log Exceptions in Visual Basic</span></span>
<span data-ttu-id="9cfd3-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen zu Ausnahmen zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="9cfd3-104">In diesen Beispielen wird gezeigt, wie Sie die `My.Application.Log.WriteException`-Methode verwenden können, um Ausnahmen zu protokollieren, die Sie explizit abfangen bzw. die unbehandelt sind.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="9cfd3-105">Verwenden Sie für die Protokollierung von Nachverfolgungsinformationen die Methode `My.Application.Log.WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="9cfd3-106">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="9cfd3-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="9cfd3-107">Protokollieren einer behandelten Ausnahme</span><span class="sxs-lookup"><span data-stu-id="9cfd3-107">To log a handled exception</span></span>  
  
1.  <span data-ttu-id="9cfd3-108">Erstellen Sie die Methode, die die Ausnahmeinformationen generiert.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-108">Create the method that will generate the exception information.</span></span>  
  
     <span data-ttu-id="9cfd3-109">[!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9cfd3-109">[!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]</span></span>  
  
2.  <span data-ttu-id="9cfd3-110">Verwenden Sie einen `Try...Catch`-Block, um die Ausnahme abzufangen.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-110">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     <span data-ttu-id="9cfd3-111">[!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="9cfd3-111">[!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]</span></span>  
  
3.  <span data-ttu-id="9cfd3-112">Fügen Sie den Code, der eine Ausnahme generieren kann, in den `Try`-Block ein.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-112">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="9cfd3-113">Heben Sie die Auskommentierung der Zeilen `Dim` und `MsgBox` auf, um eine <xref:System.NullReferenceException>-Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-113">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     <span data-ttu-id="9cfd3-114">[!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="9cfd3-114">[!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]</span></span>  
  
4.  <span data-ttu-id="9cfd3-115">Verwenden Sie im `Catch`-Block die `My.Application.Log.WriteException`-Methode, um die Ausnahmeinformationen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-115">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     <span data-ttu-id="9cfd3-116">[!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="9cfd3-116">[!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]</span></span>  
  
     <span data-ttu-id="9cfd3-117">Das folgende Beispiel zeigt den vollständigen Code für das Protokollieren einer behandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-117">The following example shows the complete code for logging a handled exception.</span></span>  
  
     <span data-ttu-id="9cfd3-118">[!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="9cfd3-118">[!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]</span></span>  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="9cfd3-119">Protokollieren einer nicht behandelten Ausnahme</span><span class="sxs-lookup"><span data-stu-id="9cfd3-119">To log an unhandled exception</span></span>  
  
1.  <span data-ttu-id="9cfd3-120">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9cfd3-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-121">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="9cfd3-122">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="9cfd3-122">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="9cfd3-123">Klicken Sie auf die Schaltfläche **Anwendungsereignisse anzeigen** um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-123">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="9cfd3-124">Dadurch wird die Datei "ApplicationEvents.vb" geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-124">This opens the ApplicationEvents.vb file.</span></span>  
  
4.  <span data-ttu-id="9cfd3-125">Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-125">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="9cfd3-126">Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-126">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5.  <span data-ttu-id="9cfd3-127">Wählen Sie im Menü **Deklarationen** den Eintrag **UnhandledException** aus.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-127">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="9cfd3-128">Die Anwendung löst das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> aus, bevor die Hauptanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-128">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6.  <span data-ttu-id="9cfd3-129">Fügen Sie die Methode `My.Application.Log.WriteException` zum `UnhandledException` -Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-129">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     <span data-ttu-id="9cfd3-130">[!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="9cfd3-130">[!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]</span></span>  
  
     <span data-ttu-id="9cfd3-131">Das folgende Beispiel zeigt den vollständigen Code für das Protokollieren einer nicht behandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="9cfd3-131">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     <span data-ttu-id="9cfd3-132">[!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="9cfd3-132">[!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cfd3-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cfd3-133">See Also</span></span>  
 <span data-ttu-id="9cfd3-134"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9cfd3-134"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="9cfd3-135"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="9cfd3-135"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="9cfd3-136"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="9cfd3-136"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="9cfd3-137">[Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="9cfd3-137">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="9cfd3-138">[Vorgehensweise: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9cfd3-138">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="9cfd3-139">[Walkthrough: Determining Where My.Application.Log Writes Information (Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt)](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="9cfd3-139">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 [<span data-ttu-id="9cfd3-140">Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="9cfd3-140">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

