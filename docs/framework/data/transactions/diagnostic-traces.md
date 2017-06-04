---
title: "Diagnoseablaufverfolgungen  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Diagnoseablaufverfolgungen 
Ablaufverfolgung bedeutet das Veröffentlichen spezifischer Meldungen, die während der Anwendungsausführung generiert werden.Wenn Sie mit der Ablaufverfolgung arbeiten, müssen Sie einen Mechanismus zum Sammeln und Aufzeichnen der gesendeten Meldungen einrichten.Ablaufverfolgungsmeldungen werden von Listenern empfangen.Der Zweck eines Listeners ist das Sammeln, Speichern und Weiterleiten von Ablaufverfolgungsmeldungen.Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel, beispielsweise ein Protokoll, ein Fenster oder eine Textdatei.  
  
 Ein solcher Listener, der <xref:System.Diagnostics.DefaultTraceListener>, wird bei Aktivierung der Ablaufverfolgung automatisch erstellt und initialisiert.Wenn die Ausgabe der Ablaufverfolgung an zusätzliche Quellen geleitet werden soll, müssen Sie zusätzliche Ablaufverfolgungslistener erstellen und initialisieren.Erstellen Sie Listener, die auf Ihre individuellen Anforderungen abgestimmt sind.Beispiel: Sie brauchen ein Textprotokoll der gesamten Ablaufverfolgungsausgabe.In diesem Fall erstellen Sie einen Listener, der die gesamte Ausgabe in eine neue Textdatei schreibt, sobald er aktiviert wird.Oft ist die Anzeige der Ausgabe jedoch nur während der Anwendungsausführung erwünscht.In diesem Fall erstellen Sie einen Listener, der die gesamte Ausgabe an ein Konsolenfenster leitet.Der <xref:System.Diagnostics.EventLogTraceListener> kann die Ablaufverfolgungsausgabe an ein Ereignisprotokoll leiten, und der <xref:System.Diagnostics.TextWriterTraceListener> kann die Ablaufverfolgungsausgabe in einen Datenstrom schreiben.  
  
## Aktivieren der Ablaufverfolgung  
 Um die Ablaufverfolgung während der Transaktionsverarbeitung zu aktivieren, müssen Sie die Konfigurationsdatei der Anwendung bearbeiten.Beachten Sie folgendes Beispiel:  
  
```  
<configuration>  
<system.diagnostics>  
     <sources>  
          <source name="System.Transactions" switchValue="Warning">  
               <listeners>  
                    <add name="tx"   
                     type="System.Diagnostics.XmlWriterTraceListener"   
                     initializeData= "tx.log" />  
               </listeners>  
          </source>  
     </sources>  
</system.diagnostics>  
</configuration>  
  
```  
  
 <xref:System.Transactions>\-Ablaufverfolgungen werden in die Quelle mit dem Namen "System.Transactions" geschrieben.Mit `add` können Sie den Namen und den Typ des Ablaufverfolgungslisteners angeben, den Sie verwenden möchten.In unserer Beispielkonfiguration haben wir den Listener "tx" genannt und den standardmäßigen Ablaufverfolgungslistener .NET Framework \(<xref:System.Diagnostics.XmlWriterTraceListener>\) als zu verwendenden Typ angegeben.Verwenden Sie `initializeData`, um den Namen der Protokolldatei für diesen Listener festzulegen.Außerdem können Sie einen einfachen Dateinamen durch einen vollqualifizierten Pfad ersetzen.  
  
 Jedem Typ von Ablaufverfolgungsmeldung wird eine Ebene zugewiesen, um seinen Wichtigkeitsgrad anzugeben.Befindet sich die Ablaufverfolgungsebene der Anwendungsdomäne auf der gleichen Ebene wie ein Ereignistyp, oder einer niedrigeren, wird diese Meldung erzeugt.Die Ablaufverfolgungsebene wird von der `switchValue`\-Einstellung in der Konfigurationsdatei kontrolliert.Die Ebenen, die diagnostischen Ablaufverfolgungsmeldungen zugeordnet werden, sind in der folgenden Tabelle definiert.  
  
|Ablaufverfolgungsebene|Beschreibung|  
|----------------------------|------------------|  
|Wichtig|Schwerwiegende Fehler wie die nachfolgend aufgeführten sind aufgetreten:<br /><br /> -   Ein Fehler, der die Benutzerfunktionalität unmittelbar beeinträchtigen kann<br />-   Ein Ereignis, das den Eingriff eines Administrators erfordert, um die Beeinträchtigung der Funktionalität zu vermeiden<br />-   Codefehler<br />-   Diese Ablaufverfolgungsebene kann zudem genügenden Kontext zum Interpretieren anderer wichtiger Ablaufverfolgungen bereitstellen.Dies kann helfen, die Sequenz von Vorgängen zu identifizieren, die zu einem schwerwiegenden Fehler führt.|  
|Fehler|Ein Fehler \(beispielsweise ungültiges Konfigurations\- oder Netzwerkverhalten\) ist aufgetreten, der zu einer Beeinträchtigung der Benutzerfunktionalität führen kann.|  
|Warnung|Es besteht eine Bedingung, die zu einem Fehler oder einem schwerwiegenden Ausfall führen kann \(z. B. Speicherbelegung oder Annäherung an einen Grenzwert\).Die normale Verarbeitung von Benutzercodefehlern \(z. B. Transaktionsabbruch, Timeouts oder Authentifizierungsfehler\) kann ebenfalls eine Warnung auslösen.|  
|Information|Meldungen, die bei der Überwachung und Diagnose des Systemstatus, der Leistungsmessung oder Profilerstellung nützlich sind.Dazu gehören Transaktions\- und Eintragungslebensdauer\-Ereignisse wie beispielsweise eine Transaktion, die erstellt oder für die ein Commit ausgeführt wird, das Überschreiten einer wichtigen Begrenzung oder die Speicherbelegung bedeutender Ressourcen.Ein Entwickler kann dann solche Informationen zur Kapazitätsplanung und Leistungsverwaltung nutzen.|  
  
## Ablaufverfolgungscodes  
 In der folgenden Tabelle sind die Ablaufverfolgungscodes aufgeführt, die von der <xref:System.Transactions>\-Infrastruktur generiert werden.Außerdem werden der Codebezeichner, die <xref:System.Diagnostics.EventTypeFilter.EventType%2A>\-Enumerationsebene für die Ablaufverfolgung sowie zusätzliche Daten aus dem **TraceRecord** für die Ablaufverfolgung in der Tabelle angegeben.Zudem wird auch die entsprechende Ablaufverfolgungsebene der Ablaufverfolgung im  **TraceRecord** gespeichert.  
  
|TraceCode|EventType|Zusätzliche Daten in TraceRecord|  
|---------------|---------------|--------------------------------------|  
|TransactionCreated|Info|TransactionTraceId|  
|TransactionPromoted|Info|Local TransactionTraceId, Distributed TransactionTraceId|  
|EnlistmentCreated|Info|TransactionTraceId, EnlistmentTraceId, EnlistmentType \(durable\/volatile\), EnlistmentOptions|  
|EnlistmentCallbackNegative|Warnung|TransactionTraceId, EnlistmentTraceId<br /><br /> Callback \(forcerollback\/aborted\/indoubt\)|  
|TransactionRollbackCalled|Warnung|TransactionTraceId|  
|TransactionAborted|Warnung|TransactionTraceId|  
|TransactionInDoubt|Warnung|TransactionTraceId|  
|TransactionScopeCreated|Info|TransactionScopeResult, das folgendes sein kann:<br /><br /> -   Neue Transaktion<br />-   Transaktion ausgeführt<br />-   Abhängige Transaktion ausgeführt<br />-   Mit aktueller Transaktion<br />-   Keine Transaktion<br /><br /> Neue aktuelle TransactionTraceId|  
|TransactionScopeDisposed|Info|TransactionTraceId der vom Bereich "erwarteten" aktuellen Transaktion|  
|TransactionScopeIncomplete|Warnung|TransactionTraceId der vom Bereich "erwarteten" aktuellen Transaktion|  
|TransactionScopeNestedIncorrectly|Warnung|TransactionTraceId der vom Bereich "erwarteten" aktuellen Transaktion|  
|TransactionScopeCurrentTransactionChanged|Warnung|Alte aktuelle TransactionTraceId, sonstige TransactionTraceId|  
|TransactionScopeTimeout|Warnung|TransactionTraceId der vom Bereich "erwarteten" aktuellen Transaktion|  
|DependentCloneCreated|Info|TransactionTraceId, Typ der erzeugten abhängigen Transaktion \(RollbackIfNotComplete\/BlockCommitUntilComplete\)|  
|DependentCloneComplete|Info|TransactionTraceId|  
|RecoveryComplete|Info|Ressourcen\-Manager\-GUID \(von Basis\)|  
|Reenlist|Info|Ressourcen\-Manager\-GUID \(von Basis\)|  
|TransactionSerialized|Info|TransactionTraceId|  
|TransactionException|Fehler|Ausnahmemeldung|  
|InvalidOperationException|Fehler|Ausnahmemeldung|  
|InternalError|Wichtig|Ausnahmemeldung|  
|TransferEvent||Wenn eine Transaktion deserialisiert oder von einer <xref:System.Transactions>\-Transaktion zu einer verteilten Transaktion erweitert wird, werden die aktuelle ActivityID aus ExecutionContext und die ID der verteilten Transaktion geschrieben.<br /><br /> Wenn DTC verwalteten Code zurückruft, wird die ID der verteilten Transaktion für die Dauer des Rückrufs als ActivityID in ExecutionContext festgelegt.|  
|ConfiguredDefaultTimeoutAdjusted|Warnung|Keine zusätzlichen Daten|  
|TransactionTimeout|Warnung|Die TransactionTraceId der Transaktion hat das Zeitlimit überschritten.|  
  
 Das XML\-Schema für jedes der vorangehenden zusätzlichen Datenelemente hat das folgende Format.  
  
### TransactionTraceIdentifier  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### EnlistmentTraceIdentifier  
 `<EnlistmentTraceIdentifier>`  
  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `<CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<EnlistmentIdentifier>`  
  
 `the enlistment id number`  
  
 `</EnlistmentIdentifier>`  
  
 `</EnlistmentTraceIdentifier>`  
  
### Ressourcen\-Manager\-Bezeichner  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## Sicherheitsprobleme bei der Ablaufverfolgung  
 Wenn Sie als Administrator die Ablaufverfolgung aktivieren, könnten vertrauliche Informationen in ein Ablaufverfolgungsprotokoll geschrieben werden, auf das standardmäßig öffentlich zugegriffen werden kann.Um mögliche Sicherheitsrisiken zu mindern, sollten Sie das Ablaufverfolgungsprotokoll an einem sicheren Ort speichern, der durch Zugriffsberechtigungen für Freigaben und Dateisysteme kontrolliert wird.