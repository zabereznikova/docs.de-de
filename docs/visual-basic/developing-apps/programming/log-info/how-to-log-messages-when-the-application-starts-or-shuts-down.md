---
title: 'Gewusst wie: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung (Visual Basic)'
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
- event logs, shutdown
- My.Application.Log object, logging
- Startup event
- event logs, startup
- Shutdown event
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fa5bf57ac5245e9363089b85607b7e6d1a00ba14
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a><span data-ttu-id="8c93f-102">Gewusst wie: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c93f-102">How to: Log Messages When the Application Starts or Shuts Down (Visual Basic)</span></span>
<span data-ttu-id="8c93f-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="8c93f-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="8c93f-104">Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry` -Methode mit den Ereignissen `Startup` und `Shutdown` zum Erfassen von Ablaufverfolgungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="8c93f-104">This example shows how to use the `My.Application.Log.WriteEntry` method with the `Startup` and `Shutdown` events to write tracing information.</span></span>  
  
### <a name="to-access-the-applications-event-handler-code"></a><span data-ttu-id="8c93f-105">Zugriff auf den Code des Ereignishandlers der Anwendung</span><span class="sxs-lookup"><span data-stu-id="8c93f-105">To access the application's event-handler code</span></span>  
  
1.  <span data-ttu-id="8c93f-106">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="8c93f-106">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8c93f-107">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8c93f-107">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="8c93f-108">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="8c93f-108">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="8c93f-109">Klicken Sie auf die Schaltfläche **Anwendungsereignisse anzeigen** um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8c93f-109">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="8c93f-110">Dadurch wird die Datei "ApplicationEvents.vb" geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8c93f-110">This opens the ApplicationEvents.vb file.</span></span>  
  
### <a name="to-log-messages-when-the-application-starts"></a><span data-ttu-id="8c93f-111">Protokollieren von Meldungen beim Starten der Anwendung</span><span class="sxs-lookup"><span data-stu-id="8c93f-111">To log messages when the application starts</span></span>  
  
1.  <span data-ttu-id="8c93f-112">Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="8c93f-112">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="8c93f-113">Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.</span><span class="sxs-lookup"><span data-stu-id="8c93f-113">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2.  <span data-ttu-id="8c93f-114">Wählen Sie im Menü **Deklarationen** den Eintrag **Start**aus.</span><span class="sxs-lookup"><span data-stu-id="8c93f-114">On the **Declarations** menu, choose **Startup**.</span></span>  
  
     <span data-ttu-id="8c93f-115">Die Anwendung löst das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> aus, bevor die Hauptanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c93f-115">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> event before the main application runs.</span></span>  
  
3.  <span data-ttu-id="8c93f-116">Fügen Sie die Methode `My.Application.Log.WriteEntry` zum `Startup` -Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c93f-116">Add the `My.Application.Log.WriteEntry` method to the `Startup` event handler.</span></span>  
  
     <span data-ttu-id="8c93f-117">[!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8c93f-117">[!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]</span></span>  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a><span data-ttu-id="8c93f-118">Protokollieren von Meldungen beim Herunterfahren der Anwendung</span><span class="sxs-lookup"><span data-stu-id="8c93f-118">To log messages when the application shuts down</span></span>  
  
1.  <span data-ttu-id="8c93f-119">Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="8c93f-119">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="8c93f-120">Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.</span><span class="sxs-lookup"><span data-stu-id="8c93f-120">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2.  <span data-ttu-id="8c93f-121">Wählen Sie im Menü **Deklarationen** den Eintrag **Herunterfahren**aus.</span><span class="sxs-lookup"><span data-stu-id="8c93f-121">On the **Declarations** menu, choose **Shutdown**.</span></span>  
  
     <span data-ttu-id="8c93f-122">Die Anwendung löst das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> -Ereignis aus, wenn der Hauptthread der Anwendung ausgeführt wird, jedoch bevor er heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="8c93f-122">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> event after the main application runs, but before it shuts down.</span></span>  
  
3.  <span data-ttu-id="8c93f-123">Fügen Sie die Methode `My.Application.Log.WriteEntry` zum `Shutdown` -Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c93f-123">Add the `My.Application.Log.WriteEntry` method to the `Shutdown` event handler.</span></span>  
  
     <span data-ttu-id="8c93f-124">[!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8c93f-124">[!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c93f-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c93f-125">Example</span></span>  
 <span data-ttu-id="8c93f-126">Sie können den **Projekt-Designer** verwenden, um auf die Anwendungsereignisse im Code-Editor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="8c93f-126">You can use the **Project Designer** to access the application events in the Code Editor.</span></span> <span data-ttu-id="8c93f-127">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8c93f-127">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="8c93f-128">[!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8c93f-128">[!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c93f-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c93f-129">See Also</span></span>  
 <span data-ttu-id="8c93f-130"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8c93f-130"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="8c93f-131"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="8c93f-131"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="8c93f-132"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="8c93f-132"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="8c93f-133">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="8c93f-133">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
 [<span data-ttu-id="8c93f-134">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="8c93f-134">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)

