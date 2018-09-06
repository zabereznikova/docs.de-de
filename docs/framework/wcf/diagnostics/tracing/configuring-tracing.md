---
title: Konfigurieren der Ablaufverfolgung
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [WCF]
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
ms.openlocfilehash: c5064d90c8601ee44be593446b0fd5ad483e57f2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43884067"
---
# <a name="configuring-tracing"></a>Konfigurieren der Ablaufverfolgung
In diesem Thema wird Folgendes beschrieben: das Aktivieren der Ablaufverfolgung, das Konfigurieren von Ablaufverfolgungsquellen zum Ausgeben von Ablaufverfolgungen, das Festlegen von Ablaufverfolgungsebenen, das Festlegen der Aktivitätsablaufverfolgung und -weitergabe zur Unterstützung der End-to-End-Ablaufverfolgungskorrelation sowie das Festlegen von Ablaufverfolgungslistenern für den Zugriff auf Ablaufverfolgungen.  
  
 Einstellungen für Empfehlungen zur Ablaufverfolgung in Produktions- oder Debugumgebung finden Sie unter [empfohlenen Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md).  
  
> [!IMPORTANT]
>  Unter Windows 8 müssen Sie die Anwendung mit erhöhten Rechten (als Administrator) ausführen, damit die Anwendung Ablaufverfolgungsprotokolle generieren kann.  
  
## <a name="enabling-tracing"></a>Aktivieren der Ablaufverfolgung  
 Windows Communication Foundation (WCF) gibt die folgenden Daten für die diagnoseablaufverfolgung aus:  
  
-   Ablaufverfolgungen für Verarbeitungsmeilensteine in allen Komponenten der Anwendungen, beispielsweise Operationsaufrufe, Codeausnahmen, Warnungen und andere wichtige Verarbeitungsereignisse.  
  
-   Windows-Fehlerereignisse bei Fehlern der Ablaufverfolgungsfunktion. Finden Sie unter [Ereignisprotokollierung](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md).  
  
 Ablaufverfolgung von WCF basiert auf der Basis von <xref:System.Diagnostics>. Definieren Sie in der Konfigurationsdatei oder im Code Ablaufverfolgungsquellen, wenn Sie die Ablaufverfolgung verwenden möchten. WCF definiert eine Ablaufverfolgungsquelle für jede WCF-Assembly. Die `System.ServiceModel` Ablaufverfolgungsquelle ist die allgemeinste WCF-Ablaufverfolgungsquelle und zeichnet Verarbeitung Meilensteine für die WCF-Kommunikationsstapel vom eintreten/Verlassen des Transports zum Eintreten/verlassen von Benutzercode. Die `System.ServiceModel.MessageLogging`-Ablaufverfolgungsquelle zeichnet alle Nachrichten auf, die das System durchlaufen.  
  
 Die Ablaufverfolgung ist standardmäßig nicht aktiviert. Um die Ablaufverfolgung zu aktivieren, müssen Sie einen Ablaufverfolgungslistener erstellen und eine andere Ablaufverfolgungsebene als "Off" für die ausgewählte Ablaufverfolgungsquelle in der Konfiguration festlegen; WCF generiert, andernfalls keine ablaufverfolgungen. Wenn Sie keinen Listener angeben, ist die Ablaufverfolgung automatisch deaktiviert. Wenn Sie einen Listener definieren, jedoch keine Ebene angeben, wird die Ebene standardmäßig auf "Off" festgelegt. Das bedeutet, dass keine Ablaufverfolgung ausgegeben wird.  
  
 Wenn Sie WCF-Erweiterbarkeitspunkte wie z. B. benutzerdefinierte Vorgangsaufrufer verwenden, sollten Sie eigene ablaufverfolgungen ausgeben. Das liegt bei der Implementierung eines Erweiterungspunkts WCF nicht mehr die standardablaufverfolgungen im Standardpfad ausgeben kann. Wenn Sie keine Unterstützung für eine manuelle Ablaufverfolgung durch Ausgabe von Ablaufverfolgungen implementieren, werden die erwarteten Ablaufverfolgungen möglicherweise nicht angezeigt.  
  
 Sie können die Ablaufverfolgung konfigurieren, indem Sie die Konfigurationsdatei der Anwendung bearbeiten, entweder Web.config für im Web gehostete Anwendungen oder Appname.exe.config für selbst gehostete Anwendungen. Das folgende Beispiel zeigt eine solche Bearbeitung. Weitere Informationen zu diesen Einstellungen finden Sie im Abschnitt "Konfigurieren von Ablaufverfolgungs-Listener zur Verwendung von Ablaufverfolgungen".  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
            <listeners>  
               <add name="traceListener"   
                   type="System.Diagnostics.XmlWriterTraceListener"   
                   initializeData= "c:\log\Traces.svclog" />  
            </listeners>  
         </source>  
      </sources>  
   </system.diagnostics>  
</configuration>  
```  
  
> [!NOTE]
>  Zum Bearbeiten der Konfigurationsdatei von einem WCF-Dienstprojekt in Visual Studio mit der rechten Maustaste Konfigurationsdatei der Anwendung – entweder Web.config für im Web gehostete Anwendungen oder Appname.exe.config für selbst gehostete Anwendungen in **Projektmappen-Explorer** . Wählen Sie dann die **WCF-Konfiguration bearbeiten** Kontextmenüelement. Dadurch wird die [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md), können Sie Konfigurationseinstellungen für WCF-Dienste, die mithilfe einer grafischen Benutzeroberfläche zu ändern.  
  
## <a name="configuring-trace-sources-to-emit-traces"></a>Konfigurieren von Ablaufverfolgungsquellen zum Ausgeben von Ablaufverfolgungen  
 WCF definiert eine Ablaufverfolgungsquelle für jede Assembly. Innerhalb einer Assembly generierte Ablaufverfolgungen werden von den Listenern verwendet, die für diese Quelle definiert sind. Folgende Ablaufverfolgungsquellen sind definiert:  
  
-   System.ServiceModel: Protokolliert alle Stufen der WCF-Verarbeitung, jedes Mal, wenn Konfiguration wird gelesen, eine Nachricht im Transport verarbeitet wird, wird zur Verarbeitung, der eine Nachricht im Benutzercode usw. verteilt.  
  
-   System.ServiceModel.MessageLogging: Protokolliert alle Nachrichten, die das System durchlaufen.  
  
-   System.IdentityModel.  
  
-   System.ServiceModel.Activation.  
  
-   System.IO.Log: Protokollierung für die .NET Framework-Schnittstelle im gemeinsamen Protokolldateisystem (Common Log File System, CLFS).  
  
-   System.Runtime.Serialization: Protokolliert das Lesen oder Schreiben von Objekten.  
  
-   CardSpace.  
  
 Das folgenden Konfigurationsbeispiel veranschaulicht, wie Sie jede Ablaufverfolgungsquelle so konfigurieren können, dass sie den gleichen (freigegebenen) Listener verwendet:  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="CardSpace">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IO.Log">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.Runtime.Serialization">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IdentityModel">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
        </sources>  
  
        <sharedListeners>  
            <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\log\Traces.svclog" />  
        </sharedListeners>  
    </system.diagnostics>  
</configuration>  
```  
  
 Sie können außerdem benutzerdefinierte Ablaufverfolgungsquellen hinzufügen, um Ablaufverfolgungsquellen im Benutzercode auszugeben (wie im folgenden Code dargestellt):  
  
```xml  
<system.diagnostics>  
   <sources>  
       <source name="UserTraceSource" switchValue="Warning, ActivityTracing" >  
          <listeners>  
              <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="C:\logs\UserTraces.svclog" />  
          </listeners>  
       </source>  
   </sources>  
   <trace autoflush="true" />   
</system.diagnostics>  
```  
  
 Weitere Informationen zum Erstellen von benutzerdefinierten Ablaufverfolgungsquellen finden Sie unter [erweitern Ablaufverfolgung](../../../../../docs/framework/wcf/samples/extending-tracing.md).  
  
## <a name="configuring-trace-listeners-to-consume-traces"></a>Konfigurieren von Ablaufverfolgungslistenern zur Verwendung von Ablaufverfolgungen  
 Während der Laufzeit-feeds WCF Ablaufverfolgungsdaten an die Listener, die die Daten zu verarbeiten. WCF bietet verschiedene vordefinierte Listener für <xref:System.Diagnostics>, unterscheiden sich in dem Format, das sie für die Ausgabe verwenden. Sie können auch benutzerdefinierte Listenertypen hinzufügen.  
  
 Mit `add` können Sie den Namen und den Typ des Ablaufverfolgungslisteners angeben, den Sie verwenden möchten. In unserer Beispielkonfiguration haben wir den Listener `traceListener` genannt und den standardmäßigen .NET Framework-Ablaufverfolgungslistener (`System.Diagnostics.XmlWriterTraceListener`) als zu verwendenden Typ angegeben. Sie können jeder Quelle beliebig viele Ablaufverfolgungslistener hinzufügen. Wenn der Ablaufverfolgungslistener die Ablaufverfolgung an eine Datei ausgibt, müssen Sie den Speicherort der Ausgabedatei angeben und sie in der Konfigurationsdatei benennen. Legen Sie dazu `initializeData` auf den Namen der Datei für diesen Listener fest. Wenn Sie keinen Dateinamen angeben, wird basierend auf dem verwendeten Listenertyp ein beliebiger Dateiname generiert. Wenn <xref:System.Diagnostics.XmlWriterTraceListener> verwendet wird, wird ein Dateiname ohne Erweiterung generiert. Beim Implementieren eines benutzerdefinierten Listeners können Sie dieses Attribut auch verwenden, um andere Initialisierungsdaten als den Dateinamen zu erhalten. Sie können für dieses Attribut z. B. einen Datenbankbezeichner angeben.  
  
 Sie können einen benutzerdefinierten Ablaufverfolgungslistener konfigurieren, um Ablaufverfolgungen zu übertragen, z. B. an eine Remotedatenbank. Stellen Sie beim Bereitstellen von Anwendungen eine ordnungsgemäße Zugriffsteuerung für die Protokolle auf dem Remotecomputer sicher.  
  
 Sie können einen Ablaufverfolgungslistener auch programmgesteuert konfigurieren. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungslistenern](https://go.microsoft.com/fwlink/?LinkId=94648) und [erstellen einen benutzerdefinierten TraceListener](https://go.microsoft.com/fwlink/?LinkId=96239).  
  
> [!CAUTION]
>  Da `System.Diagnostics.XmlWriterTraceListener` nicht threadsicher ist, werden Ressourcen durch die Ablaufverfolgungsquelle bei der Ausgabe von Ablaufverfolgungen möglicherweise exklusiv gesperrt. Wenn viele Threads Ablaufverfolgungen an eine Ablaufverfolgungsquelle ausgeben, die für die Verwendung dieses Listeners konfiguriert ist, treten möglicherweise Ressourcenkonflikte auf. Das kann die Leistung erheblich beeinträchtigen. Implementieren Sie einen threadsicheren benutzerdefinierten Listener, um dieses Problem zu beheben.  
  
## <a name="trace-level"></a>Ablaufverfolgungsebene  
 Die Ablaufverfolgungsebene wird von der `switchValue`-Einstellung der Ablaufverfolgungsquelle gesteuert. Die verfügbaren Ablaufverfolgungsebenen werden in der folgenden Tabelle beschrieben.  
  
|Ablaufverfolgungsebene|Art der verfolgten Ereignisse|Inhalt der verfolgten Ereignisse|Verfolgte Ereignisse|Zielgruppe|  
|-----------------|----------------------------------|-----------------------------------|--------------------|-----------------|  
|Aus|Nicht zutreffend|Nicht zutreffend|Keine Ablaufverfolgungen werden ausgegeben.|Nicht zutreffend|  
|Kritisch|"Negative" Ereignisse: Ereignisse, die eine unerwartete Verarbeitung oder eine fehlerbedingung angeben.||Nicht behandelte Ausnahmen (einschließlich der folgenden) werden protokolliert:<br /><br /> -OutOfMemoryException<br />-ThreadAbortException (die CLR ruft jeden threadabortexceptionhandler auf)<br />-StackOverflowException (kann nicht abgefangen werden)<br />-ConfigurationErrorsException<br />-SEHException-Ausnahme<br />-Startfehler der Anwendung<br />-Failfast Ereignisse<br />: Hängenbleiben des Systems<br />-Nicht verarbeitbare Nachrichten: nachrichtenablaufverfolgungen, die die Anwendung möglicherweise nicht ausgeführt.|Administratoren<br /><br /> Anwendungsentwickler|  
|Fehler|"Negative" Ereignisse: Ereignisse, die eine unerwartete Verarbeitung oder eine fehlerbedingung angeben.|Eine unerwartete Verarbeitung ist aufgetreten. Die Anwendung konnte die Aufgabe nicht wie erwartet ausführen. Die Anwendung wird jedoch weiter ordnungsgemäß ausgeführt.|Alle Ausnahmen werden protokolliert.|Administratoren<br /><br /> Anwendungsentwickler|  
|Warnung|"Negative" Ereignisse: Ereignisse, die eine unerwartete Verarbeitung oder eine fehlerbedingung angeben.|Ein mögliches Problem ist aufgetreten oder tritt möglicherweise auf, die Anwendung funktioniert jedoch noch ordnungsgemäß. Allerdings ist nicht sicher, dass sie weiterhin ordnungsgemäß ausgeführt wird.|– Die Anwendung empfängt mehr Anforderungen, als die drosselungseinstellungen zulassen.<br />– Die empfangende Warteschlange hat nahezu die maximal konfigurierte Kapazität erreicht.<br />-Timeout wurde überschritten.<br />-Anmeldeinformationen werden abgelehnt.|Administratoren<br /><br /> Anwendungsentwickler|  
|Information|"Positive" Ereignisse: Ereignisse, die erfolgreiche Meilensteine kennzeichnen.|Wichtige und erfolgreiche Meilensteine der Anwendungsausführung, unabhängig davon, ob die Anwendung ordnungsgemäß funktioniert.|In der Regel werden Meldungen generiert, die bei der Überwachung und Diagnose des Systemstatus, der Leistungsmessung oder Profilerstellung nützlich sind. Solche Informationen können zur Kapazitätsplanung und Leistungsverwaltung genutzt werden:<br /><br /> -Kanäle werden erstellt.<br />-Der Endpunktlistener werden erstellt.<br />-Nachricht eingibt oder verlässt den Transport.<br />-Sicherheitstoken wird abgerufen.<br />-Konfigurationseinstellung wird gelesen.|Administratoren<br /><br /> Anwendungsentwickler<br /><br /> Produktentwickler|  
|Ausführlich|"Positive" Ereignisse: Ereignisse, die erfolgreiche Meilensteine kennzeichnen.|Ereignisse auf niedriger Ebene werden für Benutzercode und Dienste ausgegeben.|Im Allgemeinen können Sie diese Ebene zum Debuggen oder zur Anwendungsoptimierung verwenden.<br /><br /> -Verstandener Nachrichtenheader.|Administratoren<br /><br /> Anwendungsentwickler<br /><br /> Produktentwickler|  
|ActivityTracing||Ablaufereignisse zwischen Verarbeitungsaktivitäten und Komponenten.|Diese Ebene ermöglicht es Administratoren und Entwicklern, Anwendungen in einer Anwendungsdomäne zu korrelieren:<br /><br /> -Ablaufverfolgungen für Aktivitätsgrenzen wie Start/Stopp.<br />-Ablaufverfolgungen für Übertragungen.|Alle|  
|Alle||Die Anwendung funktioniert möglicherweise ordnungsgemäß. Alle Ereignisse werden ausgegeben.|Alle vorherigen Ereignisse.|Alle|  
  
 Die Ebenen von Verbose bis Critical bauen aufeinander auf, d. h. jede Ablaufverfolgungsebene umfasst alle Ebenen darüber, außer der Off-Ebene. Beispielsweise empfängt en Listener, der die Warning-Ebene überwacht, Critical-, Error- and Warning-Ablaufverfolgungen. Die All-Ebene schließt Ereignisse von Verbose- bis Critical- und ActivityTracing-Ereignissen ein.  
  
> [!CAUTION]
>  Die Ebenen "Information", "Verbose" und "ActivityTracing" generieren eine Vielzahl von Ablaufverfolgungen, was sich negativ auf den Nachrichtendurchsatz auswirken kann, wenn alle verfügbaren Ressourcen des Computers belegt sind.  
  
## <a name="configuring-activity-tracing-and-propagation-for-correlation"></a>Konfigurieren der Aktivitätsablaufverfolgung und Weitergabe für die Korrelation  
 Mit dem für das `activityTracing`-Attribut angegebenen `switchValue`-Wert wird die Aktivitätsablaufverfolgung aktiviert, die Ablaufverfolgungen für Aktivitätsgrenzen und Übertragungen innerhalb von Endpunkten ausgibt.  
  
> [!NOTE]
>  Wenn Sie bestimmte Erweiterungsfunktionen in WCF verwenden, erhalten Sie möglicherweise eine <xref:System.NullReferenceException> Wenn die aktivitätsablaufverfolgung aktiviert ist. Um dieses Problem zu beheben, überprüfen Sie die Konfigurationsdatei der Anwendung und stellen sicher, dass das `switchValue`-Attribut für die Ablaufverfolgungsquelle nicht auf `activityTracing` festgelegt wurde.  
  
 Das `propagateActivity`-Attribut gibt an, ob die Aktivität an andere Endpunkte weitergegeben werden soll, die an dem Nachrichtenaustausch teilnehmen. Wenn Sie diesen Wert auf `true` festlegen, können Sie anhand von Ablaufverfolgungsdateien, die durch zwei Endpunkte generiert wurden, feststellen, wie eine Reihe von Ablaufverfolgungen an einem Endpunkt zu einer Reihe von Ablaufverfolgungen an einem anderen Endpunkt übergegangen sind.  
  
 Weitere Informationen zur aktivitätsablaufverfolgung und Weitergabe finden Sie unter [Weitergabe](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md).  
  
 Beide `propagateActivity` und `ActivityTracing` booleschen Werte gelten für die System.ServiceModel-Ablaufverfolgungsquelle. Die `ActivityTracing` -Wert gilt außerdem für alle Ablaufverfolgungsquellen, einschließlich WCF oder benutzerdefinierte Quellen.  
  
 Das `propagateActivity`-Attribut kann nicht bei benutzerdefinierten Ablaufverfolgungsquellen verwendet werden. Stellen Sie bei der Aktivitäts-ID-Weitergabe in Benutzercode sicher, dass Sie `ActivityTracing` von ServiceModel nicht festlegen, während das `propagateActivity`-Attribute von ServiceModel noch auf `true` festgelegt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungslistenern](https://go.microsoft.com/fwlink/?LinkId=94648)  
 [Erstellen eines benutzerdefinierten TraceListener](https://go.microsoft.com/fwlink/?LinkId=96239)
