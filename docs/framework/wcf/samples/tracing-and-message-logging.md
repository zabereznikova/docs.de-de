---
title: "Ablaufverfolgung und Nachrichtenprotokollierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Ablaufverfolgung und Protokollierung"
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: 53
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 53
---
# Ablaufverfolgung und Nachrichtenprotokollierung
In diesem Beispiel wird das Aktivieren der Ablaufverfolgung und Nachrichtenprotokollierung veranschaulicht.Die resultierenden Ablaufverfolgungen und Nachrichtenprotokolle werden mit dem [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) angezeigt.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## Ablaufverfolgung  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet den im <xref:System.Diagnostics>\-Namespace definierten Ablaufverfolgungsmechanismus.In diesem Ablaufverfolgungsmodell werden Ablaufverfolgungsdaten von Ablaufverfolgungsquellen erzeugt, die von Anwendungen implementiert werden.Jede Quelle wird durch einen Namen identifiziert.Ablaufverfolgungsconsumer erstellen Ablaufverfolgungslistener für die Ablaufverfolgungsquellen, für die sie Informationen abrufen möchten.Sie müssen einen Listener für die Ablaufverfolgungsquelle erstellen, um Ablaufverfolgungsdaten zum empfangen.In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann hierzu der folgende Code in der Konfigurationsdatei des Diensts oder Clients hinzugefügt werden, indem die Dienstmodell\-Ablaufverfolgungsquelle `switchValue` festgelegt wird:  
  
```  
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
  
 Weitere Informationen zu Ablaufverfolgungsquellen finden Sie im Abschnitt zu Ablaufverfolgungsquellen im Thema [Konfigurieren der Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
## Aktivitätsablaufverfolgung und Weitergabe  
 Wenn in den `system.ServiceModel`\-Ablaufverfolgungsquellen für den Client und den Dienst `ActivityTracing` aktiviert und `propagateActivity` auf `true` festgelegt ist, wird die Korrelation von Ablaufverfolgungen in logischen Verarbeitungseinheiten \(Aktivitäten\), über Aktivitäten mit Endpunkten hinweg \(durch Aktivitätsübertragungen\) und über Aktivitäten über mehrere Endpunkte hinweg \(durch Weitergabe der Aktivitäts\-IDs\) bereitgestellt.  
  
 Mithilfe dieser drei Mechanismen \(Aktivitäten, Übertragungen und Weitergabe\) können Sie die Ursache eines Fehlers schneller mit dem Tool Service Trace Viewer ermitteln.Weitere Informationen finden Sie unter [Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Durch das Erstellen von benutzerdefinierten Aktivitätsablaufverfolgungen kann die von ServiceModel bereitgestellte Ablaufverfolgung erweitert werden.Durch die benutzerdefinierte Aktivitätsablaufverfolgung kann der Benutzer Ablaufverfolgungsaktivitäten für folgenden Aktionen erstellen:  
  
-   Gruppieren von Ablaufverfolgungen in logische Arbeitseinheiten.  
  
-   Korrelieren von Aktivitäten durch Übertragungen und Weitergabe.  
  
-   Verringern der Leistungskosten für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Ablaufverfolgung \(beispielsweise der benötigte Speicherplatz für eine Protokolldatei\).  
  
 Weitere Informationen zur benutzerdefinierten Aktivitätsablaufverfolgung finden Sie im Beispiel [Erweitern der Ablaufverfolgung](../../../../docs/framework/wcf/samples/extending-tracing.md).  
  
## Nachrichtenprotokollierung  
 Die Nachrichtenprotokollierung kann auf dem Client und dem Dienst aller [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen aktiviert werden.Zum Aktivieren der Nachrichtenprotokollierung müssen Sie dem Client oder dem Dienst den folgenden Code hinzufügen:  
  
```  
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
  
 Wenn eine Nachricht aufgezeichnet wird, ist der Ablaufverfolgungstyp abhängig davon, ob die Ablaufverfolgung beim Client oder beim Server erfolgt.Eine "Add"\-Nachricht, die an einen Client gesendet wird, wird beispielsweise in der Kategorie "TransportWrite" beim Client verfolgt, während die gleiche Nachricht beim Dienst in der Kategorie "TransportRead" verfolgt wird.  
  
 Konfigurieren Sie den Ablaufverfolgungslistener, indem Sie den folgenden Code im <xref:System.Diagnostics>\-Abschnitt der Datei "App.config" für den Client oder der Datei "Web.config" für den Dienst hinzufügen:  
  
```  
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
  
 Nachrichten werden im XML\-Format in dem in der Konfigurationsdatei angegebenen Zielverzeichnis protokolliert.  
  
> [!NOTE]
>  Ablaufverfolgungsdateien werden nur erstellt, wenn zuerst das Protokollverzeichnis erstellt wurde.Stellen Sie sicher, dass das Verzeichnis C:\\logs\\ vorhanden ist, oder geben Sie ein anderes Protokollierungsverzeichnis in der Listenerkonfiguration an.Weitere Informationen finden Sie in den Anweisungen zum ersten Einrichten am Ende dieses Dokuments.  
  
 Weitere Informationen zur Nachrichtenprotokollierung finden Sie im Thema [Konfigurieren der Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md).  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Bevor Sie das Beispiel zur Ablaufverfolgung und Nachrichtenprotokollierung ausführen, erstellen Sie das Verzeichnis C:\\logs\\, in das der Dienst die SVCLOG\-Dateien schreiben kann.Der Name dieses Verzeichnisses wird in der Konfigurationsdatei als Pfad für die zu protokollierenden Ablaufverfolgungen und Nachrichten definiert und kann geändert werden.Weisen Sie dem Benutzer Network Service Schreibzugriff für das Protokollverzeichnis zu.  
  
3.  Folgen Sie zum Erstellen der C\#\-, C\+\+\- oder Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)