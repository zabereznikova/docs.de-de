---
title: Konfigurieren der Ablaufverfolgung
description: Erfahren Sie, wie Sie die Ablauf Verfolgung aktivieren, Ablauf Verfolgungs Quellen konfigurieren, Aktivitäts Ablauf Verfolgung und-Weitergabe festlegen und Ablaufverfolgungslistener für den Zugriff auf
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [WCF]
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
ms.openlocfilehash: 7b0cc58975ee145e5234adf51e24109898853e1c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558900"
---
# <a name="configuring-tracing"></a>Konfigurieren der Ablaufverfolgung
In diesem Thema wird Folgendes beschrieben: das Aktivieren der Ablaufverfolgung, das Konfigurieren von Ablaufverfolgungsquellen zum Ausgeben von Ablaufverfolgungen, das Festlegen von Ablaufverfolgungsebenen, das Festlegen der Aktivitätsablaufverfolgung und -weitergabe zur Unterstützung der End-to-End-Ablaufverfolgungskorrelation sowie das Festlegen von Ablaufverfolgungslistenern für den Zugriff auf Ablaufverfolgungen.  
  
 Empfehlungen zu den Ablauf Verfolgungs Einstellungen in der Produktions-oder Debugumgebung finden Sie unter [Empfohlene Einstellungen für Ablauf Verfolgung und Nachrichten Protokollierung](recommended-settings-for-tracing-and-message-logging.md).  
  
> [!IMPORTANT]
> Unter Windows 8 müssen Sie die Anwendung mit erhöhten Rechten (als Administrator) ausführen, damit die Anwendung Ablaufverfolgungsprotokolle generieren kann.  
  
## <a name="enabling-tracing"></a>Aktivieren der Ablaufverfolgung  
 Windows Communication Foundation (WCF) gibt die folgenden Daten für die Diagnose Ablauf Verfolgung aus:  
  
- Ablauf Verfolgungen für Prozess Meilensteine in allen Komponenten der Anwendungen, wie z. b. Vorgangs Aufrufe, Code Ausnahmen, Warnungen und andere wichtige Verarbeitungs Ereignisse.  
  
- Windows-Fehlerereignisse bei Fehlern der Ablaufverfolgungsfunktion. Siehe [Ereignisprotokollierung](../event-logging/index.md).  
  
 Die WCF-Ablauf Verfolgung baut auf auf <xref:System.Diagnostics> . Definieren Sie in der Konfigurationsdatei oder im Code Ablaufverfolgungsquellen, wenn Sie die Ablaufverfolgung verwenden möchten. WCF definiert eine Ablauf Verfolgungs Quelle für jede WCF-Assembly. Die Ablauf `System.ServiceModel` Verfolgungs Quelle ist die allgemeinste WCF-Ablauf Verfolgungs Quelle und zeichnet die Verarbeitung von Meilensteinen im WCF-Kommunikations Stapel auf, von der Eingabe/der Übertragung des Transports zum eingeben/belassen von Benutzercode. Die `System.ServiceModel.MessageLogging`-Ablaufverfolgungsquelle zeichnet alle Nachrichten auf, die das System durchlaufen.  
  
 Die Ablaufverfolgung ist standardmäßig nicht aktiviert. Um die Ablauf Verfolgung zu aktivieren, müssen Sie einen Ablaufverfolgungslistener erstellen und für die ausgewählte Ablauf Verfolgungs Quelle in der Konfiguration eine andere Ablauf Verfolgungs Ebene festlegen. Andernfalls generiert WCF keine Ablauf Verfolgungen. Wenn Sie keinen Listener angeben, ist die Ablaufverfolgung automatisch deaktiviert. Wenn Sie einen Listener definieren, jedoch keine Ebene angeben, wird die Ebene standardmäßig auf "Off" festgelegt. Das bedeutet, dass keine Ablaufverfolgung ausgegeben wird.  
  
 Wenn Sie WCF-Erweiterbarkeits Punkte (z. b. benutzerdefinierte Vorgangs Aufrufe) verwenden, sollten Sie Ihre eigenen Ablauf Verfolgungen ausgeben. Dies liegt daran, dass WCF bei der Implementierung eines Erweiterungs Punkts die Standard Ablauf Verfolgungen nicht mehr im Standardpfad ausgeben kann. Wenn Sie keine Unterstützung für eine manuelle Ablaufverfolgung durch Ausgabe von Ablaufverfolgungen implementieren, werden die erwarteten Ablaufverfolgungen möglicherweise nicht angezeigt.  
  
 Sie können die Ablauf Verfolgung konfigurieren, indem Sie die Konfigurationsdatei der Anwendung bearbeiten – Web.config entweder für im Internet gehostete Anwendungen oder für selbst gehostete Anwendungen Appname.exe.config. Das folgende Beispiel zeigt eine solche Bearbeitung. Weitere Informationen zu diesen Einstellungen finden Sie im Abschnitt "Konfigurieren von Ablaufverfolgungslistenern zur Nutzung von Ablauf Verfolgungen".  
  
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
> Um die Konfigurationsdatei eines WCF-Dienst Projekts in Visual Studio zu bearbeiten, klicken Sie mit der rechten Maustaste auf die Konfigurationsdatei der Anwendung – Web.config entweder für im Internet gehostete Anwendungen oder Appname.exe.config für eine selbstgeh ostete Anwendung in **Projektmappen-Explorer**. Wählen Sie dann das Kontextmenü Element **WCF-Konfiguration bearbeiten** aus. Dadurch wird das [Configuration Editor-Tool (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md)gestartet, mit dem Sie Konfigurationseinstellungen für WCF-Dienste mithilfe einer grafischen Benutzeroberfläche ändern können.  
  
## <a name="configuring-trace-sources-to-emit-traces"></a>Konfigurieren von Ablaufverfolgungsquellen zum Ausgeben von Ablaufverfolgungen  
 WCF definiert eine Ablauf Verfolgungs Quelle für jede Assembly. Innerhalb einer Assembly generierte Ablaufverfolgungen werden von den Listenern verwendet, die für diese Quelle definiert sind. Folgende Ablaufverfolgungsquellen sind definiert:  
  
- System. Service Model: protokolliert alle Phasen der WCF-Verarbeitung, wenn die Konfiguration gelesen wird, eine Nachricht bei Transport, Sicherheits Verarbeitung, eine Nachricht im Benutzercode usw. verarbeitet wird.  
  
- System.ServiceModel.MessageLogging: Protokolliert alle Nachrichten, die das System durchlaufen.  
  
- System.IdentityModel.  
  
- System.ServiceModel.Activation.  
  
- System.IO.Log: Protokollierung für die .NET Framework-Schnittstelle im gemeinsamen Protokolldateisystem (Common Log File System, CLFS).  
  
- System.Runtime.Serialization: Protokolliert das Lesen oder Schreiben von Objekten.  
  
- CardSpace.  
  
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
  
 Weitere Informationen zum Erstellen benutzerdefinierter Ablauf Verfolgungs Quellen finden Sie unter [erweitern](../../samples/extending-tracing.md)der Ablauf Verfolgung.  
  
## <a name="configuring-trace-listeners-to-consume-traces"></a>Konfigurieren von Ablaufverfolgungslistenern zur Verwendung von Ablaufverfolgungen  
 Zur Laufzeit Feeds WCF Ablauf Verfolgungs Daten an die Listener, die die Daten verarbeiten. WCF stellt mehrere vordefinierte Listener für bereit <xref:System.Diagnostics> . Diese unterscheiden sich im Format, das für die Ausgabe verwendet wird. Sie können auch benutzerdefinierte Listenertypen hinzufügen.  
  
 Mit `add` können Sie den Namen und den Typ des Ablaufverfolgungslisteners angeben, den Sie verwenden möchten. In unserer Beispielkonfiguration haben wir den Listener `traceListener` genannt und den standardmäßigen .NET Framework-Ablaufverfolgungslistener (`System.Diagnostics.XmlWriterTraceListener`) als zu verwendenden Typ angegeben. Sie können jeder Quelle beliebig viele Ablaufverfolgungslistener hinzufügen. Wenn der Ablaufverfolgungslistener die Ablaufverfolgung an eine Datei ausgibt, müssen Sie den Speicherort der Ausgabedatei angeben und sie in der Konfigurationsdatei benennen. Legen Sie dazu `initializeData` auf den Namen der Datei für diesen Listener fest. Wenn Sie keinen Dateinamen angeben, wird basierend auf dem verwendeten Listenertyp ein beliebiger Dateiname generiert. Wenn <xref:System.Diagnostics.XmlWriterTraceListener> verwendet wird, wird ein Dateiname ohne Erweiterung generiert. Beim Implementieren eines benutzerdefinierten Listeners können Sie dieses Attribut auch verwenden, um andere Initialisierungsdaten als den Dateinamen zu erhalten. Sie können für dieses Attribut z. B. einen Datenbankbezeichner angeben.  
  
 Sie können einen benutzerdefinierten Ablaufverfolgungslistener konfigurieren, um Ablaufverfolgungen zu übertragen, z. B. an eine Remotedatenbank. Stellen Sie beim Bereitstellen von Anwendungen eine ordnungsgemäße Zugriffsteuerung für die Protokolle auf dem Remotecomputer sicher.  
  
 Sie können einen Ablaufverfolgungslistener auch programmgesteuert konfigurieren. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen und initialisieren](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) von Ablaufverfolgungslistenern und [Erstellen eines benutzerdefinierten TraceListener](/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics).  
  
> [!CAUTION]
> Da `System.Diagnostics.XmlWriterTraceListener` nicht threadsicher ist, werden Ressourcen durch die Ablaufverfolgungsquelle bei der Ausgabe von Ablaufverfolgungen möglicherweise exklusiv gesperrt. Wenn viele Threads Ablaufverfolgungen an eine Ablaufverfolgungsquelle ausgeben, die für die Verwendung dieses Listeners konfiguriert ist, treten möglicherweise Ressourcenkonflikte auf. Das kann die Leistung erheblich beeinträchtigen. Implementieren Sie einen threadsicheren benutzerdefinierten Listener, um dieses Problem zu beheben.  
  
## <a name="trace-level"></a>Ablaufverfolgungsebene  
 Die Ablaufverfolgungsebene wird von der `switchValue`-Einstellung der Ablaufverfolgungsquelle gesteuert. Die verfügbaren Ablaufverfolgungsebenen werden in der folgenden Tabelle beschrieben.  
  
|Ablaufverfolgungsebene|Art der verfolgten Ereignisse|Inhalt der verfolgten Ereignisse|Verfolgte Ereignisse|Zielgruppe|  
|-----------------|----------------------------------|-----------------------------------|--------------------|-----------------|  
|Aus|Nicht zutreffend|Nicht zutreffend|Keine Ablaufverfolgungen werden ausgegeben.|–|  
|Kritisch|"Negative" Ereignisse: Ereignisse, die auf eine unerwartete Verarbeitung oder einen Fehlerzustand hinweisen.||Nicht behandelte Ausnahmen (einschließlich der folgenden) werden protokolliert:<br /><br /> -Ouyf memoryexception<br />-ThreadAbortException (die CLR ruft jeden ThreadAbortExceptionHandler auf)<br />-StackOverflowException (kann nicht abgefangen werden)<br />-ConfigurationErrorsException<br />-SEH Exception<br />-Fehler beim Starten der Anwendung<br />-FailFast-Ereignisse<br />-System hängt nicht aus<br />-Nicht verarbeitbare Nachrichten: Nachrichten Ablauf Verfolgungen, die zu einem Fehler der Anwendung führen|Administratoren<br /><br /> Anwendungsentwickler|  
|Fehler|"Negative" Ereignisse: Ereignisse, die auf eine unerwartete Verarbeitung oder einen Fehlerzustand hinweisen.|Eine unerwartete Verarbeitung ist aufgetreten. Die Anwendung konnte die Aufgabe nicht wie erwartet ausführen. Die Anwendung wird jedoch weiter ordnungsgemäß ausgeführt.|Alle Ausnahmen werden protokolliert.|Administratoren<br /><br /> Anwendungsentwickler|  
|Warnung|"Negative" Ereignisse: Ereignisse, die auf eine unerwartete Verarbeitung oder einen Fehlerzustand hinweisen.|Ein mögliches Problem ist aufgetreten oder tritt möglicherweise auf, die Anwendung funktioniert jedoch noch ordnungsgemäß. Allerdings ist nicht sicher, dass sie weiterhin ordnungsgemäß ausgeführt wird.|-Die Anwendung empfängt mehr Anforderungen, als ihre einschrändungs Einstellungen zulassen.<br />-Die empfangende Warteschlange liegt fast der konfigurierten Kapazität.<br />-Timeout wurde überschritten.<br />-Anmelde Informationen werden abgelehnt.|Administratoren<br /><br /> Anwendungsentwickler|  
|Information|"Positive" Ereignisse: Ereignisse, die erfolgreiche Meilensteine markieren|Wichtige und erfolgreiche Meilensteine der Anwendungsausführung, unabhängig davon, ob die Anwendung ordnungsgemäß funktioniert.|In der Regel werden Meldungen generiert, die bei der Überwachung und Diagnose des Systemstatus, der Leistungsmessung oder Profilerstellung nützlich sind. Solche Informationen können zur Kapazitätsplanung und Leistungsverwaltung genutzt werden:<br /><br /> -Kanäle werden erstellt.<br />-Endpunkt Listener werden erstellt.<br />-Message gelangt/verlässt den Transport.<br />-Das Sicherheits Token wird abgerufen.<br />-Die Konfigurationseinstellung wird gelesen.|Administratoren<br /><br /> Anwendungsentwickler<br /><br /> Produktentwickler|  
|Ausführlich|"Positive" Ereignisse: Ereignisse, die erfolgreiche Meilensteine markieren.|Ereignisse auf niedriger Ebene für Benutzercode und Wartung werden ausgegeben.|Im Allgemeinen können Sie diese Ebene zum Debuggen oder zur Anwendungsoptimierung verwenden.<br /><br /> -Der Nachrichten Header wurde verstanden.|Administratoren<br /><br /> Anwendungsentwickler<br /><br /> Produktentwickler|  
|ActivityTracing||Ablaufereignisse zwischen Verarbeitungsaktivitäten und Komponenten.|Diese Ebene ermöglicht es Administratoren und Entwicklern, Anwendungen in einer Anwendungsdomäne zu korrelieren:<br /><br /> -Ablauf Verfolgungen für Aktivitäts Grenzen, z. b. Start/Ende.<br />-Ablauf Verfolgungen für Übertragungen.|Alle|  
|Alle||Die Anwendung funktioniert möglicherweise ordnungsgemäß. Alle Ereignisse werden ausgegeben.|Alle vorherigen Ereignisse.|Alle|  
  
 Die Ebenen von Verbose bis Critical bauen aufeinander auf, d. h. jede Ablaufverfolgungsebene umfasst alle Ebenen darüber, außer der Off-Ebene. Beispielsweise empfängt en Listener, der die Warning-Ebene überwacht, Critical-, Error- and Warning-Ablaufverfolgungen. Die All-Ebene schließt Ereignisse von Verbose- bis Critical- und ActivityTracing-Ereignissen ein.  
  
> [!CAUTION]
> Die Ebenen "Information", "Verbose" und "ActivityTracing" generieren eine Vielzahl von Ablaufverfolgungen, was sich negativ auf den Nachrichtendurchsatz auswirken kann, wenn alle verfügbaren Ressourcen des Computers belegt sind.  
  
## <a name="configuring-activity-tracing-and-propagation-for-correlation"></a>Konfigurieren der Aktivitätsablaufverfolgung und Weitergabe für die Korrelation  
 Mit dem für das `activityTracing`-Attribut angegebenen `switchValue`-Wert wird die Aktivitätsablaufverfolgung aktiviert, die Ablaufverfolgungen für Aktivitätsgrenzen und Übertragungen innerhalb von Endpunkten ausgibt.  
  
> [!NOTE]
> Wenn Sie bestimmte Erweiterbarkeits Funktionen in WCF verwenden, erhalten Sie möglicherweise eine, <xref:System.NullReferenceException> Wenn die Aktivitäts Ablauf Verfolgung aktiviert ist. Um dieses Problem zu beheben, überprüfen Sie die Konfigurationsdatei der Anwendung und stellen sicher, dass das `switchValue`-Attribut für die Ablaufverfolgungsquelle nicht auf `activityTracing` festgelegt wurde.  
  
 Das `propagateActivity`-Attribut gibt an, ob die Aktivität an andere Endpunkte weitergegeben werden soll, die an dem Nachrichtenaustausch teilnehmen. Wenn Sie diesen Wert auf `true` festlegen, können Sie anhand von Ablaufverfolgungsdateien, die durch zwei Endpunkte generiert wurden, feststellen, wie eine Reihe von Ablaufverfolgungen an einem Endpunkt zu einer Reihe von Ablaufverfolgungen an einem anderen Endpunkt übergegangen sind.  
  
 Weitere Informationen zur Aktivitäts Ablauf Verfolgung und-Weitergabe finden Sie unter [Propagierung](propagation.md).  
  
 Sowohl `propagateActivity` als auch `ActivityTracing` boolesche Werte gelten für die System. Service Model-TraceSource. Der `ActivityTracing` Wert gilt auch für alle Ablauf Verfolgungs Quellen, einschließlich WCF-oder benutzerdefinierter Dateien.  
  
 Das `propagateActivity`-Attribut kann nicht bei benutzerdefinierten Ablaufverfolgungsquellen verwendet werden. Stellen Sie bei der Aktivitäts-ID-Weitergabe in Benutzercode sicher, dass Sie `ActivityTracing` von ServiceModel nicht festlegen, während das `propagateActivity`-Attribute von ServiceModel noch auf `true` festgelegt ist.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](index.md)
- [Verwaltung und Diagnose](../index.md)
- [Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungslistenern](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md)
- [Erstellen eines benutzerdefinierten TraceListener](/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics)
