---
title: 'Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll (Visual Basic)'
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
- Computer.EventLog element
- WriteEntry method
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
caps.latest.revision: 21
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
ms.openlocfilehash: 7cc73b0644003f8231a7792b0b62d143159da075
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a><span data-ttu-id="a4f8a-102">Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4f8a-102">How to: Write to an Application Event Log (Visual Basic)</span></span>
<span data-ttu-id="a4f8a-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu erfassen, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-103">You can use the `My.Application.Log` and `My.Log` objects to write information about events that occur in your application.</span></span> <span data-ttu-id="a4f8a-104">Dieses Beispiel veranschaulicht, wie ein Ereignisprotokolllistener konfiguriert wird, damit `My.Application.Log` Ablaufverfolgungsinformationen in das Anwendungsereignisprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-104">This example shows how to configure an event log listener so `My.Application.Log` writes tracing information to the Application event log.</span></span>  
  
 <span data-ttu-id="a4f8a-105">In das Sicherheitsprotokoll kann nicht geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-105">You cannot write to the Security log.</span></span> <span data-ttu-id="a4f8a-106">Um in das Systemprotokoll zu schreiben, müssen Sie Mitglied des Kontos "LocalSystem" oder "Administrator" sein.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-106">In order to write to the System log, you must be a member of the LocalSystem or Administrator account.</span></span>  
  
 <span data-ttu-id="a4f8a-107">Zum Anzeigen von Ereignisprotokollen können Sie den **Server-Explorer** oder die **Windows-Ereignisanzeige**verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-107">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="a4f8a-108">Weitere Informationen finden Sie unter [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span><span class="sxs-lookup"><span data-stu-id="a4f8a-108">For more information, see [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4f8a-109">Ereignisprotokolle werden unter Windows 95, Windows 98 bzw. Windows Millennium Edition (ME) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-109">Event logs are not supported on Windows 95, Windows 98, or Windows Millennium Edition.</span></span>  
  
### <a name="to-add-and-configure-the-event-log-listener"></a><span data-ttu-id="a4f8a-110">Hinzufügen und Konfigurieren des Ereignisprotokolllisteners</span><span class="sxs-lookup"><span data-stu-id="a4f8a-110">To add and configure the event log listener</span></span>  
  
1.  <span data-ttu-id="a4f8a-111">Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="a4f8a-112">\- oder –</span><span class="sxs-lookup"><span data-stu-id="a4f8a-112">\- or -</span></span>  
  
     <span data-ttu-id="a4f8a-113">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="a4f8a-113">If there is no app.config file,</span></span>  
  
    1.  <span data-ttu-id="a4f8a-114">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-114">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="a4f8a-115">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-115">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="a4f8a-116">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-116">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="a4f8a-117">Suchen Sie den Abschnitt `<listeners>` in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-117">Locate the `<listeners>` section in the application configuration file.</span></span>  
  
     <span data-ttu-id="a4f8a-118">Sie finden den Abschnitt `<listeners>` im `<source>` -Abschnitt mit dem Namensattribut "DefaultSource", der in den `<system.diagnostics>` -Abschnitt verschachtelt ist, der seinerseits in den `<configuration>` -Abschnitt der obersten Ebene verschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-118">You will find the `<listeners>` section in the `<source>` section with the name attribute "DefaultSource", which is nested under the `<system.diagnostics>` section, which is nested under the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="a4f8a-119">Fügen Sie dem `<listeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="a4f8a-119">Add this element to that `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="EventLog"/>  
    ```  
  
4.  <span data-ttu-id="a4f8a-120">Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-120">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="a4f8a-121">Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="a4f8a-121">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="EventLog"  
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="APPLICATION_NAME"/>  
    ```  
  
     <span data-ttu-id="a4f8a-122">Ersetzen Sie `APPLICATION_NAME` durch den Namen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-122">Replace `APPLICATION_NAME` with the name of your application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4f8a-123">Normalerweise schreiben Anwendungen nur Fehler in das Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-123">Typically, an application writes only errors to the event log.</span></span> <span data-ttu-id="a4f8a-124">Informationen zum Filtern von Protokollausgaben finden Sie unter [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="a4f8a-124">For information on filtering log output, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
### <a name="to-write-event-information-to-the-event-log"></a><span data-ttu-id="a4f8a-125">Schreiben von Ereignisinformationen in das Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="a4f8a-125">To write event information to the event log</span></span>  
  
-   <span data-ttu-id="a4f8a-126">Verwenden Sie die `My.Application.Log.WriteEntry` - oder die `My.Application.Log.WriteException` -Methode, um Informationen in das Ereignisprotokoll zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-126">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the event log.</span></span> <span data-ttu-id="a4f8a-127">Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) und [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="a4f8a-127">For more information, see [How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) and [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
     <span data-ttu-id="a4f8a-128">Nachdem Sie den Ereignisprotokolllistener für eine Assembly konfiguriert haben, empfängt er alle Meldungen, die `My.Applcation.Log` für die betreffende Assembly schreibt.</span><span class="sxs-lookup"><span data-stu-id="a4f8a-128">After you configure the event log listener for an assembly, it receives all messages that `My.Applcation.Log` writes from that assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f8a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4f8a-129">See Also</span></span>  
 <span data-ttu-id="a4f8a-130"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a4f8a-130"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="a4f8a-131"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="a4f8a-131"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="a4f8a-132"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="a4f8a-132"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="a4f8a-133">[Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="a4f8a-133">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="a4f8a-134">[Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="a4f8a-134">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 [<span data-ttu-id="a4f8a-135">Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="a4f8a-135">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)

