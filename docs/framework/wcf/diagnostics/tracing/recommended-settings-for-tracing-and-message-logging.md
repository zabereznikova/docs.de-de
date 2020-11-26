---
title: Empfohlene Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung
description: Erfahren Sie mehr über empfohlene Einstellungen für Ablauf Verfolgung und Nachrichten Protokollierung für verschiedene Betriebsumgebungen in WCF.
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: b23298b8ee95b3bcd61a3712e9ff91acf6a6a3e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240094"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="a425a-103">Empfohlene Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="a425a-103">Recommended Settings for Tracing and Message Logging</span></span>

<span data-ttu-id="a425a-104">In diesem Thema werden empfohlene Ablaufverfolgungs- und Nachrichtenprotokollierungseinstellungen für andere Arbeitsumfelder beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a425a-104">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="a425a-105">Empfohlene Einstellungen für eine Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="a425a-105">Recommended Settings for a Production Environment</span></span>  

 <span data-ttu-id="a425a-106">Legen Sie in einer Produktionsumgebung, wenn Sie WCF-Ablaufverfolgungsquellen verwenden, `switchValue` auf Warnung fest.</span><span class="sxs-lookup"><span data-stu-id="a425a-106">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="a425a-107">Legen Sie, wenn Sie die WCF `System.ServiceModel`-Ablaufverfolgungsquelle verwenden, das `switchValue`-Attribut auf `Warning` und das `propagateActivity`-Attribut auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="a425a-107">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="a425a-108">Legen Sie, wenn Sie eine benutzerdefinierte Ablaufverfolgungsquelle verwenden, das `switchValue`-Attribut auf `Warning, ActivityTracing` fest.</span><span class="sxs-lookup"><span data-stu-id="a425a-108">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="a425a-109">Dies kann manuell mithilfe des- [Konfigurations-Editor-Tools (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md)erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a425a-109">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="a425a-110">Wenn Sie keinen Treffer in der Leistung erwarten, können Sie das `switchValue`-Attribut in allen zuvor erwähnten Fällen auf `Information` festlegen, wodurch relativ viele Ablaufverfolgungsdaten generiert werden.</span><span class="sxs-lookup"><span data-stu-id="a425a-110">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="a425a-111">Im folgenden Beispiel werden diese empfohlenen Einstellungen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a425a-111">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="a425a-112">Empfohlene Einstellungen für Bereitstellung oder Debuggen</span><span class="sxs-lookup"><span data-stu-id="a425a-112">Recommended Settings for Deployment or Debugging</span></span>  

 <span data-ttu-id="a425a-113">Wählen Sie in einer Bereitstellungs- oder Debugumgebung `Information` oder `Verbose` zusammen mit `ActivityTracing` entweder für eine benutzerdefinierte oder `System.ServiceModel`-Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="a425a-113">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="a425a-114">Zum Optimieren des Debugvorgangs müssen Sie der Konfiguration auch eine zusätzliche Ablaufverfolgungsquelle (`System.ServiceModel.MessageLogging`) hinzufügen, um die Meldungsprotokollierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a425a-114">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="a425a-115">Beachten Sie, dass das `switchValue`-Attribut keine Auswirkungen auf diese Ablaufverfolgungsquelle hat.</span><span class="sxs-lookup"><span data-stu-id="a425a-115">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="a425a-116">Im folgenden Beispiel keyword werden die empfohlenen Einstellungen veranschaulicht und ein freigegebener Listener wird verwendet, der das `XmlWriterTraceListener` nutzt.</span><span class="sxs-lookup"><span data-stu-id="a425a-116">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging
           logEntireMessage="true"
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="a425a-117">Verwenden von WMI zum Ändern von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a425a-117">Using WMI to Modify Settings</span></span>  

 <span data-ttu-id="a425a-118">Mit WMI können Sie Konfigurationseinstellungen zur Laufzeit ändern (durch Aktivieren des `wmiProviderEnabled`-Attributs in der Konfiguration, wie im vorherigen Konfigurationsbeispiel dargestellt).</span><span class="sxs-lookup"><span data-stu-id="a425a-118">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="a425a-119">Sie können beispielsweise mit WMI im CIM-Studio zur Laufzeit die Ablaufverfolgungsquellenebenen von Warnung in Information ändern.</span><span class="sxs-lookup"><span data-stu-id="a425a-119">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="a425a-120">Beachten Sie dabei, dass die Leistungseinbußen von Livedebuggen auf diese Weise sehr hoch sein können.</span><span class="sxs-lookup"><span data-stu-id="a425a-120">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="a425a-121">Weitere Informationen zur Verwendung von WMI finden Sie im Thema [Verwenden von Windows-Verwaltungsinstrumentation für die Diagnose](../wmi/index.md) .</span><span class="sxs-lookup"><span data-stu-id="a425a-121">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="a425a-122">Aktivieren von korrelierenden Ereignissen in der ASP.NET-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="a425a-122">Enable Correlated Events in ASP.NET Tracing</span></span>  

 <span data-ttu-id="a425a-123">ASP.NET-Ereignisse legen die Korrelation-ID (ActivityID) nicht fest, außer wenn die Ablaufverfolgung von ASP.NET-Ereignissen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="a425a-123">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="a425a-124">Um Korrelierte Ereignisse ordnungsgemäß anzuzeigen, müssen Sie die ASP.NET-Ereignis Ablauf Verfolgung mit dem folgenden Befehl in der Befehlskonsole aktivieren. dieser Befehl kann aufgerufen werden, indem Sie zu **Start**, **Ausführen** und **cmd** eingeben.</span><span class="sxs-lookup"><span data-stu-id="a425a-124">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="a425a-125">Verwenden Sie den folgenden Befehl, um die Ablaufverfolgung von ASP.NET-Ereignissen zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="a425a-125">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="a425a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a425a-126">See also</span></span>

- [<span data-ttu-id="a425a-127">Verwenden von Windows-Verwaltungsinstrumentation für die Diagnose</span><span class="sxs-lookup"><span data-stu-id="a425a-127">Using Windows Management Instrumentation for Diagnostics</span></span>](../wmi/index.md)
