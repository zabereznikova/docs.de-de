---
title: WCF-Leistungsindikatoren
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
ms.openlocfilehash: d0ad7ee0bc3ea1d15197e6b8d9888d60b21a2f15
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44192183"
---
# <a name="wcf-performance-counters"></a>WCF-Leistungsindikatoren
Windows Communication Foundation (WCF) umfasst eine große Anzahl von Leistungsindikatoren können Sie die Leistung Ihrer Anwendung zu messen.  
  
## <a name="enabling-performance-counters"></a>Aktivieren von Leistungsindikatoren  
 Sie können die Leistungsindikatoren für einen WCF-Dienst über die Konfigurationsdatei "App.config" des WCF-Diensts wie folgt aktivieren:  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 Das `performanceCounters`-Attribut kann dafür festgelegt werden, dass ein bestimmter Typ von Leistungsindikatoren aktiviert wird. Folgende Werte sind gültig:  
  
-   All: Alle Kategorieindikatoren (ServiceModelService, ServiceModelEndpoint und ServiceModelOperation) werden aktiviert.  
  
-   ServiceOnly: Nur ServiceModelService-Kategorieindikatoren werden aktiviert. Dies ist der Standardwert.  
  
-   Off: ServiceModel*-Leistungsindikatoren werden deaktiviert.  
  
 Wenn Sie die Leistungsindikatoren für alle WCF-Anwendungen aktivieren möchten, können Sie die Konfigurationseinstellungen in der Datei "Machine.config" platzieren.  Informieren Sie sich die **Erhöhen der Arbeitsspeichergröße für Leistungsindikatoren** Abschnitt unten für Weitere Informationen zum Konfigurieren ausreichenden Arbeitsspeichers für Leistungsindikatoren auf Ihrem Computer.  
  
 Wenn Sie WCF-Erweiterbarkeitspunkte wie z. B. benutzerdefinierte Vorgangsaufrufer verwenden, sollten Sie auch eigene Leistungsindikatoren ausgeben. Das liegt bei der Implementierung eines Erweiterungspunkts WCF nicht mehr die standardmäßigen Leistungsindikatordaten im Standardpfad ausgeben kann. Wenn Sie keine Unterstützung für manuelle Leistungsindikatoren implementieren, werden die erwarteten Leistungsindikatordaten möglicherweise nicht angezeigt.  
  
 Leistungsindikatoren können auch folgendermaßen im Code aktiviert werden:  
  
```  
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a>Anzeigen von Leistungsdaten  
 Wenn Sie von den Leistungsindikatoren erfasste Daten anzeigen möchten, verwenden Sie den in Windows integrierten Leistungsmonitor (Perfmon.exe). Sie können dieses Tool starten, indem Sie zu **starten**, und klicken Sie auf **ausführen** und `perfmon.exe` im Dialogfeld.  
  
> [!NOTE]
>  Leistungsindikatorinstanzen werden möglicherweise freigegeben, bevor die letzten Nachrichten vom Endpunktverteiler verarbeitet wurden. Dies kann dazu führen, dass Leistungsdaten für einige Nachrichten nicht erfasst werden.  
  
## <a name="increasing-memory-size-for-performance-counters"></a>Erhöhen der Arbeitsspeichergröße für Leistungsindikatoren  
 WCF verwendet separaten freigegebenen Arbeitsspeicher für die Leistungsindikatorkategorien.  
  
 Standardmäßig wird separater freigegebener Arbeitsspeicher auf ein Viertel der Größe des globalen Leistungsindikator-Arbeitsspeichers festgelegt. Der standardmäßige globale Leistungsindikator-Arbeitsspeicher besitzt eine Größe von 524.288 Byte. Daher müssen die drei WCF-Leistungsindikatorkategorien eine Standardgröße von ungefähr 128KB. Abhängig von den laufzeitmerkmalen der WCF-Clientanwendungen auf einem Computer, kann Arbeitsspeicher des Leistungsindikators erschöpft sein. In diesem Fall schreibt WCF einen Fehler in das Anwendungsereignisprotokoll. Der Inhaltsfehler gibt an, dass ein Leistungsindikator nicht geladen wurde, und der Eintrag beinhaltet die Ausnahme "System.InvalidOperationException: Nicht genügend Arbeitsspeicher zum Anzeigen der benutzerdefinierten Indikatordatei." Wird die Ablaufverfolgung auf Fehlerebene aktiviert, wird dieser Fehler ebenfalls nachverfolgt. Wenn der Arbeitsspeicher des Leistungsindikators erschöpft ist, kann weiterhin ausgeführt wird Ihre WCF-Anwendungen mit aktivierten Leistungsindikatoren zu Leistungseinbußen führen. Der zuständige Administrator sollte den Computer für das Zuordnen von ausreichendem Arbeitsspeicher konfigurieren, damit die maximale Anzahl der Leistungsindikatoren, die jederzeit vorhanden sein können, unterstützt wird.  
  
 Sie können die Menge des Leistungsindikator-Arbeitsspeichers für WCF-Kategorien in der Registrierung ändern. Dazu muss den drei folgenden Speicherorten ein neuer DWORD-Wert mit der Bezeichnung `FileMappingSize` hinzugefügt und auf den gewünschten Wert in Byte festgelegt werden. Starten Sie den Computer neu, damit diese Änderungen wirksam werden.  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance  
  
 Wenn eine große Anzahl von Objekten (z. B. ServiceHost) verworfen wird, die automatische Speicherbereinigung jedoch noch aussteht, registriert der `PrivateBytes`-Leistungsindikator eine ungewöhnlich hohe Anzahl. Zum Beheben dieses Problems können Sie entweder eigene anwendungsspezifische Indikatoren hinzufügen oder mithilfe des `performanceCounters`-Attributs nur Indikatoren auf Dienstebene aktivieren.  
  
## <a name="types-of-performance-counters"></a>Leistungsindikatortypen  
 Leistungsindikatoren werden für drei verschiedene Ebenen festgelegt: Dienst, Endpunkt und Vorgang.  
  
 Sie können WMI verwenden, um den Namen einer Leistungsindikatorinstanz abzurufen. Ein auf ein Objekt angewendeter  
  
-   -Instanzname des Indikators Service erhalten Sie über WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) die "CounterInstanceName"-Eigenschaft der Instanz.  
  
-   Namen der Leistungsindikatorinstanz Endpunkt erhalten Sie über WMI [Endpunkt](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) die "CounterInstanceName"-Eigenschaft der Instanz.  
  
-   Namen der Leistungsindikatorinstanz Vorgang erhalten Sie über WMI [Endpunkt](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) die "GetOperationCounterInstanceName"-Methode Instanz.  
  
 Weitere Informationen zu WMI finden Sie unter [mithilfe von Windows-Verwaltungsinstrumentation für die Diagnose](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
### <a name="service-performance-counters"></a>Dienstleistungsindikatoren  
 Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft. Sie sind beim Anzeigen mit dem Leistungsmonitor unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden. Die Instanzen werden nach dem folgenden Schema benannt:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 Ein Indikator in einem Dienstbereich wird vom Indikator in einer Auflistung von Endpunkten aggregiert.  
  
 Leistungsindikatoren zur Dienstinstanzerstellung werden inkrementiert, wenn ein neuer InstanceContext erstellt wird. Beachten Sie, dass auch dann ein neuer InstanceContext erstellt wird, wenn eine nicht aktivierende Nachricht empfangen wird (mit einem vorhandenen Dienst), oder wenn Sie von einer Sitzung aus eine Verbindung zu einer Instanz herstellen, die Sitzung beenden und dann von einer anderen Sitzung aus die Verbindung wieder herstellen.  
  
### <a name="endpoint-performance-counters"></a>Endpunktleistungsindikatoren  
 Endpunktleistungsindikatoren ermöglichen das Anzeigen von Daten, die das Akzeptieren von Nachrichten durch einen Endpunkt widerspiegeln. Sie sind beim Anzeigen mit dem Leistungsmonitor unter dem `ServiceModelEndpoint 4.0.0.0`-Leistungsobjekt zu finden. Die Instanzen werden nach dem folgenden Schema benannt:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Die Daten ähneln den Daten, die für einzelne Vorgänge erfasst werden, sie werden jedoch nur über den Endpunkt aggregiert.  
  
 Ein Indikator in einem Endpunktbereich wird von den Indikatoren in einer Auflistung von Vorgängen aggregiert.  
  
> [!NOTE]
>  Wenn zwei Endpunkte identische Vertragsnamen und Adressen besitzen, werden sie derselben Indikatorinstanz zugeordnet.  
  
### <a name="operation-performance-counters"></a>Vorgangsleistungsindikatoren  
 Vorgangsleistungsindikatoren befinden sich unter dem `ServiceModelOperation 4.0.0.0`-Leistungsobjekt, wenn sie mit dem Leistungsmonitor angezeigt werden. Jeder Vorgang hat eine einzelne Instanz. Das heißt, wenn ein bestimmter Vertrag 10 Vorgänge enthält, werden mit diesem Vertrag 10 Vorgangsleistungsindikatoren verbunden. Die Objektinstanzen werden nach dem folgenden Muster benannt:  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 Mit diesem Indikator können Sie messen, wie der Aufruf verwendet wird und wie gut der Vorgang funktioniert.  
  
 Wenn Indikatoren in mehreren Bereichen angezeigt werden können, werden von einem höheren Bereich gesammelte Daten mit Daten aus niedrigeren Bereichen aggregiert. Beispielsweise ist `Calls` an einem Endpunkt die Summe aller Vorgangsaufrufe innerhalb des Endpunkts; bei einem Dienst ist `Calls` die Summe aller Aufrufe von Endpunkten innerhalb des Diensts.  
  
> [!NOTE]
>  Sind in einem Vertrag Vorgangsnamen doppelt vorhanden, wird nur eine Indikatorinstanz für beide Vorgänge ausgegeben.  
  
## <a name="programming-the-wcf-performance-counters"></a>Programmieren der WCF-Leistungsindikatoren  
 Mehrere Dateien werden in SDK-Installationsordner installiert, sodass Sie die WCF-Leistungsindikatoren programmgesteuert zugreifen können. Diese Dateien werden wie folgt aufgelistet.  
  
-   _ServiceModelEndpointPerfCounters.vrg  
  
-   _ServiceModelOperationPerfCounters.vrg  
  
-   _ServiceModelServicePerfCounters.vrg  
  
-   _SMSvcHostPerfCounters.vrg  
  
-   _TransactionBridgePerfCounters.vrg  
  
 Weitere Informationen zum programmgesteuerten Zugriff auf die Indikatoren finden Sie unter [Architektur der Leistungsindikatorprogrammierung](https://go.microsoft.com/fwlink/?LinkId=95179).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
