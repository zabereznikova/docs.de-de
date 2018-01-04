---
title: Extrahieren von WF-Daten mithilfe der Nachverfolgung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d6c269dc9c8b5a0050cfc3ffcefc3160b07c897
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="extract-wf-data-using-tracking"></a><span data-ttu-id="a9bfc-102">Extrahieren von WF-Daten mithilfe der Nachverfolgung</span><span class="sxs-lookup"><span data-stu-id="a9bfc-102">Extract WF Data using Tracking</span></span>
<span data-ttu-id="a9bfc-103">In diesem Beispiel wird veranschaulicht, wie die Workflownachverfolgung verwendet wird, um Workflowvariablen und Argumente aus Aktivitäten zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-103">This sample demonstrates how to use workflow tracking to extract workflow variables and arguments from activities.</span></span> <span data-ttu-id="a9bfc-104">Außerdem wird auch das Hinzufügen von Bemerkungen zu Überwachungsdatensätzen sowie das Extrahieren der Datennutzlast innerhalb von benutzerdefinierten Überwachungsdatensätzen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-104">It also shows the addition of annotations to tracking records and the extraction of data payload within custom tracking records.</span></span> <span data-ttu-id="a9bfc-105">Im Beispiel wird der ETW-Überwachungsteilnehmer (Ereignisablaufverfolgung für Windows) zum Extrahieren von Daten aus dem Workflow verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-105">The sample uses the Event Tracing for Windows (ETW) tracking participant to extract data from the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="a9bfc-106">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="a9bfc-106">Sample Details</span></span>  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="a9bfc-107"> stellt die Überwachung bereit, um einen Einblick in die Ausführung einer Workflowinstanz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-107"> provides tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="a9bfc-108">Die Überwachungslaufzeit gibt während der Ausführung des Workflows Workflowüberwachungsdatensätze aus.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-108">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="a9bfc-109">Zusammen mit den Workflowüberwachungsdatensätzen können Daten innerhalb der Workflowinstanz aus dem Workflow extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-109">Along with the workflow tracking records, data within the workflow instance can be extracted from the workflow.</span></span> <span data-ttu-id="a9bfc-110">In der folgenden Liste sind die Typen von Daten aufgeführt, die aus Überwachungsdatensätzen extrahiert werden können:</span><span class="sxs-lookup"><span data-stu-id="a9bfc-110">The following list details the types of data that can be extracted from tracking records:</span></span>  
  
1.  <span data-ttu-id="a9bfc-111">Workflowvariablen in einer Aktivität und Überwachungsdatensätze während der Aktivitätsausführung.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-111">Workflow variables within an activity and tracking records during activity execution.</span></span>  
  
     <span data-ttu-id="a9bfc-112">Um Workflowvariablen zu extrahieren, werden die zu extrahierenden Variablen in einem Profil angegeben.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-112">To extract workflow variables, the variables to be extracted are specified in a profile.</span></span> <span data-ttu-id="a9bfc-113">Zu extrahierende Variablen können nur mit `ActivityStateQueries` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-113">Variables to be extracted can only be specified with `ActivityStateQueries`.</span></span> <span data-ttu-id="a9bfc-114">Im folgenden Codebeispiel ist ein Überwachungsprofil dargestellt, das zum Extrahieren der Workflowvariablen aus einer Aktivität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-114">The following code example demonstrates a tracking profile used to extract the workflow variable from an activity.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  <span data-ttu-id="a9bfc-115">Aktivitätsargumente und Aktivitätszustands-Überwachungsdatensätze.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-115">Activity arguments and activity state tracking records.</span></span>  
  
     <span data-ttu-id="a9bfc-116">Argumente definieren die Richtung, in der Daten in oder aus einer Aktivität fließen.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-116">Arguments define the way data flows in or out of an activity.</span></span> <span data-ttu-id="a9bfc-117">Zu extrahierende Argumente werden mit einer <xref:System.Activities.Tracking.ActivityStateQuery> angegeben. Im folgenden Codebeispiel ist ein Überwachungsprofil dargestellt, das das `Value`-Argument extrahiert.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-117">Arguments to be extracted are specified using an <xref:System.Activities.Tracking.ActivityStateQuery>.The following code example is a tracking profile that extracts the `Value` argument.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  <span data-ttu-id="a9bfc-118">Anmerkungen sind Schlüssel-Wert-Paare, die einem beliebigen Überwachungsdatensatz hinzugefügt werden können, der ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-118">Annotations are key/value pairs that can be added to any tracking record that is emitted.</span></span>  
  
     <span data-ttu-id="a9bfc-119">Anmerkungen dienen der Markierung von Überwachungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-119">Annotations serve as a tagging mechanism for tracking records.</span></span> <span data-ttu-id="a9bfc-120">Sie verwenden Überwachungsdatensätzen über ein Überwachungsprofil hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-120">Annotations are added to tracking records through a tracking profile.</span></span> <span data-ttu-id="a9bfc-121">Anmerkungen können einem beliebigen Typ einer Workflowüberwachungsabfrage hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-121">Annotations can be added to any type of a workflow tracking query.</span></span> <span data-ttu-id="a9bfc-122">Im folgenden Codebeispiel ist ein Nachverfolgungsprofil dargestellt, das zeigt, wie einem Überwachungsdatensatz eine Anmerkung hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-122">The following code example is a tracking profile that shows how an annotation can be added to a tracking record.</span></span>  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  <span data-ttu-id="a9bfc-123">Benutzerdefinierte Überwachungsdatensätze werden von benutzerdefinierten Aktivitäten ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-123">Custom tracking records are emitted from user-defined activities.</span></span>  
  
     <span data-ttu-id="a9bfc-124">Benutzerdefinierte Überwachungsdatensätze können innerhalb dieser Aktivität definierte Nutzlastdaten tragen.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-124">Custom tracking records can carry payload data defined within this activity.</span></span> <span data-ttu-id="a9bfc-125">Durch Abonnieren von benutzerdefinierten Überwachungsdatensätzen in einem Überwachungsprofil wird das Extrahieren der Nutzlast innerhalb des Überwachungsdatensatzes ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-125">Subscribing for custom tracking records in a tracking profile allows the extraction of the payload within the tracking record.</span></span> <span data-ttu-id="a9bfc-126">Die benutzerdefinierten Überwachungsdatensätze können mit einer benutzerdefinierten <xref:System.Activities.Tracking.TrackingQuery> extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-126">The custom tracking records can be extracted with custom a <xref:System.Activities.Tracking.TrackingQuery>.</span></span> <span data-ttu-id="a9bfc-127">Im folgenden Codebeispiel ist ein Überwachungsprofil dargestellt, das einen benutzerdefinierten Überwachungsdatensatz zusammen mit seiner Nutzlast extrahiert.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-127">The following code example is a tracking profile that extracts a custom tracking record along with its payload.</span></span>  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 <span data-ttu-id="a9bfc-128">In dem Beispiel wird das Extrahieren von Variablen, Argumenten, benutzerdefinierten Datensätzen und das Hinzufügen von Anmerkungen mithilfe eines in "Web.config" angegebenen Profils veranschaulicht. Die Nachverfolgung wird in dem Beispielworkflowdienst durch Hinzufügen eines `<etwTracking>`-Verhaltenselements ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-128">The sample demonstrates the extraction of a variables, arguments, custom records and adding annotations using a profile specified in a Web.config. Tracking is enabled on the sample workflow service by adding an `<etwTracking>` behavior element.</span></span> <span data-ttu-id="a9bfc-129">Im folgenden Codebeispiel wird die Verfolgung für das `ExtractWorkflowVariables`-Nachverfolgungsprofil aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-129">The following code example enables tracking for the `ExtractWorkflowVariables` tracking profile.</span></span>  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a9bfc-130">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9bfc-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="a9bfc-131">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "WFStockPriceApplication.sln".</span><span class="sxs-lookup"><span data-stu-id="a9bfc-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="a9bfc-132">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a9bfc-133">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-133">To run the solution, press F5.</span></span>  
  
     <span data-ttu-id="a9bfc-134">Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-134">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="a9bfc-135">Klicken Sie im Browser auf "StockPriceService.xamlx".</span><span class="sxs-lookup"><span data-stu-id="a9bfc-135">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="a9bfc-136">Der Browser zeigt die Seite "StockPriceService" an, die die WSDL-Adresse des lokalen Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-136">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="a9bfc-137">Kopieren Sie diese Adresse.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-137">Copy this address.</span></span>  
  
     <span data-ttu-id="a9bfc-138">Das folgende Beispiel zeigt eine WSDL-Adresse des lokalen Diensts.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-138">The following example shows a local service WSDL address.</span></span> `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  <span data-ttu-id="a9bfc-139">Starten Sie vor dem Aufrufen des Diensts die Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für vom Workflowdienst ausgegebene Überwachungsereignisse ausführt.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-139">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>  
  
7.  <span data-ttu-id="a9bfc-140">Aus der **starten** klicken Sie im Menü **Verwaltung** und dann **Ereignisanzeige**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-140">From the **Start** menu, select **Administrative Tools** and then **Event Viewer**.</span></span>  
  
8.  <span data-ttu-id="a9bfc-141">Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, und **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-141">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="a9bfc-142">Mit der rechten Maustaste **Microsoft** , und wählen Sie **Ansicht** und dann **anzeigen analytische und Debugprotokolle**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-142">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="a9bfc-143">Sicherstellen, dass die **anzeigen analytische und Debugprotokolle** Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-143">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="a9bfc-144">Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**,  **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-144">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="a9bfc-145">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-145">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="a9bfc-146">Öffnen Sie den WCF-Testclient mit [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9bfc-146">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], open the WCF test client.</span></span>  
  
     <span data-ttu-id="a9bfc-147">WCF-Testclient (WcfTestClient.exe) befindet sich der \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] -Installationsordner > \Common7\IDE\-Ordner.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-147">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder>\Common7\IDE\ folder.</span></span>  
  
     <span data-ttu-id="a9bfc-148">Der standardmäßige [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Installationsordner ist "C:\Programme\Microsoft-Visual Studio 10.0".</span><span class="sxs-lookup"><span data-stu-id="a9bfc-148">The default [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>  
  
11. <span data-ttu-id="a9bfc-149">Wählen Sie im WCF-Testclient **Dienst hinzufügen** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-149">In WCF test client, select **Add Service** from the **File** menu.</span></span>  
  
     <span data-ttu-id="a9bfc-150">Fügen Sie die WSDL-Adresse des lokalen Diensts, die Sie zuvor kopiert haben, in das Eingabefeld ein.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-150">Add the local service WSDL address you copied earlier in the input box.</span></span>  
  
12. <span data-ttu-id="a9bfc-151">Doppelklicken Sie im WCF-Testclient auf `GetStockPrice`.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-151">In WCF test client, double-click `GetStockPrice`.</span></span>  
  
     <span data-ttu-id="a9bfc-152">Dadurch wird die `GetStockPrice`-Methode geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-152">This opens the `GetStockPrice` method.</span></span> <span data-ttu-id="a9bfc-153">Die Anforderung akzeptiert einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-153">The request accepts one parameter.</span></span> <span data-ttu-id="a9bfc-154">Verwenden Sie den Wert **Contoso**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-154">Use the value **Contoso**.</span></span>  
  
13. <span data-ttu-id="a9bfc-155">Klicken Sie auf **Aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-155">Click **Invoke**.</span></span>  
  
14. <span data-ttu-id="a9bfc-156">Wechseln Sie zurück zur Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**,  **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-156">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="a9bfc-157">Mit der rechten Maustaste **analytisch** , und wählen Sie **aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-157">Right-click **Analytic** and select **Refresh**.</span></span> <span data-ttu-id="a9bfc-158">Die Workflowereignisse befinden sich im Ereignis-ID-Bereich 100-199.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-158">The workflow events are in the event ID ranges 100-199.</span></span>  
  
     <span data-ttu-id="a9bfc-159">Die Ereignisse enthalten die Anmerkungen, Variablen, Argumente und benutzerdefinierten Überwachungsdatensätze, die in der Ereignisanzeige angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-159">The events contain the annotations, variables, arguments and custom tracking records that can be viewed in the event viewer.</span></span>  
  
## <a name="cleaning-up-in-the-event-viewer"></a><span data-ttu-id="a9bfc-160">Bereinigen in der Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="a9bfc-160">Cleaning up in the Event Viewer</span></span>  
 <span data-ttu-id="a9bfc-161">Der analytische Channel im Ereignisprotokoll kann in der Ereignisanzeige folgendermaßen bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-161">The analytic channel in the event log can be cleaned up in the Event Viewer by doing the following.</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="a9bfc-162">So führen Sie eine Bereinigung aus (optional)</span><span class="sxs-lookup"><span data-stu-id="a9bfc-162">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="a9bfc-163">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-163">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="a9bfc-164">Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendung Server-Applications**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-164">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="a9bfc-165">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-165">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="a9bfc-166">Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendung Server-Applications**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-166">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="a9bfc-167">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll löschen**.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-167">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
     <span data-ttu-id="a9bfc-168">Wählen Sie die **deaktivieren** Option aus, um die Ereignisse zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-168">Choose the **Clear** option to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="a9bfc-169">Bekanntes Problem</span><span class="sxs-lookup"><span data-stu-id="a9bfc-169">Known Issue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9bfc-170">Es gibt ein bekanntes Problem in der Ereignisanzeige, bei dem bei der Decodierung von ETW-Ereignissen ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-170">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="a9bfc-171">Möglicherweise wird eine Fehlermeldung ähnlich der Folgenden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-171">You may see an error message that looks like the following.</span></span>  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  <span data-ttu-id="a9bfc-172">Wenn dieser Fehler auftritt, klicken Sie auf **aktualisieren** klicken Sie im Bereich "Aktionen".</span><span class="sxs-lookup"><span data-stu-id="a9bfc-172">If you encounter this error, click **Refresh** in the actions pane.</span></span> <span data-ttu-id="a9bfc-173">Das Ereignis sollte jetzt ordnungsgemäß decodiert werden.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-173">The event should now decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9bfc-174">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-174">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a9bfc-175">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-175">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a9bfc-176">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-176">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9bfc-177">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a9bfc-177">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a><span data-ttu-id="a9bfc-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9bfc-178">See Also</span></span>  
 [<span data-ttu-id="a9bfc-179">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="a9bfc-179">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
