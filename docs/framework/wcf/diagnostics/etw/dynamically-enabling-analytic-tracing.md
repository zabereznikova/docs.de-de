---
title: Dynamisches Aktivieren der analytischen Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: 68152741541fdbc048ba290cfb956babaed2e0d7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803488"
---
# <a name="dynamically-enabling-analytic-tracing"></a>Dynamisches Aktivieren der analytischen Ablaufverfolgung
Mit Tools, die im Lieferumfang des Windows-Betriebssystems enthalten sind, können Sie die Ablaufverfolgung mithilfe der Ereignisablaufverfolgung für Windows (ETW) aktivieren und deaktivieren. Für alle [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] Windows Communication Foundation (WCF)-Dienste aktivierten und deaktivierten dynamisch ohne Ändern der Anwendungsdatei "Web.config" oder Neustarten des Diensts, kann analytische Ablaufverfolgung werden. Auf diese Weise wird die Anwendung, die die Ablaufverfolgungsereignisse ausgibt, nicht beeinträchtigt.  
  
 Optionen für WCF-Ablaufverfolgung können auf ähnliche Weise konfiguriert werden. Sie können z. B. den Schweregrad von **Error** in **Information** ändern, ohne die Anwendung zu beeinträchtigen. Sie können dafür die folgenden Tools verwenden:  
  
-   **Logman** – Ein Befehlszeilentool zum Konfigurieren, Steuern und Abfragen von Ablaufverfolgungsdaten. Weitere Informationen finden Sie unter [Logman erstellen Trace](http://go.microsoft.com/fwlink/?LinkId=165426) und [Logman Update Trace](http://go.microsoft.com/fwlink/?LinkId=165427).  
  
-   **Ereignisanzeige (EventViewer)** – Grafisches Windows-Verwaltungstool zum Anzeigen der Ergebnisse einer Ablaufverfolgung. Weitere Informationen finden Sie unter [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md) und [Ereignisanzeige](http://go.microsoft.com/fwlink/?LinkId=165428).  
  
-   **Perfmon** – Grafisches Windows-Verwaltungstool, das Indikatoren zum Überwachen der Ablaufverfolgung und der Auswirkungen der Ablaufverfolgung auf die Leistung verwendet. Weitere Informationen finden Sie unter [Erstellen einer Data Collector manuell](http://go.microsoft.com/fwlink/?LinkId=165429).  
  
### <a name="keywords"></a>Stichwörter  
 Wenn Sie die <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> -Klasse verwenden, werden .NET Framework-Ablaufverfolgungsmeldungen im Allgemeinen nach dem Schweregrad gefiltert (z. B. "Error", "Warning" und "Information") gefiltert. ETW unterstützt das Schweregradkonzept, führt jedoch einen neuen, flexiblen Filtermechanismus mit Schlüsselwörtern ein. Schlüsselwörter sind beliebige Textwerte, über die Ablaufverfolgungsereignisse zusätzlichen Kontext zur Bedeutung eines Ereignisses bereitstellen können.  
  
 Für die analytische Ablaufverfolgung von WCF verfügt jedes Ablaufverfolgungsereignis zwei Typen von Schlüsselwörtern. Erstens verfügt jedes Ereignis über ein oder mehrere Szenarioschlüsselwörter. Diese Schlüsselwörter bezeichnen die Szenarien, die das Ereignis unterstützen soll. Es gibt drei Szenarioschlüsselwörter, die jeweils einen bestimmten Zweck haben. Dies ist in der folgenden Tabelle beschrieben. Filtern mit Schlüsselwörtern kann dynamisch geändert werden, ohne den WCF-Dienst beeinträchtigen. Dies bedeutet, dass Sie das aktuelle Ablaufverfolgungsszenario und die Menge der erfassten Ablaufverfolgungsinformationen dynamisch ändern können. Sie können z. B. `HealthMonitoring` in `Troubleshooting` ändern und die Granularität für Ablaufverfolgungsereignisse erhöhen.  
  
|Stichwort|Beschreibung|  
|-------------|-----------------|  
|`HealthMonitoring`|Sehr einfache, minimale Ablaufverfolgung, mit der Sie die Aktivität des Diensts überwachen können.|  
|`EndToEndMonitoring`|Ereignisse, die zum Unterstützen der Ablaufverfolgung des Nachrichtenflusses verwendet werden.|  
|`Troubleshooting`|Genauere Ereignisse in Bezug auf die Erweiterbarkeitspunkte von WCF.|  
  
 Die zweite Gruppe von Schlüsselwörtern definiert, welche Komponente von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] das Ereignis ausgegeben hat.  
  
|Stichwort|Beschreibung|  
|-------------|-----------------|  
|`UserEvents`|Vom Benutzercode und nicht von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]ausgegebene Ereignisse.|  
|`ServiceModel`|Ereignisse, die von der WCF-Laufzeit ausgegeben werden.|  
|`ServiceHost`|Vom Diensthost ausgegebene Ereignisse.|  
|`WCFMessageLogging`|-Ereignisse zur nachrichtenprotokollierung WCF.|  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
