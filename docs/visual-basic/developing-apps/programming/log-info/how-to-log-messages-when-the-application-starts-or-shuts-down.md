---
title: 'Vorgehensweise: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event [Visual Basic]
- event logs, startup
- Shutdown event [Visual Basic]
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
ms.openlocfilehash: 19cfc4d8104ce3575bf9355f750bdb4616450743
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835769"
---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a><span data-ttu-id="e33d2-102">Vorgehensweise: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e33d2-102">How to: Log Messages When the Application Starts or Shuts Down (Visual Basic)</span></span>
<span data-ttu-id="e33d2-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="e33d2-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="e33d2-104">Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry` -Methode mit den Ereignissen `Startup` und `Shutdown` zum Erfassen von Ablaufverfolgungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="e33d2-104">This example shows how to use the `My.Application.Log.WriteEntry` method with the `Startup` and `Shutdown` events to write tracing information.</span></span>  
  
### <a name="to-access-the-applications-event-handler-code"></a><span data-ttu-id="e33d2-105">Zugriff auf den Code des Ereignishandlers der Anwendung</span><span class="sxs-lookup"><span data-stu-id="e33d2-105">To access the application's event-handler code</span></span>  
  
1.  <span data-ttu-id="e33d2-106">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e33d2-106">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e33d2-107">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e33d2-107">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="e33d2-108">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="e33d2-108">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="e33d2-109">Klicken Sie auf die Schaltfläche **Anwendungsereignisse anzeigen** um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e33d2-109">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="e33d2-110">Dadurch wird die Datei "ApplicationEvents.vb" geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e33d2-110">This opens the ApplicationEvents.vb file.</span></span>  
  
### <a name="to-log-messages-when-the-application-starts"></a><span data-ttu-id="e33d2-111">Protokollieren von Meldungen beim Starten der Anwendung</span><span class="sxs-lookup"><span data-stu-id="e33d2-111">To log messages when the application starts</span></span>  
  
1.  <span data-ttu-id="e33d2-112">Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="e33d2-112">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="e33d2-113">Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.</span><span class="sxs-lookup"><span data-stu-id="e33d2-113">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2.  <span data-ttu-id="e33d2-114">Wählen Sie im Menü **Deklarationen** den Eintrag **Start**aus.</span><span class="sxs-lookup"><span data-stu-id="e33d2-114">On the **Declarations** menu, choose **Startup**.</span></span>  
  
     <span data-ttu-id="e33d2-115">Die Anwendung löst das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> aus, bevor die Hauptanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e33d2-115">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> event before the main application runs.</span></span>  
  
3.  <span data-ttu-id="e33d2-116">Fügen Sie die Methode `My.Application.Log.WriteEntry` zum `Startup` -Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="e33d2-116">Add the `My.Application.Log.WriteEntry` method to the `Startup` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#1)]  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a><span data-ttu-id="e33d2-117">Protokollieren von Meldungen beim Herunterfahren der Anwendung</span><span class="sxs-lookup"><span data-stu-id="e33d2-117">To log messages when the application shuts down</span></span>  
  
1.  <span data-ttu-id="e33d2-118">Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="e33d2-118">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="e33d2-119">Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.</span><span class="sxs-lookup"><span data-stu-id="e33d2-119">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2.  <span data-ttu-id="e33d2-120">Wählen Sie im Menü **Deklarationen** den Eintrag **Herunterfahren**aus.</span><span class="sxs-lookup"><span data-stu-id="e33d2-120">On the **Declarations** menu, choose **Shutdown**.</span></span>  
  
     <span data-ttu-id="e33d2-121">Die Anwendung löst das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> -Ereignis aus, wenn der Hauptthread der Anwendung ausgeführt wird, jedoch bevor er heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="e33d2-121">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> event after the main application runs, but before it shuts down.</span></span>  
  
3.  <span data-ttu-id="e33d2-122">Fügen Sie die Methode `My.Application.Log.WriteEntry` zum `Shutdown` -Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="e33d2-122">Add the `My.Application.Log.WriteEntry` method to the `Shutdown` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="e33d2-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e33d2-123">Example</span></span>  
 <span data-ttu-id="e33d2-124">Sie können den **Projekt-Designer** verwenden, um auf die Anwendungsereignisse im Code-Editor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e33d2-124">You can use the **Project Designer** to access the application events in the Code Editor.</span></span> <span data-ttu-id="e33d2-125">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e33d2-125">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 [!code-vb[VbVbalrMyApplicationLog#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e33d2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e33d2-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="e33d2-127">Seite „Anwendung“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e33d2-127">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="e33d2-128">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="e33d2-128">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
