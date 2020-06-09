---
title: Erkennen einer Transaktionsanwendung
ms.date: 03/30/2017
ms.assetid: 4a993492-1088-4d10-871b-0c09916af05f
ms.openlocfilehash: fb3a83083e876cf697621ba70dcf7dd67636f83a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599216"
---
# <a name="diagnosing-transactional-applications"></a>Erkennen einer Transaktionsanwendung
In diesem Thema wird beschrieben, wie Sie die Verwaltung und Diagnose von Windows Communication Foundation (WCF) verwenden, um Probleme mit einer Transaktions Anwendung zu beheben.  
  
## <a name="performance-counters"></a>Leistungsindikatoren  
 WCF stellt einen Standardsatz von Leistungsindikatoren bereit, mit denen Sie die Leistung Ihrer Transaktions Anwendung messen können. Weitere Informationen finden Sie unter [Performance Counters](../diagnostics/performance-counters/index.md).  
  
 Leistungsindikatoren werden in drei verschiedene Stufen unterteilt: Dienst, Endpunkt und Vorgang, gemäß folgender Tabellen.  
  
### <a name="service-performance-counters"></a>Dienst-Leistungsindikatoren  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|Übergegangene Transaktionen|Die Anzahl der Transaktionen, die in Vorgänge in diesem Dienst übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn die Nachricht, die an den Dienst gesendet wird, eine Transaktion enthält.|  
|Übergegangene Transaktionen pro Sekunde|Die Anzahl der Transaktionen, die innerhalb von einer Sekunde in Vorgänge in diesem Dienst übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn die Nachricht, die an den Dienst gesendet wird, eine Transaktion enthält.|  
|Übermittelte abgewickelte Vorgänge|Die Anzahl der durchgeführten abgewickelten Vorgänge, deren Transaktion mit dem Ergebnis „übermittelt“ abgeschlossen wurde. Arbeiten, die im Rahmen dieser Vorgänge ausgeführt werden, wurden komplett übermittelt. Ressourcen werden in Übereinstimmung mit der im Vorgang erledigten Arbeit aktualisiert.|  
|Transacted Operations Committed Per Second|Die Anzahl der pro Sekunde durchgeführten abgewickelten Vorgänge, deren Transaktion mit dem Ergebnis „übermittelt“ abgeschlossen wurde. Arbeiten, die im Rahmen dieser Vorgänge ausgeführt werden, wurden komplett übermittelt. Ressourcen werden in Übereinstimmung mit der im Vorgang erledigten Arbeit aktualisiert.|  
|Abgebrochene abgewickelte Vorgänge|Die Anzahl der durchgeführten abgewickelten Vorgänge, deren Transaktion mit dem Ergebnis „abgebrochen“ abgeschlossen wurde. Arbeiten, die im Rahmen dieser Vorgänge ausgeführt werden, werden komplett zurückgesetzt. Ressourcen werden in ihren vorherigen Zustand zurückgesetzt.|  
|Abgebrochene abgewickelte Vorgänge pro Sekunde|Die Anzahl der pro Sekunde durchgeführten abgewickelten Vorgänge, deren Transaktion mit dem Ergebnis „abgebrochen“ abgeschlossen wurde. Arbeiten, die im Rahmen dieser Vorgänge ausgeführt werden, werden komplett zurückgesetzt. Ressourcen werden in ihren vorherigen Zustand zurückgesetzt.|  
|Transacted Operations In Doubt|Die Anzahl der durchgeführten abgewickelten Vorgänge, deren Transaktion mit dem Ergebnis „zweifelhaft“ abgeschlossen wurde. Eine Arbeit, deren Ergebnis zweifelhaft ist, befindet sich in einem unbestimmten Zustand. Für das ausstehende Ergebnis werden Ressourcen bereitgehalten.|  
|Transacted Operations In Doubt Per Second|Die Anzahl der pro Sekunde durchgeführten abgewickelten Vorgänge, deren Transaktion mit dem Ergebnis "zweifelhaft" abgeschlossen wurde. Eine Arbeit, deren Ergebnis zweifelhaft ist, befindet sich in einem unbestimmten Zustand. Für das ausstehende Ergebnis werden Ressourcen bereitgehalten.|  
  
### <a name="endpoint-performance-counters"></a>Endpunktleistungsindikatoren  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|Übergegangene Transaktionen|Die Anzahl der Transaktionen, die an diesem Endpunkt in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Nachricht, die an den Endpunkt gesendet wird, eine Transaktion enthält.|  
|Übergegangene Transaktionen pro Sekunde|Die Anzahl der Transaktionen, die innerhalb von einer Sekunde an diesem Endpunkt in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Nachricht, die an den Endpunkt gesendet wird, eine Transaktion enthält.|  
  
### <a name="operation-performance-counters"></a>Vorgangsleistungsindikatoren  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|Übergegangene Transaktionen|Die Anzahl der Transaktionen, die an diesem Endpunkt in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Nachricht, die an den Endpunkt gesendet wird, eine Transaktion enthält.|  
|Übergegangene Transaktionen pro Sekunde|Die Anzahl der Transaktionen, die innerhalb von einer Sekunde an diesem Endpunkt in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Nachricht, die an den Endpunkt gesendet wird, eine Transaktion enthält.|  
  
## <a name="windows-management-instrumentation"></a>Windows-Verwaltungsinstrumentation  
 WCF macht Inspektionsdaten eines Dienstanbieters zur Laufzeit über einen WCF-Windows-Verwaltungsinstrumentation (WMI)-Anbieter verfügbar. Weitere Informationen zum Zugreifen auf WMI-Daten finden [Sie unter Verwenden von Windows-Verwaltungsinstrumentation für die Diagnose](../diagnostics/wmi/index.md).  
  
 Einige schreibgeschützte WMI-Eigenschaften geben die angewendeten Transaktionseinstellungen für einen Dienst an. In der folgenden Tabelle sind alle diese Einstellungen aufgeführt.  
  
 In einem Dienst weist  `ServiceBehaviorAttribute` die folgenden Eigenschaften auf.  
  
|Name|type|BESCHREIBUNG|  
|----------|----------|-----------------|  
|ReleaseServiceInstanceOnTransactionComplete|Boolesch|Gibt an, ob das Dienstobjekt wiederverwendet wird, wenn die aktuelle Transaktion abgeschlossen wird.|  
|TransactionAutoCompleteOnSessionClose|Boolesch|Gibt an, ob ausstehende Transaktionen abgeschlossen werden, wenn die aktuelle Sitzung schließt.|  
|TransactionIsolationLevel|Eine Zeichenfolge, die einen gültigen Wert der Enumeration <xref:System.Transactions.IsolationLevel> enthält.|Gibt die Transaktionsisolationsstufe an, die dieser Dienst unterstützt.|  
|TransactionTimeout|<xref:System.DateTime>|Gibt den Zeitraum an, innerhalb dessen eine Transaktion abgeschlossen werden muss.|  
  
 `ServiceTimeoutsBehavior` verfügt über die folgende Eigenschaft.  
  
|Name|type|BESCHREIBUNG|  
|----------|----------|-----------------|  
|TransactionTimeout|<xref:System.DateTime>|Gibt den Zeitraum an, innerhalb dessen eine Transaktion abgeschlossen werden muss.|  
  
 In einer Bindung weist  `TransactionFlowBindingElement` die folgenden Eigenschaften auf.  
  
|Name|type|BESCHREIBUNG|  
|----------|----------|-----------------|  
|TransactionProtocol|Eine Zeichenfolge, die einen gültigen Wert des Typs <xref:System.ServiceModel.TransactionProtocol> enthält.|Gibt das Transaktionsprotokoll an, das beim Durchführen einer Transaktion verwendet werden sollte.|  
|TransactionFlow|Boolesch|Gibt an, ob der eingehende Transaktionsfluss aktiviert ist.|  
  
 In einem Vorgang weist `OperationBehaviorAttribute` die folgenden Eigenschaften auf:  
  
|Name|type|BESCHREIBUNG|  
|----------|----------|-----------------|  
|TransactionAutoComplete|Boolesch|Gibt an, ob die aktuelle Transaktion automatisch übermittelt werden soll, wenn keine nicht behandelten Ausnahmen auftreten.|  
|TransactionScopeRequired|Boolesch|Gibt an, ob der Vorgang eine Transaktion erfordert.|  
  
 In einem Vorgang weist `TransactionFlowAttribute` die folgenden Eigenschaften auf.  
  
|Name|type|BESCHREIBUNG|  
|----------|----------|-----------------|  
|TransactionFlowOption|Eine Zeichenfolge, die einen gültigen Wert der Enumeration <xref:System.ServiceModel.TransactionFlowOption> enthält.|Gibt den Umfang an, in dem ein Transaktionsfluss erforderlich ist.|  
  
## <a name="tracing"></a>Ablaufverfolgung  
 Ablaufverfolgungen ermöglichen es, Fehler in den Transaktionsanwendungen zu überwachen und zu analysieren. Die Ablaufverfolgung kann auf verschiedene Weise aktiviert werden:  
  
- WCF-Standard Ablauf Verfolgung  
  
     Diese Art der Ablauf Verfolgung ist identisch mit der Ablauf Verfolgung einer beliebigen WCF-Anwendung. Weitere Informationen finden Sie unter [Configuring Tracing](../diagnostics/tracing/configuring-tracing.md).  
  
- WS-AtomicTransaction-Ablaufverfolgung  
  
     Die WS-AtomicTransaction-Ablauf Verfolgung kann mit dem [WS-AtomicTransaction-Konfigurations Hilfsprogramm (wsatConfig. exe)](../ws-atomictransaction-configuration-utility-wsatconfig-exe.md)aktiviert werden. Eine derartige Ablaufverfolgung bietet einen Einblick in den Zustand der Transaktionen und Teilnehmer innerhalb eines Systems. Zum Aktivieren der Service Model-Ablaufverfolgung muss der `HKLM\SOFTWARE\Microsoft\WSAT\3.0\ServiceModelDiagnosticTracing`-Registrierungsschlüssel auf einen gültigen Wert der Enumeration <xref:System.Diagnostics.SourceLevels> festgelegt sein. Sie können die Nachrichten Protokollierung auf die gleiche Weise aktivieren wie andere WCF-Anwendungen.  
  
- `System.Transactions`-Ablaufverfolgung  
  
     Bei Verwendung des OleTransactions-Protokolls können Protokollnachrichten nicht aufgezeichnet werden. Die Ablaufverfolgung, die von der <xref:System.Transactions>-Infrastruktur geboten wird (die OleTransactions nutzt), ermöglicht es den Benutzern, Ereignisse, die bei den Transaktionen geschehen sind, anzusehen. Um die Ablaufverfolgung für eine <xref:System.Transactions>-Anwendung zu aktivieren, integrieren Sie den folgenden Code in die Konfigurationsdatei `App.config`.  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
         <sources>  
            <source name="System.Transactions" switchValue="Verbose, ActivityTracing">  
               <listeners>  
                  <add name="Text"  
                     type="System.Diagnostics.XmlWriterTraceListener"  
                     initializeData="SysTx.log"  
                     traceOutputOptions="Callstack" />  
               </listeners>  
            </source>  
         </sources>  
         <trace autoflush="true" indentsize="4">  
         </trace>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
     Dies ermöglicht auch die WCF-Ablauf Verfolgung, da WCF auch die- <xref:System.Transactions> Infrastruktur nutzt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwaltung und Diagnose](../diagnostics/index.md)
- [Konfigurieren der Ablaufverfolgung](../diagnostics/tracing/configuring-tracing.md)
- [WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)](../ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
