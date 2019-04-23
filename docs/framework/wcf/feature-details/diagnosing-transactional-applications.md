---
title: Erkennen einer Transaktionsanwendung
ms.date: 03/30/2017
ms.assetid: 4a993492-1088-4d10-871b-0c09916af05f
ms.openlocfilehash: aca5f95e2085dfadf06da35dfd86af72c0b6092d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101711"
---
# <a name="diagnosing-transactional-applications"></a>Erkennen einer Transaktionsanwendung
Dieses Thema beschreibt, wie Sie die Windows Communication Foundation (WCF)-Verwaltung und die Diagnosefunktion zu verwenden, um einer transaktionsanwendung zu beheben.  
  
## <a name="performance-counters"></a>Leistungsindikatoren  
 WCF bietet einen Standardsatz von Leistungsindikatoren für den Sie transaktionale die Leistung Ihrer Anwendung zu messen. Weitere Informationen finden Sie unter [Leistungsindikatoren](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md).  
  
 Leistungsindikatoren werden in drei verschiedene Stufen unterteilt: Dienst, Endpunkt und Vorgang, gemäß folgender Tabellen.  
  
### <a name="service-performance-counters"></a>Dienst-Leistungsindikatoren  
  
|Leistungsindikator|Beschreibung|  
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
  
|Leistungsindikator|Beschreibung|  
|-------------------------|-----------------|  
|Übergegangene Transaktionen|Die Anzahl der Transaktionen, die an diesem Endpunkt in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Nachricht, die an den Endpunkt gesendet wird, eine Transaktion enthält.|  
|Übergegangene Transaktionen pro Sekunde|Die Anzahl der Transaktionen, die innerhalb von einer Sekunde an diesem Endpunkt in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Nachricht, die an den Endpunkt gesendet wird, eine Transaktion enthält.|  
  
### <a name="operation-performance-counters"></a>Vorgangsleistungsindikatoren  
  
|Leistungsindikator|Beschreibung|  
|-------------------------|-----------------|  
|Übergegangene Transaktionen|Die Anzahl der Transaktionen, die an diesem Endpunkt in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Nachricht, die an den Endpunkt gesendet wird, eine Transaktion enthält.|  
|Übergegangene Transaktionen pro Sekunde|Die Anzahl der Transaktionen, die innerhalb von einer Sekunde an diesem Endpunkt in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Nachricht, die an den Endpunkt gesendet wird, eine Transaktion enthält.|  
  
## <a name="windows-management-instrumentation"></a>Windows-Verwaltungsinstrumentation (Windows Management Instrumentation)  
 WCF macht inspektionsdaten eines Diensts zur Laufzeit über einen WCF (Windows Management Instrumentation, WMI) Anbieter verfügbar. Weitere Informationen zum Zugreifen auf WMI-Daten finden Sie unter [mithilfe von Windows-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
 Einige schreibgeschützte WMI-Eigenschaften geben die angewendeten Transaktionseinstellungen für einen Dienst an. In der folgenden Tabelle sind alle diese Einstellungen aufgeführt.  
  
 In einem Dienst weist  `ServiceBehaviorAttribute` die folgenden Eigenschaften auf.  
  
|Name|Typ|Beschreibung|  
|----------|----------|-----------------|  
|ReleaseServiceInstanceOnTransactionComplete|Boolesch|Gibt an, ob das Dienstobjekt wiederverwendet wird, wenn die aktuelle Transaktion abgeschlossen wird.|  
|TransactionAutoCompleteOnSessionClose|Boolesch|Gibt an, ob ausstehende Transaktionen abgeschlossen werden, wenn die aktuelle Sitzung schließt.|  
|TransactionIsolationLevel|Eine Zeichenfolge, die einen gültigen Wert der Enumeration <xref:System.Transactions.IsolationLevel> enthält.|Gibt die Transaktionsisolationsstufe an, die dieser Dienst unterstützt.|  
|TransactionTimeout|<xref:System.DateTime>|Gibt den Zeitraum an, innerhalb dessen eine Transaktion abgeschlossen werden muss.|  
  
 `ServiceTimeoutsBehavior` verfügt über die folgende Eigenschaft.  
  
|Name|Typ|Beschreibung|  
|----------|----------|-----------------|  
|TransactionTimeout|<xref:System.DateTime>|Gibt den Zeitraum an, innerhalb dessen eine Transaktion abgeschlossen werden muss.|  
  
 In einer Bindung weist  `TransactionFlowBindingElement` die folgenden Eigenschaften auf.  
  
|Name|Typ|Beschreibung|  
|----------|----------|-----------------|  
|TransactionProtocol|Eine Zeichenfolge, die einen gültigen Wert des Typs <xref:System.ServiceModel.TransactionProtocol> enthält.|Gibt das Transaktionsprotokoll an, das beim Durchführen einer Transaktion verwendet werden sollte.|  
|TransactionFlow|Boolesch|Gibt an, ob der eingehende Transaktionsfluss aktiviert ist.|  
  
 In einem Vorgang weist `OperationBehaviorAttribute` die folgenden Eigenschaften auf:  
  
|Name|Typ|Beschreibung|  
|----------|----------|-----------------|  
|TransactionAutoComplete|Boolesch|Gibt an, ob die aktuelle Transaktion automatisch übermittelt werden soll, wenn keine nicht behandelten Ausnahmen auftreten.|  
|TransactionScopeRequired|Boolesch|Gibt an, ob der Vorgang eine Transaktion erfordert.|  
  
 In einem Vorgang weist `TransactionFlowAttribute` die folgenden Eigenschaften auf.  
  
|Name|Typ|Beschreibung|  
|----------|----------|-----------------|  
|TransactionFlowOption|Eine Zeichenfolge, die einen gültigen Wert der Enumeration <xref:System.ServiceModel.TransactionFlowOption> enthält.|Gibt den Umfang an, in dem ein Transaktionsfluss erforderlich ist.|  
  
## <a name="tracing"></a>Ablaufverfolgung  
 Ablaufverfolgungen ermöglichen es, Fehler in den Transaktionsanwendungen zu überwachen und zu analysieren. Die Ablaufverfolgung kann auf verschiedene Weise aktiviert werden:  
  
-   Standard-WCF-Ablaufverfolgung  
  
     Dieser Typ der Ablaufverfolgung ist identisch mit der Ablaufverfolgung für alle WCF-Anwendung. Weitere Informationen finden Sie unter [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
-   WS-AtomicTransaction-Ablaufverfolgung  
  
     WS-AtomicTransaction-Ablaufverfolgung kann aktiviert werden, mithilfe der [WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md). Eine derartige Ablaufverfolgung bietet einen Einblick in den Zustand der Transaktionen und Teilnehmer innerhalb eines Systems. Zum Aktivieren der Service Model-Ablaufverfolgung muss der `HKLM\SOFTWARE\Microsoft\WSAT\3.0\ServiceModelDiagnosticTracing`-Registrierungsschlüssel auf einen gültigen Wert der Enumeration <xref:System.Diagnostics.SourceLevels> festgelegt sein. Sie können die nachrichtenprotokollierung auf die gleiche Weise wie andere WCF-Anwendungen aktivieren.  
  
-   `System.Transactions`-Ablaufverfolgung  
  
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
  
     Dies aktiviert außerdem die WCF-Ablaufverfolgung, wie WCF außerdem verwendet die <xref:System.Transactions> Infrastruktur.  
  
## <a name="see-also"></a>Siehe auch

- [Verwaltung und Diagnose](../../../../docs/framework/wcf/diagnostics/index.md)
- [Konfigurieren der Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [WS-AtomicTransaction-Konfigurationshilfsprogramm (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
