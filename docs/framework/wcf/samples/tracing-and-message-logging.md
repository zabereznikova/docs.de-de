---
title: Ablaufverfolgung und Nachrichtenprotokollierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: "53"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91d824efaf8f58074297c417990ecf6b3aef78eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="tracing-and-message-logging"></a>Ablaufverfolgung und Nachrichtenprotokollierung
In diesem Beispiel wird das Aktivieren der Ablaufverfolgung und Nachrichtenprotokollierung veranschaulicht. Die resultierende ablaufverfolgungen und Nachrichtenprotokollen mit angezeigt werden die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## <a name="tracing"></a>Ablaufverfolgung  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet den im <xref:System.Diagnostics>-Namespace definierten Ablaufverfolgungsmechanismus. In diesem Ablaufverfolgungsmodell werden Ablaufverfolgungsdaten von Ablaufverfolgungsquellen erzeugt, die von Anwendungen implementiert werden. Jede Quelle wird durch einen Namen identifiziert. Ablaufverfolgungsconsumer erstellen Ablaufverfolgungslistener für die Ablaufverfolgungsquellen, für die sie Informationen abrufen möchten. Sie müssen einen Listener für die Ablaufverfolgungsquelle erstellen, um Ablaufverfolgungsdaten zum empfangen. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann hierzu der folgende Code in der Konfigurationsdatei des Diensts oder Clients hinzugefügt werden, indem die Dienstmodell-Ablaufverfolgungsquelle `switchValue` festgelegt wird:  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 Weitere Informationen zu Ablaufverfolgungsquellen, finden Sie im Abschnitt Ablaufverfolgungsquelle in der [Konfigurieren der Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) Thema.  
  
## <a name="activity-tracing-and-propagation"></a>Aktivitätsablaufverfolgung und Weitergabe  
 Mit `ActivityTracing` aktiviert und `propagateActivity` festgelegt `true` in die `system.ServiceModel` Ablaufverfolgungsquellen für Client und Dienst Korrelation von ablaufverfolgungen in logischen Verarbeitungseinheiten (Aktivitäten), geben Sie über Aktivitäten innerhalb von Endpunkten ( durch aktivitätsübertragungen) und über Aktivitäten über mehrere Endpunkte (über die ID-Aktivitätsweitergabe).  
  
 Mithilfe dieser drei Mechanismen (Aktivitäten, Übertragungen und Weitergabe) können Sie die Grundursache eines Fehlers schneller mit dem Tool Service Trace Viewer ermitteln. Weitere Informationen finden Sie unter [mithilfe von Service Trace Viewer für korrelierte Ablaufverfolgungen anzeigen und Problembehandlung](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Durch das Erstellen von benutzerdefinierten Aktivitätsablaufverfolgungen kann die von ServiceModel bereitgestellte Ablaufverfolgung erweitert werden. Durch die benutzerdefinierte Aktivitätsablaufverfolgung kann der Benutzer Ablaufverfolgungsaktivitäten für folgenden Aktionen erstellen:  
  
-   Gruppieren von Ablaufverfolgungen in logische Arbeitseinheiten.  
  
-   Korrelieren von Aktivitäten durch Übertragungen und Weitergabe.  
  
-   Verringern der Leistungskosten für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Ablaufverfolgung (beispielsweise der benötigte Speicherplatz für eine Protokolldatei).  
  
 Weitere Informationen über eine benutzerdefinierte Aktivität Ablaufverfolgung finden Sie unter der [erweitern Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) Beispiel.  
  
## <a name="message-logging"></a>Nachrichtenprotokollierung  
 Die Nachrichtenprotokollierung kann auf dem Client und dem Dienst aller [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen aktiviert werden. Zum Aktivieren der Nachrichtenprotokollierung müssen Sie dem Client oder dem Dienst den folgenden Code hinzufügen:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels >  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 Wenn eine Nachricht aufgezeichnet wird, ist der Ablaufverfolgungstyp abhängig davon, ob die Ablaufverfolgung beim Client oder beim Server erfolgt. Eine "Add"-Nachricht, die an einen Client gesendet wird, wird beispielsweise in der Kategorie "TransportWrite" beim Client verfolgt, während die gleiche Nachricht beim Dienst in der Kategorie "TransportRead" verfolgt wird.  
  
 Konfigurieren Sie den Ablaufverfolgungslistener, indem Sie den folgenden Code im <xref:System.Diagnostics>-Abschnitt der Datei "App.config" für den Client oder der Datei "Web.config" für den Dienst hinzufügen:  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 Nachrichten werden im XML-Format in dem in der Konfigurationsdatei angegebenen Zielverzeichnis protokolliert.  
  
> [!NOTE]
>  Ablaufverfolgungsdateien werden nur erstellt, wenn zuerst das Protokollverzeichnis erstellt wurde. Stellen Sie sicher, dass das Verzeichnis C:\logs\ vorhanden ist, oder geben Sie ein anderes Protokollierungsverzeichnis in der Listenerkonfiguration an. Weitere Informationen finden Sie in den Anweisungen zum ersten Einrichten am Ende dieses Dokuments.  
  
 Weitere Informationen zur nachrichtenprotokollierung finden Sie unter der [Konfigurieren der Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) Thema.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Bevor Sie das Beispiel zur Ablaufverfolgung und Nachrichtenprotokollierung ausführen, erstellen Sie das Verzeichnis C:\logs\, in das der Dienst die SVCLOG-Dateien schreiben kann. Der Name dieses Verzeichnisses wird in der Konfigurationsdatei als Pfad für die zu protokollierenden Ablaufverfolgungen und Nachrichten definiert und kann geändert werden. Weisen Sie dem Benutzer Network Service Schreibzugriff für das Protokollverzeichnis zu.  
  
3.  Führen Sie zum Erstellen der C#-, C++ oder Visual Basic .NET Edition der Lösung die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Überwachen der AppFabric-Beispiele](http://go.microsoft.com/fwlink/?LinkId=193959)
