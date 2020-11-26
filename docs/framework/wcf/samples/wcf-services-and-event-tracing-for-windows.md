---
title: WCF-Dienste und Ereignisablaufverfolgung für Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b5fcfb34843d1168511141b4ce2b4f956559290a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247836"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="9e98d-102">WCF-Dienste und Ereignisablaufverfolgung für Windows</span><span class="sxs-lookup"><span data-stu-id="9e98d-102">WCF Services and Event Tracing for Windows</span></span>

<span data-ttu-id="9e98d-103">In diesem Beispiel wird veranschaulicht, wie die analytische Ablauf Verfolgung in Windows Communication Foundation (WCF) verwendet wird, um Ereignisse in der Ereignis Ablauf Verfolgung für Windows (ETW) auszugeben.</span><span class="sxs-lookup"><span data-stu-id="9e98d-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="9e98d-104">Die analytischen Ablauf Verfolgungen sind Ereignisse, die an wichtigen Punkten im WCF-Stapel ausgegeben werden und die Problembehandlung von WCF-Diensten in der Produktionsumgebung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9e98d-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="9e98d-105">Die analytische Ablauf Verfolgung in WCF-Diensten ist die Ablauf Verfolgung, die in einer Produktionsumgebung mit minimalen Auswirkungen auf die Leistung aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e98d-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="9e98d-106">Diese Ablaufverfolgungen werden als Ereignisse zu einer ETW-Sitzung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9e98d-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="9e98d-107">Dieses Beispiel enthält einen einfachen WCF-Dienst, in dem Ereignisse vom Dienst an das Ereignisprotokoll ausgegeben werden, das mithilfe von Ereignisanzeige angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e98d-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="9e98d-108">Es ist auch möglich, eine dedizierte ETW-Sitzung zu starten, die auf Ereignisse vom WCF-Dienst lauscht.</span><span class="sxs-lookup"><span data-stu-id="9e98d-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="9e98d-109">Das Beispiel enthält ein Skript zum Erstellen einer dedizierten ETW-Sitzung, in der Ereignisse in einer Binärdatei gespeichert werden, die mithilfe der Ereignisanzeige gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e98d-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="9e98d-110">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e98d-110">To use this sample</span></span>

1. <span data-ttu-id="9e98d-111">Öffnen Sie mit Visual Studio 2012 die Projektmappendatei "EtwAnalyticTraceSample. sln".</span><span class="sxs-lookup"><span data-stu-id="9e98d-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="9e98d-112">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9e98d-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="9e98d-113">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9e98d-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="9e98d-114">Klicken Sie im Webbrowser auf **Calculator. svc**.</span><span class="sxs-lookup"><span data-stu-id="9e98d-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="9e98d-115">Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e98d-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="9e98d-116">Kopieren Sie diesen URI.</span><span class="sxs-lookup"><span data-stu-id="9e98d-116">Copy that URI.</span></span>

     <span data-ttu-id="9e98d-117">Standardmäßig beginnt der Dienst mit dem lauschen auf Anforderungen an Port 1378 `http://localhost:1378/Calculator.svc` .</span><span class="sxs-lookup"><span data-stu-id="9e98d-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="9e98d-118">Führen Sie den WCF-Test Client (WcfTestClient.exe) aus.</span><span class="sxs-lookup"><span data-stu-id="9e98d-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="9e98d-119">Der WCF-Test Client (WcfTestClient.exe) befindet sich unter `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe` .</span><span class="sxs-lookup"><span data-stu-id="9e98d-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="9e98d-120">Der Standard Installationsverzeichnis von Visual Studio 2012 lautet `C:\Program Files\Microsoft Visual Studio 10.0` .</span><span class="sxs-lookup"><span data-stu-id="9e98d-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="9e98d-121">Fügen Sie im WCF-Test Client den Dienst hinzu, indem Sie auf **Datei** und dann auf **Dienst hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="9e98d-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="9e98d-122">Fügen Sie die Endpunktadresse im Eingabefeld hinzu.</span><span class="sxs-lookup"><span data-stu-id="9e98d-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="9e98d-123">Der Standardwert ist `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="9e98d-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="9e98d-124">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="9e98d-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="9e98d-125">Bevor Sie den Dienst aufrufen, starten Sie Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll nach Verfolgungs Ereignissen lauscht, die vom WCF-Dienst ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9e98d-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="9e98d-126">Klicken Sie im **Startmenü** auf **Verwaltung**, und klicken Sie dann auf **Ereignisanzeige**.</span><span class="sxs-lookup"><span data-stu-id="9e98d-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="9e98d-127">Aktivieren Sie die **analytischen** und **Debugprotokolle** .</span><span class="sxs-lookup"><span data-stu-id="9e98d-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="9e98d-128">Navigieren Sie in der Strukturansicht in Ereignisanzeige zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows** und dann zu **Anwendungs Server-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="9e98d-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="9e98d-129">Klicken Sie mit der rechten Maustaste auf **Anwendungs Server-Anwendungen**, wählen Sie **Ansicht** und dann **analytische und Debugprotokolle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="9e98d-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="9e98d-130">Stellen Sie sicher, dass die Option **analytische und Debugprotokolle anzeigen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9e98d-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="9e98d-131">Aktivieren Sie das **analytische** Protokoll.</span><span class="sxs-lookup"><span data-stu-id="9e98d-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="9e98d-132">Navigieren Sie in der Strukturansicht in Ereignisanzeige zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows** und dann zu **Anwendungs Server-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="9e98d-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="9e98d-133">Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll aktivieren**</span><span class="sxs-lookup"><span data-stu-id="9e98d-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="9e98d-134">So testen Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="9e98d-134">To test the service</span></span>

1. <span data-ttu-id="9e98d-135">Wechseln Sie zurück zum WCF-Test Client, und doppelklicken Sie auf `Divide` , und behalten Sie die Standardwerte bei, die einen Nenner von 0 angeben.</span><span class="sxs-lookup"><span data-stu-id="9e98d-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="9e98d-136">Wenn der Nenner 0 ist, löst der Dienst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="9e98d-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="9e98d-137">Beachten Sie die vom Dienst ausgegebenen Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="9e98d-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="9e98d-138">Wechseln Sie zurück zu Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows** und dann zu **Anwendungs Server-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="9e98d-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="9e98d-139">Klicken Sie mit der rechten Maustaste auf **Analyse** , **und wählen Sie**</span><span class="sxs-lookup"><span data-stu-id="9e98d-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="9e98d-140">Die analytischen Ablaufverfolgungsereignisse in WCF werden in der Ereignisanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e98d-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="9e98d-141">Beachten Sie, dass ein Fehler als Ablaufverfolgungsereignis in der Ereignisanzeige angezeigt wird, da ein Fehler vom Dienst ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="9e98d-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="9e98d-142">Wiederholen Sie Schritt 1 und 2 mit gültigen Eingaben.</span><span class="sxs-lookup"><span data-stu-id="9e98d-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="9e98d-143">Der Wert des `N2`-Parameters kann eine beliebige Zahl außer 0 sein.</span><span class="sxs-lookup"><span data-stu-id="9e98d-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="9e98d-144">Aktualisieren Sie den analytischen Kanal, um die WCF-Ereignisse anzuzeigen, wobei keine Fehlerereignisse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9e98d-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="9e98d-145">Im Beispiel werden die von einem WCF-Dienst ausgegebenen analytischen Ablaufverfolgungsereignisse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9e98d-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="9e98d-146">So führen Sie eine (optionale) Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="9e98d-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="9e98d-147">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="9e98d-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="9e98d-148">Navigieren Sie zu **Ereignisanzeige**, Anwendungs- **und Dienst Protokolle**, **Microsoft**, **Windows** und dann zu **Anwendungs Server-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="9e98d-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="9e98d-149">Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="9e98d-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="9e98d-150">Navigieren Sie zu **Ereignisanzeige**, Anwendungs- **und Dienst Protokolle**, **Microsoft**, **Windows** und dann zu **Anwendungs Server-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="9e98d-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="9e98d-151">Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll löschen**</span><span class="sxs-lookup"><span data-stu-id="9e98d-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="9e98d-152">Wählen Sie die Option **Clear** aus, um die Ereignisse zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9e98d-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e98d-153">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="9e98d-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9e98d-154">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9e98d-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="9e98d-155">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e98d-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9e98d-156">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9e98d-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="9e98d-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e98d-157">See also</span></span>

- <span data-ttu-id="9e98d-158">[AppFabric-Überwachungsbeispiele](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="9e98d-158">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
