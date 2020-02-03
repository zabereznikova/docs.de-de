---
title: Erweitern der Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: c6d62f6c334261b0dc897a1c1a2cd71d40ee4f51
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734921"
---
# <a name="extending-tracing"></a>Erweitern der Ablaufverfolgung
In diesem Beispiel wird veranschaulicht, wie die Windows Communication Foundation (WCF)-Ablauf Verfolgungs Funktion erweitert wird, indem benutzerdefinierte Aktivitäts Ablauf Verfolgungen in Client-und Dienst Code geschrieben werden. Dies ermöglicht es dem Benutzer, Ablaufverfolgungsaktivitäten zu erstellen und Ablaufverfolgungen in logischen Arbeitseinheiten zu gruppieren. Es ist auch möglich, Aktivitäten über Übertragungen (innerhalb desselben Endpunkts) und Weitergabe (über verschiedene Endpunkte) zu korrelieren. In diesem Beispiel wird Ablaufverfolgung sowohl für den Client als auch den Dienst aktiviert. Weitere Informationen zum Aktivieren der Ablauf Verfolgung in Client-und Dienst Konfigurationsdateien finden Sie unter Ablauf [Verfolgung und Nachrichten Protokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 Dieses Beispiel basiert [auf den ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritten.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a>Ablaufverfolgung und Aktivitätsweitergabe  
 Die benutzerdefinierte Aktivitäts Ablauf Verfolgung ermöglicht dem Benutzer das Erstellen eigener Ablauf Verfolgungs Aktivitäten, um Ablauf Verfolgungen in logische Arbeitseinheiten zu gruppieren, Aktivitäten über Übertragungen und Weitergabe zu korrelieren und die Leistungskosten der WCF-Ablauf Verfolgung zu verringern (z. b. die Kosten für den Speicherplatz). einer Protokolldatei).  
  
### <a name="adding-custom-sources"></a>Hinzufügen benutzerdefinierter Quellen  
 Benutzerdefinierte Ablaufverfolgungen können sowohl zu Client- als auch Dienstcode hinzugefügt werden. Durch das Hinzufügen von Ablauf Verfolgungs Quellen zu den Client-oder Dienst Konfigurationsdateien können diese benutzerdefinierten Ablauf Verfolgungen aufgezeichnet und im [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)angezeigt werden. Der folgende Code zeigt, wie der Konfigurationsdatei eine benutzerdefinierte Ablaufverfolgungsquelle namens `ServerCalculatorTraceSource` hinzugefügt wird.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a>Korrelieren von Aktivitäten  
 Zum Korrelieren von Aktivitäten direkt zwischen Endpunkten muss für das `propagateActivity`-Attribut in der `true`-Ablaufverfolgungsquelle der Wert `System.ServiceModel` festgelegt werden. Außerdem muss die Service Model-Aktivitäts Ablauf Verfolgung deaktiviert werden, damit Ablauf Verfolgungen ohne WCF-Aktivitäten weitergegeben werden können. Dies ist im folgenden Codebeispiel zu erkennen.  
  
> [!NOTE]
> Das Deaktivieren von ServiceModel-Aktivitätsablaufverfolgung ist nicht dasselbe, wie die von der `switchValue`-Eigenschaft angegebene Ablaufverfolgungsebene zu deaktivieren.  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a>Verringern von Leistungskosten  
 Wenn `ActivityTracing` in der `System.ServiceModel`-Ablaufverfolgungsquelle ausgeschaltet wird, wird eine Ablaufverfolgungsdatei erstellt, die nur benutzerdefinierte Aktivitätsablaufverfolgungen, jedoch keine der ServiceModel-Aktivitätsablaufverfolgungen enthält. Dadurch wird die Protokolldatei deutlich kleiner. Die Möglichkeit zum Korrelieren von WCF-Verarbeitungs Ablauf Verfolgungen geht jedoch verloren.  
  
##### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungs Beispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
