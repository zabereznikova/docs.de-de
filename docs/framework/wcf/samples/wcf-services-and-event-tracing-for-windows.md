---
title: WCF-Dienste und Ereignisablaufverfolgung für Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: ea917ee87b598fc3ad01df70d9aedfadfd1396a4
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809832"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="ceca6-102">WCF-Dienste und Ereignisablaufverfolgung für Windows</span><span class="sxs-lookup"><span data-stu-id="ceca6-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="ceca6-103">Dieses Beispiel veranschaulicht, wie die analytische Ablaufverfolgung in der Windows Communication Foundation (WCF) verwenden, um Ereignisse in Event Tracing for Windows (ETW) auszugeben.</span><span class="sxs-lookup"><span data-stu-id="ceca6-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="ceca6-104">Die analytische Ablaufverfolgung werden Ereignisse, die an Schlüsselpunkten im WCF-Stapel, die es ermöglichen, zur Problembehandlung von WCF-Diensten in produktionsumgebung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ceca6-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>  
  
 <span data-ttu-id="ceca6-105">Analytische Ablaufverfolgung in WCF-Diensten ist, die die Ablaufverfolgung aktiviert werden kann in einer produktiven Umgebung mit minimaler Auswirkung auf die Leistung.</span><span class="sxs-lookup"><span data-stu-id="ceca6-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="ceca6-106">Diese Ablaufverfolgungen werden als Ereignisse zu einer ETW-Sitzung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ceca6-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="ceca6-107">Dieses Beispiel enthält einen grundlegenden WCF-Dienst in dem Ereignisse aus dem Dienst in das Ereignisprotokoll ausgegeben werden mithilfe der Ereignisanzeige angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="ceca6-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="ceca6-108">Es ist auch möglich, eine dedizierte ETW-Sitzung zu starten, die für Ereignisse aus den WCF-Dienst überwacht.</span><span class="sxs-lookup"><span data-stu-id="ceca6-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="ceca6-109">Das Beispiel enthält ein Skript zum Erstellen einer dedizierten ETW-Sitzung, in der Ereignisse in einer Binärdatei gespeichert werden, die mithilfe der Ereignisanzeige gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ceca6-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ceca6-110">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="ceca6-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="ceca6-111">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die EtwAnalyticTraceSample.sln-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ceca6-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ceca6-112">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ceca6-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ceca6-113">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ceca6-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="ceca6-114">Klicken Sie in den Webbrowser auf **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="ceca6-115">Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ceca6-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="ceca6-116">Kopieren Sie diesen URI.</span><span class="sxs-lookup"><span data-stu-id="ceca6-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="ceca6-117">Standardmäßig Dienststart lauscht Anforderungen auf Port 1378 (http://localhost:1378/Calculator.svc).</span><span class="sxs-lookup"><span data-stu-id="ceca6-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="ceca6-118">Führen Sie den WCF-Testclient (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="ceca6-118">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="ceca6-119">WCF-Testclient (WcfTestClient.exe) befindet sich der \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] -Installationsverzeichnis > \Common7\IDE\ WcfTestClient.exe (Standardeinstellung [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Installationsverzeichnis ist C:\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="ceca6-119">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="ceca6-120">Fügen Sie innerhalb der WCF-Testclient den Dienst, indem Sie auswählen **Datei**, und klicken Sie dann **Dienst hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-120">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="ceca6-121">Fügen Sie die Endpunktadresse im Eingabefeld hinzu.</span><span class="sxs-lookup"><span data-stu-id="ceca6-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="ceca6-122">Die Standardeinstellung ist http://localhost:1378/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="ceca6-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="ceca6-123">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="ceca6-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="ceca6-124">Vor dem Aufrufen des Diensts die Ereignisanzeige starten, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für vom WCF-Dienst ausgegebene Überwachungsereignisse ausführt.</span><span class="sxs-lookup"><span data-stu-id="ceca6-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
7.  <span data-ttu-id="ceca6-125">Aus der **starten** klicken Sie im Menü **Verwaltung**, und klicken Sie dann **Ereignisanzeige**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="ceca6-126">Aktivieren der **analytisch** und **Debuggen** Protokolle.</span><span class="sxs-lookup"><span data-stu-id="ceca6-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="ceca6-127">Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="ceca6-128">Mit der rechten Maustaste **Anwendungsserver-Anwendungen**Option **Ansicht**, und klicken Sie dann **anzeigen analytische und Debugprotokolle**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="ceca6-129">Sicherstellen, dass die **anzeigen analytische und Debugprotokolle** Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ceca6-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="ceca6-130">Aktivieren der **analytisch** Protokoll.</span><span class="sxs-lookup"><span data-stu-id="ceca6-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="ceca6-131">Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="ceca6-132">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="ceca6-133">So testen Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="ceca6-133">To test the service</span></span>  
  
1.  <span data-ttu-id="ceca6-134">Wechseln Sie zurück zum WCF-Testclient, und doppelklicken Sie auf `Divide` und behalten Sie die Standardwerte, die als Nenner 0 angeben.</span><span class="sxs-lookup"><span data-stu-id="ceca6-134">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="ceca6-135">Wenn der Nenner 0 ist, löst der Dienst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="ceca6-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="ceca6-136">Beachten Sie die vom Dienst ausgegebenen Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="ceca6-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="ceca6-137">Wechseln Sie zurück zur Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="ceca6-138">Mit der rechten Maustaste **analytisch** , und wählen Sie **aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="ceca6-139">Die analytischen Ablaufverfolgungsereignisse in WCF werden in der Ereignisanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ceca6-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="ceca6-140">Beachten Sie, dass ein Fehler als Ablaufverfolgungsereignis in der Ereignisanzeige angezeigt wird, da ein Fehler vom Dienst ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="ceca6-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="ceca6-141">Wiederholen Sie Schritt 1 und 2 mit gültigen Eingaben.</span><span class="sxs-lookup"><span data-stu-id="ceca6-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="ceca6-142">Der Wert des `N2`-Parameters kann eine beliebige Zahl außer 0 sein.</span><span class="sxs-lookup"><span data-stu-id="ceca6-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="ceca6-143">Aktualisieren Sie den analytischen Kanal, um die WCF-Ereignisse anzuzeigen, wobei keine Fehlerereignisse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ceca6-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="ceca6-144">Im Beispiel werden die von einem WCF-Dienst ausgegebenen analytischen Ablaufverfolgungsereignisse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ceca6-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="ceca6-145">So führen Sie eine (optionale) Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="ceca6-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="ceca6-146">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="ceca6-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="ceca6-147">Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="ceca6-148">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="ceca6-149">Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="ceca6-150">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll löschen**.</span><span class="sxs-lookup"><span data-stu-id="ceca6-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="ceca6-151">Wählen Sie die **deaktivieren** Option aus, um die Ereignisse zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ceca6-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ceca6-152">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ceca6-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ceca6-153">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ceca6-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ceca6-154">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="ceca6-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ceca6-155">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ceca6-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="ceca6-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ceca6-156">See Also</span></span>  
 [<span data-ttu-id="ceca6-157">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="ceca6-157">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
