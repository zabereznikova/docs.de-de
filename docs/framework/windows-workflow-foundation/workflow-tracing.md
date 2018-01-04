---
title: "Workflowüberwachung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b07dda940e35746a4d57c0cd300375692c6ab2f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-tracing"></a><span data-ttu-id="0c153-102">Workflowüberwachung</span><span class="sxs-lookup"><span data-stu-id="0c153-102">Workflow Tracing</span></span>
<span data-ttu-id="0c153-103">Die Workflowüberwachung bietet eine Möglichkeit, Diagnoseinformationen mit .NET Framework-Ablaufverfolgungslistenern zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="0c153-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="0c153-104">Die Ablaufverfolgung kann aktiviert werden, wenn ein Problem mit der Anwendung erkannt wird, und dann wieder deaktiviert werden, sobald das Problem behoben ist.</span><span class="sxs-lookup"><span data-stu-id="0c153-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="0c153-105">Es gibt zwei Methoden zur Aktivierung der Debugablaufverfolgung für Workflows.</span><span class="sxs-lookup"><span data-stu-id="0c153-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="0c153-106">Sie können sie mit der Ereignisablaufverfolgung (ETW) konfigurieren, oder Sie können Ablaufverfolgungsereignisse mit <xref:System.Diagnostics> an eine Datei senden.</span><span class="sxs-lookup"><span data-stu-id="0c153-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="0c153-107">Aktivieren der Debugablaufverfolgung in ETW</span><span class="sxs-lookup"><span data-stu-id="0c153-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="0c153-108">Zum Aktivieren der Ablaufverfolgung in ETW aktivieren Sie den Debugkanal in der Ereignisanzeige:</span><span class="sxs-lookup"><span data-stu-id="0c153-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1.  <span data-ttu-id="0c153-109">Navigieren Sie in der Ereignisanzeige zum Knoten für analytische und Debugprotokolle.</span><span class="sxs-lookup"><span data-stu-id="0c153-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2.  <span data-ttu-id="0c153-110">Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige -> Anwendungen und Dienstprotokolle -> Microsoft -> Windows -> Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="0c153-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="0c153-111">Mit der rechten Maustaste **Anwendungsserver-Anwendungen** , und wählen Sie **anzeigen -> Anzeigen analytische und Debugprotokolle**.</span><span class="sxs-lookup"><span data-stu-id="0c153-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="0c153-112">Mit der rechten Maustaste **Debuggen** , und wählen Sie **Protokoll aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="0c153-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3.  <span data-ttu-id="0c153-113">Wenn ein Workflow den Debugmodus ausführt und die Ablaufverfolgungen an den Debugkanal in ETW ausgegeben werden, können Sie diese in der Ereignisanzeige anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c153-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="0c153-114">Navigieren Sie zu **Ereignisanzeige -> Anwendungen und Dienstprotokolle -> Microsoft -> Windows -> Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="0c153-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="0c153-115">Mit der rechten Maustaste **Debuggen** , und wählen Sie **aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="0c153-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4.  <span data-ttu-id="0c153-116">Die Standardpuffergröße für die analytische Ablaufverfolgung beträgt nur 4 Kilobytes (KB). Es wird empfohlen, die Größe auf 32 KB zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0c153-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="0c153-117">Gehen Sie hierzu folgendermaßen vor.</span><span class="sxs-lookup"><span data-stu-id="0c153-117">To do this, perform the following steps.</span></span>  
  
    1.  <span data-ttu-id="0c153-118">Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus: `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="0c153-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2.  <span data-ttu-id="0c153-119">Ändern der \<BufferSize > Wert in der Datei "Windows.ApplicationServer.Applications.man" 32 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0c153-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  <span data-ttu-id="0c153-120">Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus: `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="0c153-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c153-121">Wenn Sie die .NET Framework 4 Client Profile verwenden, müssen Sie zuerst das ETW-Manifest registrieren, durch Ausführen des folgenden Befehls aus dem .NET Framework 4-Verzeichnis:`ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="0c153-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="0c153-122">Aktivieren der Debugablaufverfolgung mit System.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="0c153-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="0c153-123">Diese Listener können in der Datei App.config der Workflowanwendung konfiguriert werden bzw. in der Datei Web.config, wenn es sich um einen Workflowdienst handelt.</span><span class="sxs-lookup"><span data-stu-id="0c153-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="0c153-124">In diesem Beispiel wird eine [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) konfiguriert ist, um Ablaufverfolgungsinformationen in der Datei "MyTraceLog.txt" im aktuellen Verzeichnis zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0c153-124">In this example, a [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c153-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c153-125">See Also</span></span>  
 [<span data-ttu-id="0c153-126">Windows Server App Fabric-Überwachung</span><span class="sxs-lookup"><span data-stu-id="0c153-126">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="0c153-127">Überwachen von Anwendungen mit AppFabric</span><span class="sxs-lookup"><span data-stu-id="0c153-127">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
