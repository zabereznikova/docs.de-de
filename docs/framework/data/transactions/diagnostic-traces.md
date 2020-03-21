---
title: Ablaufverfolgungen zur Diagnose
ms.date: 03/30/2017
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
ms.openlocfilehash: 76712710bf42f498ba859c7b1cd18a261387078c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174419"
---
# <a name="diagnostic-traces"></a>Ablaufverfolgungen zur Diagnose
Ablaufverfolgung bedeutet das Veröffentlichen spezifischer Meldungen, die während der Anwendungsausführung generiert werden. Wenn Sie mit der Ablaufverfolgung arbeiten, müssen Sie einen Mechanismus zum Sammeln und Aufzeichnen der gesendeten Meldungen einrichten. Ablaufverfolgungsmeldungen werden von Listenern empfangen. Der Zweck eines Listeners ist das Sammeln, Speichern und Weiterleiten von Ablaufverfolgungsmeldungen. Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel, beispielsweise ein Protokoll, ein Fenster oder eine Textdatei.  
  
 Ein solcher Listener, der <xref:System.Diagnostics.DefaultTraceListener>, wird bei Aktivierung der Ablaufverfolgung automatisch erstellt und initialisiert. Wenn die Ausgabe der Ablaufverfolgung an zusätzliche Quellen geleitet werden soll, müssen Sie zusätzliche Ablaufverfolgungslistener erstellen und initialisieren. Erstellen Sie Listener, die auf Ihre individuellen Anforderungen abgestimmt sind. Beispiel: Sie brauchen ein Textprotokoll der gesamten Ablaufverfolgungsausgabe. In diesem Fall erstellen Sie einen Listener, der die gesamte Ausgabe in eine neue Textdatei schreibt, sobald er aktiviert wird. Oft ist die Anzeige der Ausgabe jedoch nur während der Anwendungsausführung erwünscht. In diesem Fall erstellen Sie einen Listener, der die gesamte Ausgabe an ein Konsolenfenster leitet. Der <xref:System.Diagnostics.EventLogTraceListener> kann die Ablaufverfolgungsausgabe an ein Ereignisprotokoll leiten, und der <xref:System.Diagnostics.TextWriterTraceListener> kann die Ablaufverfolgungsausgabe in einen Datenstrom schreiben.  
  
## <a name="enabling-tracing"></a>Aktivieren der Ablaufverfolgung  
 Um die Ablaufverfolgung während der Transaktionsverarbeitung zu aktivieren, müssen Sie die Konfigurationsdatei der Anwendung bearbeiten. Im Folgenden finden Sie ein Beispiel.  
  
```xml  
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
  
 <xref:System.Transactions>-Ablaufverfolgungen werden in die Quelle mit dem Namen "System.Transactions" geschrieben. Mit `add` können Sie den Namen und den Typ des Ablaufverfolgungslisteners angeben, den Sie verwenden möchten. In unserer Beispielkonfiguration haben wir den Listener "tx" genannt und den standardmäßigen Ablaufverfolgungslistener .NET Framework (<xref:System.Diagnostics.XmlWriterTraceListener>) als zu verwendenden Typ angegeben. Verwenden Sie `initializeData`, um den Namen der Protokolldatei für diesen Listener festzulegen. Außerdem können Sie einen einfachen Dateinamen durch einen vollqualifizierten Pfad ersetzen.  
  
 Jedem Typ von Ablaufverfolgungsmeldung wird eine Ebene zugewiesen, um seinen Wichtigkeitsgrad anzugeben. Befindet sich die Ablaufverfolgungsebene der Anwendungsdomäne auf der gleichen Ebene wie ein Ereignistyp, oder einer niedrigeren, wird diese Meldung erzeugt. Die Ablaufverfolgungsebene wird von der `switchValue`-Einstellung in der Konfigurationsdatei kontrolliert. Die Ebenen, die diagnostischen Ablaufverfolgungsmeldungen zugeordnet werden, sind in der folgenden Tabelle definiert.  
  
|Ablaufverfolgungsebene|Beschreibung|  
|-----------------|-----------------|  
|Kritisch|Schwerwiegende Fehler wie die nachfolgend aufgeführten sind aufgetreten:<br /><br /> - Ein Fehler, der zu einem sofortigen Verlust der Benutzerfunktionalität führen kann.<br />- Ein Ereignis, bei dem ein Administrator Maßnahmen ergreifen muss, um Funktionsverlust zu vermeiden.<br />- Code hängt.<br />- Diese Ablaufverfolgungsebene kann auch ausreichendkontextigen Kontext für die Interpretation anderer kritischer Spuren bieten. Dies kann helfen, die Sequenz von Vorgängen zu identifizieren, die zu einem schwerwiegenden Fehler führt.|  
|Fehler|Ein Fehler (beispielsweise ungültiges Konfigurations- oder Netzwerkverhalten) ist aufgetreten, der zu einer Beeinträchtigung der Benutzerfunktionalität führen kann.|  
|Warnung|Es besteht eine Bedingung, die zu einem Fehler oder einem schwerwiegenden Ausfall führen kann (z. B. Speicherbelegung oder Annäherung an einen Grenzwert). Die normale Verarbeitung von Benutzercodefehlern (z. B. Transaktionsabbruch, Timeouts oder Authentifizierungsfehler) kann ebenfalls eine Warnung auslösen.|  
|Information|Meldungen, die bei der Überwachung und Diagnose des Systemstatus, der Leistungsmessung oder Profilerstellung nützlich sind. Dazu gehören Transaktions- und Eintragungslebensdauer-Ereignisse wie beispielsweise eine Transaktion, die erstellt oder für die ein Commit ausgeführt wird, das Überschreiten einer wichtigen Begrenzung oder die Speicherbelegung bedeutender Ressourcen. Ein Entwickler kann dann solche Informationen zur Kapazitätsplanung und Leistungsverwaltung nutzen.|  
  
## <a name="trace-codes"></a>Ablaufverfolgungscodes  
 In der folgenden Tabelle sind die Ablaufverfolgungscodes aufgeführt, die von der <xref:System.Transactions>-Infrastruktur generiert werden. In der Tabelle sind der Ablaufverfolgungscodebezeichner, die <xref:System.Diagnostics.EventTypeFilter.EventType%2A> Enumerationsebene für die Ablaufverfolgung und die zusätzlichen Daten enthalten, die im **TraceRecord** für die Ablaufverfolgung enthalten sind. Darüber hinaus wird die entsprechende Ablaufverfolgungsebene der Ablaufverfolgung auch im **TraceRecord**gespeichert.  
  
|TraceCode|EventType|Zusätzliche Daten in TraceRecord|  
|---------------|---------------|-------------------------------|  
|TransactionCreated|Info|TransactionTraceId|  
|TransactionPromoted|Info|Local TransactionTraceId, Distributed TransactionTraceId|  
|EnlistmentCreated|Info|TransactionTraceId, EnlistmentTraceId, EnlistmentType (durable/volatile), EnlistmentOptions|  
|EnlistmentCallbackNegative|Warnung|TransactionTraceId, EnlistmentTraceId<br /><br /> Callback (forcerollback/aborted/indoubt)|  
|TransactionRollbackCalled|Warnung|TransactionTraceId|  
|TransactionAborted|Warnung|TransactionTraceId|  
|TransactionInDoubt|Warnung|TransactionTraceId|  
|TransactionScopeCreated|Info|TransactionScopeResult, das folgendes sein kann:<br /><br /> - Neue Transaktion.<br />- Transaktion bestanden.<br />- Abhängige Transaktion übergeben.<br />- Verwenden der aktuellen Transaktion.<br />- Keine Transaktion.<br /><br /> Neue aktuelle TransactionTraceId|  
|TransactionScopeDisposed|Info|TransactionTraceId der "erwarteten" aktuellen Transaktion des Bereichs.|  
|TransactionScopeIncomplete|Warnung|TransactionTraceId der "erwarteten" aktuellen Transaktion des Bereichs.|  
|TransactionScopeNestedIncorrectly|Warnung|TransactionTraceId der "erwarteten" aktuellen Transaktion des Bereichs.|  
|TransactionScopeCurrentTransactionChanged|Warnung|Alte aktuelle TransactionTraceId, sonstige TransactionTraceId|  
|TransactionScopeTimeout|Warnung|TransactionTraceId der "erwarteten" aktuellen Transaktion des Bereichs.|  
|DependentCloneCreated|Info|TransactionTraceId, Typ der erzeugten abhängigen Transaktion (RollbackIfNotComplete/BlockCommitUntilComplete)|  
|DependentCloneComplete|Info|TransactionTraceId|  
|RecoveryComplete|Info|Ressourcen-Manager-GUID (von Basis)|  
|Reenlist|Info|Ressourcen-Manager-GUID (von Basis)|  
|TransactionSerialized|Info|TransactionTraceId|  
|TransactionException|Fehler|Ausnahmemeldung|  
|InvalidOperationException|Fehler|Ausnahmemeldung|  
|InternalError|Kritisch|Ausnahmemeldung|  
|TransferEvent||Wenn eine Transaktion deserialisiert oder von einer <xref:System.Transactions>-Transaktion zu einer verteilten Transaktion erweitert wird, werden die aktuelle ActivityID aus ExecutionContext und die ID der verteilten Transaktion geschrieben.<br /><br /> Wenn DTC verwalteten Code zurückruft, wird die ID der verteilten Transaktion für die Dauer des Rückrufs als ActivityID in ExecutionContext festgelegt.|  
|ConfiguredDefaultTimeoutAdjusted|Warnung|Keine zusätzlichen Daten|  
|TransactionTimeout|Warnung|Die TransactionTraceId der Transaktion hat das Zeitlimit überschritten.|  
  
 Das XML-Schema für jedes der vorangehenden zusätzlichen Datenelemente hat das folgende Format.  
  
### <a name="transactiontraceidentifier"></a>TransactionTraceIdentifier  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### <a name="enlistmenttraceidentifier"></a>EnlistmentTraceIdentifier  
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
  
### <a name="resource-manager-identifier"></a>Ressourcen-Manager-Bezeichner  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## <a name="security-issues-for-tracing"></a>Sicherheitsprobleme bei der Ablaufverfolgung  
 Wenn Sie als Administrator die Ablaufverfolgung aktivieren, könnten vertrauliche Informationen in ein Ablaufverfolgungsprotokoll geschrieben werden, auf das standardmäßig öffentlich zugegriffen werden kann. Um mögliche Sicherheitsrisiken zu mindern, sollten Sie das Ablaufverfolgungsprotokoll an einem sicheren Ort speichern, der durch Zugriffsberechtigungen für Freigaben und Dateisysteme kontrolliert wird.
