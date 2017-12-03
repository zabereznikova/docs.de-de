---
title: "WCF-Dienste und Ereignisablaufverfolgung für Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed3b7b370ed6b1d9a900579ff0e6f1b0a22290c3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="15e34-102">WCF-Dienste und Ereignisablaufverfolgung für Windows</span><span class="sxs-lookup"><span data-stu-id="15e34-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="15e34-103">In diesem Beispiel wird gezeigt, wie die analytische Ablaufverfolgung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet wird, um Ereignisse in der Ereignisablaufverfolgung für Windows (ETW) auszugeben.</span><span class="sxs-lookup"><span data-stu-id="15e34-103">This sample demonstrates how to use the analytic tracing in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="15e34-104">Die analytische Ablaufverfolgung besteht aus Ereignissen, die an Schlüsselpunkten im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Stapel ausgegeben werden und die Problembehandlung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste in der Produktionsumgebung zulassen.</span><span class="sxs-lookup"><span data-stu-id="15e34-104">The analytic traces are events emitted at key points in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stack that allow troubleshooting of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services in production environment.</span></span>  
  
 <span data-ttu-id="15e34-105">Die analytische Ablaufverfolgung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist eine Methode der Ablaufverfolgung, die in einer Produktionsumgebung mit minimalen Auswirkungen auf die Leistung aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="15e34-105">Analytic trace in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="15e34-106">Diese Ablaufverfolgungen werden als Ereignisse zu einer ETW-Sitzung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="15e34-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="15e34-107">Dieses Beispiel enthält einen grundlegenden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst, in dem Ereignisse vom Dienst an das Ereignisprotokoll ausgegeben werden. Dieses kann mit der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="15e34-107">This sample includes a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="15e34-108">Es ist auch möglich, eine dedizierte ETW-Sitzung zu starten, die Ereignisse des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts überwacht.</span><span class="sxs-lookup"><span data-stu-id="15e34-108">It is also possible to start a dedicated ETW session that listens for events from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="15e34-109">Das Beispiel enthält ein Skript zum Erstellen einer dedizierten ETW-Sitzung, in der Ereignisse in einer Binärdatei gespeichert werden, die mithilfe der Ereignisanzeige gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="15e34-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="15e34-110">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="15e34-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="15e34-111">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die EtwAnalyticTraceSample.sln-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="15e34-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="15e34-112">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="15e34-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="15e34-113">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="15e34-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="15e34-114">Klicken Sie in den Webbrowser auf **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="15e34-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="15e34-115">Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15e34-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="15e34-116">Kopieren Sie diesen URI.</span><span class="sxs-lookup"><span data-stu-id="15e34-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="15e34-117">Standardmäßig beginnt der Dienst damit, Anforderungen auf Port 1378 (http://localhost:1378/Calculator .svc) zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="15e34-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="15e34-118">Führen Sie den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Testclient (WcfTestClient.exe) aus.</span><span class="sxs-lookup"><span data-stu-id="15e34-118">Run the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="15e34-119">Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Testclient (WcfTestClient.exe) befindet sich der \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] -Installationsverzeichnis > \Common7\IDE\ WcfTestClient.exe (Standardeinstellung [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Installationsverzeichnis ist C:\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="15e34-119">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="15e34-120">Innerhalb der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client testen, fügen Sie den Dienst, indem Sie auswählen **Datei**, und klicken Sie dann **Dienst hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="15e34-120">Within the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="15e34-121">Fügen Sie die Endpunktadresse im Eingabefeld hinzu.</span><span class="sxs-lookup"><span data-stu-id="15e34-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="15e34-122">Die Standardadresse ist http://localhost:1378/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="15e34-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="15e34-123">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="15e34-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="15e34-124">Starten Sie vor dem Aufrufen des Diensts die Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ausgegebene Überwachungsereignisse ausführt.</span><span class="sxs-lookup"><span data-stu-id="15e34-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
7.  <span data-ttu-id="15e34-125">Aus der **starten** klicken Sie im Menü **Verwaltung**, und klicken Sie dann **Ereignisanzeige**.</span><span class="sxs-lookup"><span data-stu-id="15e34-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="15e34-126">Aktivieren der **analytisch** und **Debuggen** Protokolle.</span><span class="sxs-lookup"><span data-stu-id="15e34-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="15e34-127">Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="15e34-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="15e34-128">Mit der rechten Maustaste **Anwendungsserver-Anwendungen**Option **Ansicht**, und klicken Sie dann **anzeigen analytische und Debugprotokolle**.</span><span class="sxs-lookup"><span data-stu-id="15e34-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="15e34-129">Sicherstellen, dass die **anzeigen analytische und Debugprotokolle** Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="15e34-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="15e34-130">Aktivieren der **analytisch** Protokoll.</span><span class="sxs-lookup"><span data-stu-id="15e34-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="15e34-131">Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="15e34-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="15e34-132">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="15e34-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="15e34-133">So testen Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="15e34-133">To test the service</span></span>  
  
1.  <span data-ttu-id="15e34-134">Wechseln Sie zurück zum [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Testclient, doppelklicken Sie auf `Divide`, und behalten Sie die Standardwerte bei, die als Nenner 0 angeben.</span><span class="sxs-lookup"><span data-stu-id="15e34-134">Switch back to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="15e34-135">Wenn der Nenner 0 ist, löst der Dienst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="15e34-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="15e34-136">Beachten Sie die vom Dienst ausgegebenen Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="15e34-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="15e34-137">Wechseln Sie zurück zur Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="15e34-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="15e34-138">Mit der rechten Maustaste **analytisch** , und wählen Sie **aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="15e34-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="15e34-139">Die analytischen Ablaufverfolgungsereignisse in WCF werden in der Ereignisanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15e34-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="15e34-140">Beachten Sie, dass ein Fehler als Ablaufverfolgungsereignis in der Ereignisanzeige angezeigt wird, da ein Fehler vom Dienst ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="15e34-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="15e34-141">Wiederholen Sie Schritt 1 und 2 mit gültigen Eingaben.</span><span class="sxs-lookup"><span data-stu-id="15e34-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="15e34-142">Der Wert des `N2`-Parameters kann eine beliebige Zahl außer 0 sein.</span><span class="sxs-lookup"><span data-stu-id="15e34-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="15e34-143">Aktualisieren Sie den analytischen Kanal, um die WCF-Ereignisse anzuzeigen, wobei keine Fehlerereignisse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="15e34-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="15e34-144">Im Beispiel werden die von einem WCF-Dienst ausgegebenen analytischen Ablaufverfolgungsereignisse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="15e34-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="15e34-145">So führen Sie eine (optionale) Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="15e34-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="15e34-146">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="15e34-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="15e34-147">Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="15e34-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="15e34-148">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="15e34-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="15e34-149">Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="15e34-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="15e34-150">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll löschen**.</span><span class="sxs-lookup"><span data-stu-id="15e34-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="15e34-151">Wählen Sie die **deaktivieren** Option aus, um die Ereignisse zu löschen.</span><span class="sxs-lookup"><span data-stu-id="15e34-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15e34-152">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="15e34-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="15e34-153">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="15e34-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="15e34-154">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="15e34-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="15e34-155">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="15e34-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="15e34-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15e34-156">See Also</span></span>  
 [<span data-ttu-id="15e34-157">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="15e34-157">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
