---
title: "Überwachen mit einer Textdatei"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1d4b3f319d86dd463dabc8b71be7c76c7fef41f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="tracking-using-a-text-file"></a><span data-ttu-id="51f7e-102">Überwachen mit einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="51f7e-102">Tracking Using a Text File</span></span>
<span data-ttu-id="51f7e-103">In diesem Beispiel wird veranschaulicht, wie die Nachverfolgung von [!INCLUDE[wf](../../../../includes/wf-md.md)] erweitert wird, indem ein benutzerdefinierter Nachverfolgungsteilnehmer erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="51f7e-103">This sample demonstrates how to extend tracking in [!INCLUDE[wf](../../../../includes/wf-md.md)] by creating a custom tracking participant.</span></span> <span data-ttu-id="51f7e-104">Nachverfolgungsteilnehmer sind .NET Framework-Klassen, die Nachverfolgungsdatensätze von der Laufzeit empfangen, wenn sie ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="51f7e-104">Tracking participants are .NET Framework classes that receive tracking records from the runtime as they are emitted.</span></span> <span data-ttu-id="51f7e-105">Sie können einen Nachverfolgungsteilnehmer erstellen, um die Nachverfolgungsereignisse zu dem Ziel zu transportieren, das für das Szenario erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="51f7e-105">You can create a tracking participant to transport the tracking events to whichever destination is required for your scenario.</span></span> <span data-ttu-id="51f7e-106">Ein ETW-Nachverfolgungsteilnehmer (Event Tracing for Windows, Ereignisablaufverfolgung für Windows) wird z. B. als Bestandteil von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="51f7e-106">For example, ETW (Event Tracing for Windows) Tracking Participant is provided as part of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="51f7e-107">Der Nachverfolgungsteilnehmer in diesem Beispiel schreibt die Datensätze in eine Textdatei im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="51f7e-107">The tracking participant in this sample writes the records in XML format to a text file.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="51f7e-108">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="51f7e-108">Sample details</span></span>  
 <span data-ttu-id="51f7e-109">Um die Nützlichkeit und die Stabilität des Nachverfolgungsteilnehmers zu optimieren, müssen einige zusätzliche Schritte ausgeführt werden, damit der Nachverfolgungsteilnehmer ordnungsgemäß mit der Laufzeit verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="51f7e-109">To optimize the usefulness and robustness of your tracking participant, some additional steps must be completed to properly wire the tracking participant to the runtime.</span></span> <span data-ttu-id="51f7e-110">In der folgenden Tabelle werden die in diesem Beispiel verwendeten Klassen beschrieben, mit denen ein Nachverfolgungsteilnehmer erstellt wird, der bewährte Methoden einhält.</span><span class="sxs-lookup"><span data-stu-id="51f7e-110">The following table describes the classes used in this sample to create a tracking participant that complies with best practices.</span></span>  
  
|<span data-ttu-id="51f7e-111">Klasse</span><span class="sxs-lookup"><span data-stu-id="51f7e-111">Class</span></span>|<span data-ttu-id="51f7e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51f7e-112">Description</span></span>|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|<span data-ttu-id="51f7e-113">Ein <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> wird verwendet, um den Konfigurationsabschnitt zu definieren, der verwendet wird, um den Textdatei-Nachverfolgungsteilnehmer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="51f7e-113">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> is used to define the configuration section used to configure the text file tracking participant.</span></span> <span data-ttu-id="51f7e-114">Dies ermöglicht es Benutzern, das Ziel der Protokolldatei mit standardmäßigen .NET Framework-Konfigurationsdateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="51f7e-114">This allows users to specify the destination of the log file using standard .NET Framework configuration files.</span></span>|  
|`TextFileTrackingBehavior`|<span data-ttu-id="51f7e-115">Das Verhalten in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ermöglicht es Benutzern, Erweiterungen in die Laufzeit einzufügen.</span><span class="sxs-lookup"><span data-stu-id="51f7e-115">Behaviors in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allow users to inject extensions into the runtime.</span></span> <span data-ttu-id="51f7e-116">Dieses Verhalten fügt dem Dienst den Nachverfolgungsteilnehmer hinzu, wenn der Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="51f7e-116">This behavior adds the tracking participant to the service when the service starts.</span></span>|  
|`TextFileTrackingParticipant`|<span data-ttu-id="51f7e-117">Der Nachverfolgungsteilnehmer, der zur Laufzeit Nachverfolgungsteilnehmer empfängt und sie in einer Protokolldatei als XML speichert.</span><span class="sxs-lookup"><span data-stu-id="51f7e-117">The tracking participant that receives tracking participants at runtime and stores them to a log file as XML.</span></span>|  
  
## <a name="behavior-extension-elements-configuration"></a><span data-ttu-id="51f7e-118">Konfiguration von Verhaltenserweiterungselementen</span><span class="sxs-lookup"><span data-stu-id="51f7e-118">Behavior Extension Elements Configuration</span></span>  
 <span data-ttu-id="51f7e-119">Ein weiterer Schritt ist erforderlich, um das Verhaltenserweiterungselement zu nutzen, das zuvor mit .NET Framework-Konfigurationsdateien beschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="51f7e-119">One more step is required to make use of the behavior extension element previously described using .NET Framework configuration files.</span></span> <span data-ttu-id="51f7e-120">Die folgende Konfiguration muss in Konfigurationsdateien eingefügt werden, in denen die Erweiterung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="51f7e-120">The following configuration must be placed in configuration files where the extension is to be used.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="51f7e-121">Eine vollständige Beispielverwendung der Konfiguration von Verhaltenserweiterungselementen finden Sie in der Datei "Web.config" im Beispiel.</span><span class="sxs-lookup"><span data-stu-id="51f7e-121">See the Web.config file in the sample for a complete example usage of behavior extension elements configuration.</span></span>  
  
## <a name="custom-tracking-records"></a><span data-ttu-id="51f7e-122">Benutzerdefinierte Überwachungsdatensätze</span><span class="sxs-lookup"><span data-stu-id="51f7e-122">Custom Tracking Records</span></span>  
 <span data-ttu-id="51f7e-123">Die Datei "GetStockPrices.cs" veranschaulicht, wie benutzerdefinierte Nachverfolgungsdatensätze in <xref:System.Activities.CodeActivity> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="51f7e-123">The GetStockPrices.cs file demonstrates how to create custom tracking records from within a <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="51f7e-124">Suchen Sie nach diesem Datensatz, wenn Sie das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="51f7e-124">Look for this record when running the sample.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="51f7e-125">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="51f7e-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="51f7e-126">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "WFStockPriceApplication.sln".</span><span class="sxs-lookup"><span data-stu-id="51f7e-126">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="51f7e-127">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="51f7e-127">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="51f7e-128">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="51f7e-128">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="51f7e-129">Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="51f7e-129">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="51f7e-130">Klicken Sie im Browser auf "StockPriceService.xamlx".</span><span class="sxs-lookup"><span data-stu-id="51f7e-130">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="51f7e-131">Der Browser zeigt die **StockPriceService** Seite, die die Wsdl-Adresse des lokalen Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="51f7e-131">The browser displays the **StockPriceService** page, which contains the local service wsdl address.</span></span> <span data-ttu-id="51f7e-132">Kopieren Sie diese Adresse.</span><span class="sxs-lookup"><span data-stu-id="51f7e-132">Copy this address.</span></span>  
  
     <span data-ttu-id="51f7e-133">Ein Beispiel für die WSDL-Adresse des lokalen Diensts ist "http://localhost:65193/StockPriceService.xamlx?wsdl".</span><span class="sxs-lookup"><span data-stu-id="51f7e-133">An example of the local service wsdl address is http://localhost:53797/StockPriceService.xamlx?wsdl.</span></span>  
  
6.  <span data-ttu-id="51f7e-134">Wechseln Sie im [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] zum [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Ordner (der Standardinstallationsordner ist "%SystemDrive%\Programme\Microsoft Visual Studio 10.0").</span><span class="sxs-lookup"><span data-stu-id="51f7e-134">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], go to your [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] folder (the default installation folder is %SystemDrive%\Program Files\Microsoft Visual Studio 10.0).</span></span> <span data-ttu-id="51f7e-135">Suchen Sie dann den Unterordner "Common7\IDE\".</span><span class="sxs-lookup"><span data-stu-id="51f7e-135">Then locate the Common7\IDE\ subfolder.</span></span>  
  
7.  <span data-ttu-id="51f7e-136">Doppelklicken Sie auf die Datei "WcfTestClient.exe", um den WCF-Testclient zu starten.</span><span class="sxs-lookup"><span data-stu-id="51f7e-136">Double-click the WcfTestClient.exe file to launch the WCF Test Client.</span></span>  
  
8.  <span data-ttu-id="51f7e-137">Wählen Sie in der WCF-Testclient **Dienst hinzufügen...**</span><span class="sxs-lookup"><span data-stu-id="51f7e-137">In the WCF Test Client, select **Add Service…**</span></span> <span data-ttu-id="51f7e-138">aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="51f7e-138">from the **File** menu.</span></span>  
  
9. <span data-ttu-id="51f7e-139">Fügen Sie die URL ein, die Sie gerade in das Textfeld kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="51f7e-139">Paste the URL you just copied into the text box.</span></span>  
  
10. <span data-ttu-id="51f7e-140">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51f7e-140">Click **OK** to close the dialog.</span></span>  
  
11. <span data-ttu-id="51f7e-141">Testen Sie den Dienst mit dem WCF-Testclient.</span><span class="sxs-lookup"><span data-stu-id="51f7e-141">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="51f7e-142">Doppelklicken Sie im WCF-Testclient auf **GetStockPrice()** unter der **IStockPriceService** Knoten.</span><span class="sxs-lookup"><span data-stu-id="51f7e-142">In the WCF Test Client, double-click **GetStockPrice()** under the **IStockPriceService** node.</span></span>  
  
         <span data-ttu-id="51f7e-143">Die **GetStockPrice()** -Methode wird im rechten Bereich mit einem Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51f7e-143">The **GetStockPrice()** method appears in the right pane, with one parameter.</span></span>  
  
    2.  <span data-ttu-id="51f7e-144">Geben Sie "Contoso" als Wert für den Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="51f7e-144">Type in Contoso as the value for the parameter.</span></span>  
  
    3.  <span data-ttu-id="51f7e-145">Klicken Sie auf **Aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="51f7e-145">Click **Invoke**.</span></span>  
  
12. <span data-ttu-id="51f7e-146">Sehen Sie sich die nachverfolgten Ereignisse in der Protokolldatei an, die sich im Anwendungsdatenverzeichnis unter "%APPDATA%\trackingRecords.log" befindet.</span><span class="sxs-lookup"><span data-stu-id="51f7e-146">See the tracked events in the log file located in your application data directory at %APPDATA%\trackingRecords.log.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51f7e-147">%Appdata% ist eine Umgebungsvariable, die zu %SystemDrive%\Users aufgelöst\\< Benutzername\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], oder Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="51f7e-147">The %APPDATA% is an environment variable that resolves to %SystemDrive%\Users\\<username\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], or Windows Server 2008.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="51f7e-148">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="51f7e-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="51f7e-149">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="51f7e-149">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="51f7e-150">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="51f7e-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="51f7e-151">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="51f7e-151">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a><span data-ttu-id="51f7e-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51f7e-152">See Also</span></span>  
 [<span data-ttu-id="51f7e-153">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="51f7e-153">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
