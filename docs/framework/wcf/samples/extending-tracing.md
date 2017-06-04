---
title: "Erweitern der Ablaufverfolgung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Erweitern der Ablaufverfolgung
Dieses Beispiel veranschaulicht, wie die Ablaufverfolgungsfunktion von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] erweitert wird, indem man im Client\- und im Dienstcode Aktivitätsablaufverfolgungen schreibt.Dies ermöglicht es dem Benutzer, Ablaufverfolgungsaktivitäten zu erstellen und Ablaufverfolgungen in logischen Arbeitseinheiten zu gruppieren.Es ist auch möglich, Aktivitäten über Übertragungen \(innerhalb desselben Endpunkts\) und Weitergabe \(über verschiedene Endpunkte\) zu korrelieren.In diesem Beispiel wird Ablaufverfolgung sowohl für den Client als auch den Dienst aktiviert.Weitere Informationen dazu, wie man die Ablaufverfolgung in Client und Dienstkonfigurationsdateien aktiviert, finden Sie unter [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## Ablaufverfolgung und Aktivitätsweitergabe  
 Mithilfe von benutzerdefinierter Aktivitätsweitergabe kann der Benutzer eigene Ablaufverfolgungsaktivitäten erstellen, um Ablaufverfolgungen in logische Arbeitseinheiten zu gruppieren, Aktivitäten über Übertragungen und Weitergabe zu korrelieren und die Leistungskosten von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Ablaufverfolgung \(z. B. die Kosten des von einer Protokolldatei belegten Festplattenspeicherplatzes\) zu verringern.  
  
### Hinzufügen benutzerdefinierter Quellen  
 Benutzerdefinierte Ablaufverfolgungen können sowohl zu Client\- als auch Dienstcode hinzugefügt werden.Wenn den Client\- oder Dienstkonfigurationsdateien Ablaufverfolgungsquellen hinzugefügt werden, können diese benutzerdefinierten Ablaufverfolgungen aufgezeichnet und im [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) angezeigt werden.Der folgende Code zeigt, wie der Konfigurationsdatei eine benutzerdefinierte Ablaufverfolgungsquelle namens `ServerCalculatorTraceSource` hinzugefügt wird.  
  
```  
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
  
### Korrelieren von Aktivitäten  
 Zum Korrelieren von Aktivitäten direkt zwischen Endpunkten muss für das `propagateActivity`\-Attribut in der `System.ServiceModel`\-Ablaufverfolgungsquelle der Wert `true` festgelegt werden.Außerdem muss, um Ablaufverfolgungen weiterzugeben, ohne über [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Aktivitäten zu gehen, ServiceModel\-Aktivitätsablaufverfolgung deaktiviert werden.Dies ist im folgenden Codebeispiel zu erkennen.  
  
> [!NOTE]
>  Das Deaktivieren von ServiceModel\-Aktivitätsablaufverfolgung ist nicht dasselbe, wie die von der `switchValue`\-Eigenschaft angegebene Ablaufverfolgungsebene zu deaktivieren.  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### Verringern von Leistungskosten  
 Wenn `ActivityTracing` in der `System.ServiceModel`\-Ablaufverfolgungsquelle ausgeschaltet wird, wird eine Ablaufverfolgungsdatei erstellt, die nur benutzerdefinierte Aktivitätsablaufverfolgungen, jedoch keine der ServiceModel\-Aktivitätsablaufverfolgungen enthält.Dadurch wird die Protokolldatei deutlich kleiner.Allerdings verliert man damit die Möglichkeit, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Verarbeitungsablaufverfolgungen zu korrelieren.  
  
##### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Siehe auch  
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)