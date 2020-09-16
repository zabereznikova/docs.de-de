---
title: Workflowüberwachung
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: fc27be295cbf0a83b65ff03e36f2aeffeda12db9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557501"
---
# <a name="workflow-tracing"></a><span data-ttu-id="dac7f-102">Workflowüberwachung</span><span class="sxs-lookup"><span data-stu-id="dac7f-102">Workflow Tracing</span></span>
<span data-ttu-id="dac7f-103">Die Workflowüberwachung bietet eine Möglichkeit, Diagnoseinformationen mit .NET Framework-Ablaufverfolgungslistenern zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="dac7f-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="dac7f-104">Die Ablaufverfolgung kann aktiviert werden, wenn ein Problem mit der Anwendung erkannt wird, und dann wieder deaktiviert werden, sobald das Problem behoben ist.</span><span class="sxs-lookup"><span data-stu-id="dac7f-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="dac7f-105">Es gibt zwei Methoden zur Aktivierung der Debugablaufverfolgung für Workflows.</span><span class="sxs-lookup"><span data-stu-id="dac7f-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="dac7f-106">Sie können sie mit der Ereignisablaufverfolgung (ETW) konfigurieren, oder Sie können Ablaufverfolgungsereignisse mit <xref:System.Diagnostics> an eine Datei senden.</span><span class="sxs-lookup"><span data-stu-id="dac7f-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="dac7f-107">Aktivieren der Debugablaufverfolgung in ETW</span><span class="sxs-lookup"><span data-stu-id="dac7f-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="dac7f-108">Zum Aktivieren der Ablaufverfolgung in ETW aktivieren Sie den Debugkanal in der Ereignisanzeige:</span><span class="sxs-lookup"><span data-stu-id="dac7f-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1. <span data-ttu-id="dac7f-109">Navigieren Sie in der Ereignisanzeige zum Knoten für analytische und Debugprotokolle.</span><span class="sxs-lookup"><span data-stu-id="dac7f-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2. <span data-ttu-id="dac7f-110">Navigieren Sie in der Strukturansicht in Ereignisanzeige zu **Ereignisanzeige >Anwendungs-und Dienst Protokolle->Microsoft->Windows->Anwendungs Server-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="dac7f-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="dac7f-111">Klicken Sie mit der rechten Maustaste auf **Anwendungs Server-Anwendungen** , und wählen Sie **Ansicht->analytische und Debugprotokolle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="dac7f-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="dac7f-112">Klicken Sie mit der rechten Maustaste auf **Debug** , und wählen Sie **Protokoll aktivieren**</span><span class="sxs-lookup"><span data-stu-id="dac7f-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3. <span data-ttu-id="dac7f-113">Wenn ein Workflow den Debugmodus ausführt und die Ablaufverfolgungen an den Debugkanal in ETW ausgegeben werden, können Sie diese in der Ereignisanzeige anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dac7f-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="dac7f-114">Navigieren Sie zu **Ereignisanzeige->Anwendungs-und Dienst Protokolle->Microsoft->Windows->Anwendungs Server-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="dac7f-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="dac7f-115">Klicken Sie mit der rechten Maustaste auf **Debug** , **und wählen Sie**</span><span class="sxs-lookup"><span data-stu-id="dac7f-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4. <span data-ttu-id="dac7f-116">Die Standardpuffergröße für die analytische Ablaufverfolgung beträgt nur 4 Kilobytes (KB). Es wird empfohlen, die Größe auf 32 KB zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="dac7f-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="dac7f-117">Führen Sie dazu die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="dac7f-117">To do this, perform the following steps.</span></span>  
  
    1. <span data-ttu-id="dac7f-118">Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus: `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="dac7f-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2. <span data-ttu-id="dac7f-119">Ändern \<bufferSize> Sie den Wert in der Datei "Windows. ApplicationServer. Applications. man" in "32".</span><span class="sxs-lookup"><span data-stu-id="dac7f-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. <span data-ttu-id="dac7f-120">Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus: `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="dac7f-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dac7f-121">Wenn Sie das .NET Framework 4-Client Profil verwenden, müssen Sie zuerst das ETW-Manifest registrieren, indem Sie den folgenden Befehl im Verzeichnis ".NET Framework 4" ausführen: `ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="dac7f-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="dac7f-122">Aktivieren der Debugablaufverfolgung mit System.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="dac7f-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="dac7f-123">Diese Listener können in der Datei App.config der Workflowanwendung konfiguriert werden bzw. in der Datei Web.config, wenn es sich um einen Workflowdienst handelt.</span><span class="sxs-lookup"><span data-stu-id="dac7f-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="dac7f-124">In diesem Beispiel ist ein <xref:System.Diagnostics.TextWriterTraceListener> so konfiguriert, dass Ablauf Verfolgungs Informationen in der MyTraceLog.txt-Datei im aktuellen Verzeichnis gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="dac7f-124">In this example, a <xref:System.Diagnostics.TextWriterTraceListener> is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dac7f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dac7f-125">See also</span></span>

- <span data-ttu-id="dac7f-126">[Windows Server-App-Fabric-Überwachung](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="dac7f-126">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="dac7f-127">[Überwachen von Anwendungen mit App-Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="dac7f-127">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
