---
title: Workflowüberwachung
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: cd53ed834fdacb639b38346dca831ef4c3e26337
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321665"
---
# <a name="workflow-tracing"></a><span data-ttu-id="da264-102">Workflowüberwachung</span><span class="sxs-lookup"><span data-stu-id="da264-102">Workflow Tracing</span></span>
<span data-ttu-id="da264-103">Die Workflowüberwachung bietet eine Möglichkeit, Diagnoseinformationen mit .NET Framework-Ablaufverfolgungslistenern zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="da264-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="da264-104">Die Ablaufverfolgung kann aktiviert werden, wenn ein Problem mit der Anwendung erkannt wird, und dann wieder deaktiviert werden, sobald das Problem behoben ist.</span><span class="sxs-lookup"><span data-stu-id="da264-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="da264-105">Es gibt zwei Methoden zur Aktivierung der Debugablaufverfolgung für Workflows.</span><span class="sxs-lookup"><span data-stu-id="da264-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="da264-106">Sie können sie mit der Ereignisablaufverfolgung (ETW) konfigurieren, oder Sie können Ablaufverfolgungsereignisse mit <xref:System.Diagnostics> an eine Datei senden.</span><span class="sxs-lookup"><span data-stu-id="da264-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="da264-107">Aktivieren der Debugablaufverfolgung in ETW</span><span class="sxs-lookup"><span data-stu-id="da264-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="da264-108">Zum Aktivieren der Ablaufverfolgung in ETW aktivieren Sie den Debugkanal in der Ereignisanzeige:</span><span class="sxs-lookup"><span data-stu-id="da264-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1. <span data-ttu-id="da264-109">Navigieren Sie in der Ereignisanzeige zum Knoten für analytische und Debugprotokolle.</span><span class="sxs-lookup"><span data-stu-id="da264-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2. <span data-ttu-id="da264-110">In der Strukturansicht in der Ereignisanzeige, navigieren Sie zu **Ereignisanzeige -> Anwendungen und Dienstprotokolle > Microsoft -> Windows-Anwendungsserver-Anwendungen >**.</span><span class="sxs-lookup"><span data-stu-id="da264-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="da264-111">Mit der rechten Maustaste **Anwendungsserver-Anwendungen** , und wählen Sie **Ansicht-analytische und Debugprotokolle**.</span><span class="sxs-lookup"><span data-stu-id="da264-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="da264-112">Mit der rechten Maustaste **Debuggen** , und wählen Sie **Protokoll aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="da264-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3. <span data-ttu-id="da264-113">Wenn ein Workflow den Debugmodus ausführt und die Ablaufverfolgungen an den Debugkanal in ETW ausgegeben werden, können Sie diese in der Ereignisanzeige anzeigen.</span><span class="sxs-lookup"><span data-stu-id="da264-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="da264-114">Navigieren Sie zu **Ereignisanzeige -> Anwendungen und Dienstprotokolle > Microsoft -> Windows-Anwendungsserver-Anwendungen >**.</span><span class="sxs-lookup"><span data-stu-id="da264-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="da264-115">Mit der rechten Maustaste **Debuggen** , und wählen Sie **aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="da264-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4. <span data-ttu-id="da264-116">Die Standardpuffergröße für die analytische Ablaufverfolgung beträgt nur 4 Kilobytes (KB). Es wird empfohlen, die Größe auf 32 KB zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="da264-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="da264-117">Gehen Sie hierzu folgendermaßen vor.</span><span class="sxs-lookup"><span data-stu-id="da264-117">To do this, perform the following steps.</span></span>  
  
    1.  <span data-ttu-id="da264-118">Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus:</span><span class="sxs-lookup"><span data-stu-id="da264-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203):</span></span> `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2.  <span data-ttu-id="da264-119">Ändern der \<BufferSize >-Wert in der Datei "Windows.ApplicationServer.Applications.man" auf 32.</span><span class="sxs-lookup"><span data-stu-id="da264-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  <span data-ttu-id="da264-120">Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus:</span><span class="sxs-lookup"><span data-stu-id="da264-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203):</span></span> `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
>  <span data-ttu-id="da264-121">Wenn Sie die .NET Framework 4 Client Profile verwenden, müssen Sie zuerst das ETW-Manifest registrieren, mithilfe des folgenden Befehls aus dem .NET Framework 4-Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="da264-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory:</span></span> `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="da264-122">Aktivieren der Debugablaufverfolgung mit System.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="da264-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="da264-123">Diese Listener können in der Datei App.config der Workflowanwendung konfiguriert werden bzw. in der Datei Web.config, wenn es sich um einen Workflowdienst handelt.</span><span class="sxs-lookup"><span data-stu-id="da264-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="da264-124">In diesem Beispiel eine [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) konfiguriert, um Ablaufverfolgungsinformationen in die Datei MyTraceLog.txt im aktuellen Verzeichnis zu speichern.</span><span class="sxs-lookup"><span data-stu-id="da264-124">In this example, a [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da264-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da264-125">See also</span></span>

- [<span data-ttu-id="da264-126">Windows Server App Fabric-Überwachung</span><span class="sxs-lookup"><span data-stu-id="da264-126">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="da264-127">Überwachen von Anwendungen mit AppFabric</span><span class="sxs-lookup"><span data-stu-id="da264-127">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
