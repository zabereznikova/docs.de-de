---
title: Ablaufverfolgung und Nachrichtenprotokollierung
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: f6f2fd0bbbc191d466ac600bd9639c8955d5b7fe
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715677"
---
# <a name="tracing-and-message-logging"></a>Ablaufverfolgung und Nachrichtenprotokollierung
In diesem Beispiel wird das Aktivieren der Ablaufverfolgung und Nachrichtenprotokollierung veranschaulicht. Die resultierenden Ablauf Verfolgungen und Nachrichten Protokolle werden mit dem [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)angezeigt. Dieses Beispiel basiert [auf den ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritten.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## <a name="tracing"></a>Ablaufverfolgung  
 Windows Communication Foundation (WCF) verwendet den Ablauf Verfolgungs Mechanismus, der im <xref:System.Diagnostics>-Namespace definiert ist. In diesem Ablaufverfolgungsmodell werden Ablaufverfolgungsdaten von Ablaufverfolgungsquellen erzeugt, die von Anwendungen implementiert werden. Jede Quelle wird durch einen Namen identifiziert. Ablaufverfolgungsconsumer erstellen Ablaufverfolgungslistener für die Ablaufverfolgungsquellen, für die sie Informationen abrufen möchten. Sie müssen einen Listener für die Ablaufverfolgungsquelle erstellen, um Ablaufverfolgungsdaten zum empfangen. In WCF kann dies erreicht werden, indem der folgende Code entweder in der Konfigurationsdatei des dienstanders oder des Clients hinzugefügt wird, indem die `switchValue`der Dienstmodell-Ablauf Verfolgungs Quelle festgelegt wird:  
  
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
  
 Weitere Informationen zu Ablauf Verfolgungs Quellen finden Sie im Abschnitt "Ablauf Verfolgungs Quelle" im Thema Konfigurieren der Ablauf [Verfolgung](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) .  
  
## <a name="activity-tracing-and-propagation"></a>Aktivitätsablaufverfolgung und Weitergabe  
 Wenn `ActivityTracing` aktiviert und `propagateActivity` auf `true` in den `system.ServiceModel`-Ablauf Verfolgungs Quellen für den Client und den Dienst festgelegt ist, stellen Sie die Korrelation von Ablauf Verfolgungen innerhalb logischer Verarbeitungseinheiten (Aktivitäten), über Aktivitäten innerhalb von Endpunkten (über Aktivitäts Übertragungen) und über Aktivitäten hinweg bereit, die mehrere Endpunkte umfassen (über die Aktivitäts-ID-Propagierung).  
  
 Mithilfe dieser drei Mechanismen (Aktivitäten, Übertragungen und Weitergabe) können Sie die Grundursache eines Fehlers schneller mit dem Tool Service Trace Viewer ermitteln. Weitere Informationen finden Sie unter [Verwenden von Service Trace Viewer zum Anzeigen korrelierter Ablauf Verfolgungen und Problem](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)Behandlung.  
  
 Durch das Erstellen von benutzerdefinierten Aktivitätsablaufverfolgungen kann die von ServiceModel bereitgestellte Ablaufverfolgung erweitert werden. Durch die benutzerdefinierte Aktivitätsablaufverfolgung kann der Benutzer Ablaufverfolgungsaktivitäten für folgenden Aktionen erstellen:  
  
- Gruppieren von Ablaufverfolgungen in logische Arbeitseinheiten.  
  
- Korrelieren von Aktivitäten durch Übertragungen und Weitergabe.  
  
- Verringern der Leistungskosten der WCF-Ablauf Verfolgung (z. b. der Speicherplatz Kosten einer Protokolldatei).  
  
 Weitere Informationen zur benutzerdefinierten Aktivitäts Ablauf Verfolgung finden Sie im Beispiel zum [erweitern](../../../../docs/framework/wcf/samples/extending-tracing.md) der Ablauf Verfolgung.  
  
## <a name="message-logging"></a>Nachrichtenprotokollierung  
 Die Nachrichten Protokollierung kann sowohl auf dem Client als auch auf dem Dienst einer beliebigen WCF-Anwendung aktiviert werden. Zum Aktivieren der Nachrichtenprotokollierung müssen Sie dem Client oder dem Dienst den folgenden Code hinzufügen:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels -->  
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
> Ablaufverfolgungsdateien werden nur erstellt, wenn zuerst das Protokollverzeichnis erstellt wurde. Stellen Sie sicher, dass das Verzeichnis C:\logs\ vorhanden ist, oder geben Sie ein anderes Protokollierungsverzeichnis in der Listenerkonfiguration an. Weitere Informationen finden Sie in den Anweisungen zum ersten Einrichten am Ende dieses Dokuments.  
  
 Weitere Informationen zur Nachrichten Protokollierung finden Sie im Thema [Konfigurieren der Nachrichten Protokollierung](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) .  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Bevor Sie das Beispiel zur Ablaufverfolgung und Nachrichtenprotokollierung ausführen, erstellen Sie das Verzeichnis C:\logs\, in das der Dienst die SVCLOG-Dateien schreiben kann. Der Name dieses Verzeichnisses wird in der Konfigurationsdatei als Pfad für die zu protokollierenden Ablaufverfolgungen und Nachrichten definiert und kann geändert werden. Weisen Sie dem Benutzer Network Service Schreibzugriff für das Protokollverzeichnis zu.  
  
3. Befolgen Sie zum C#erstellen C++der-,-oder-Visual Basic .NET-Edition der Projekt Mappe die Anweisungen unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [AppFabric-Überwachungs Beispiele](https://go.microsoft.com/fwlink/?LinkId=193959)
