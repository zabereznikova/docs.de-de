---
title: Dynamisches Aktivieren der analytischen Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: bea64ac9a9312d17b7f47e72a46d876552e20a12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798099"
---
# <a name="dynamically-enabling-analytic-tracing"></a>Dynamisches Aktivieren der analytischen Ablaufverfolgung
Mit Tools, die im Lieferumfang des Windows-Betriebssystems enthalten sind, können Sie die Ablaufverfolgung mithilfe der Ereignisablaufverfolgung für Windows (ETW) aktivieren und deaktivieren. Für alle [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] Windows Communication Foundation (WCF)-Dienste kann die analytische Ablauf Verfolgung dynamisch aktiviert und deaktiviert werden, ohne die Datei "Web. config" der Anwendung zu ändern oder den Dienst neu zu starten. Auf diese Weise wird die Anwendung, die die Ablaufverfolgungsereignisse ausgibt, nicht beeinträchtigt.  
  
 WCF-Ablauf Verfolgungs Optionen können auf ähnliche Weise konfiguriert werden. Sie können z. B. den Schweregrad von **Error** in **Information** ändern, ohne die Anwendung zu beeinträchtigen. Sie können dafür die folgenden Tools verwenden:  
  
- **Logman** – Ein Befehlszeilentool zum Konfigurieren, Steuern und Abfragen von Ablaufverfolgungsdaten. Weitere Informationen finden Sie unter [logman Create Trace](https://go.microsoft.com/fwlink/?LinkId=165426) und [logman update Trace](https://go.microsoft.com/fwlink/?LinkId=165427).  
  
- **Ereignisanzeige (EventViewer)** – Grafisches Windows-Verwaltungstool zum Anzeigen der Ergebnisse einer Ablaufverfolgung. Weitere Informationen finden Sie unter [WCF-Dienste und Ereignis Ablauf Verfolgung für Windows](../../samples/wcf-services-and-event-tracing-for-windows.md) und [Ereignisanzeige](https://go.microsoft.com/fwlink/?LinkId=165428).  
  
- **Perfmon** – Grafisches Windows-Verwaltungstool, das Indikatoren zum Überwachen der Ablaufverfolgung und der Auswirkungen der Ablaufverfolgung auf die Leistung verwendet. Weitere Informationen finden Sie unter [Manuelles Erstellen eines Datensammler Satzes](https://go.microsoft.com/fwlink/?LinkId=165429).  
  
### <a name="keywords"></a>Schlüsselwörter  
 Wenn Sie die <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> -Klasse verwenden, werden .NET Framework-Ablaufverfolgungsmeldungen im Allgemeinen nach dem Schweregrad gefiltert (z. B. "Error", "Warning" und "Information") gefiltert. ETW unterstützt das Schweregradkonzept, führt jedoch einen neuen, flexiblen Filtermechanismus mit Schlüsselwörtern ein. Schlüsselwörter sind beliebige Textwerte, über die Ablaufverfolgungsereignisse zusätzlichen Kontext zur Bedeutung eines Ereignisses bereitstellen können.  
  
 Bei der analytischen WCF-Ablauf Verfolgung verfügt jedes Ablauf Verfolgungs Ereignis über zwei Arten von Schlüsselwörtern. Erstens verfügt jedes Ereignis über ein oder mehrere Szenarioschlüsselwörter. Diese Schlüsselwörter bezeichnen die Szenarien, die das Ereignis unterstützen soll. Es gibt drei Szenarioschlüsselwörter, die jeweils einen bestimmten Zweck haben. Dies ist in der folgenden Tabelle beschrieben. Das Filtern mit Schlüsselwörtern kann dynamisch geändert werden, ohne den WCF-Dienst zu beeinträchtigen. Dies bedeutet, dass Sie das aktuelle Ablaufverfolgungsszenario und die Menge der erfassten Ablaufverfolgungsinformationen dynamisch ändern können. Sie können z. B. `HealthMonitoring` in `Troubleshooting` ändern und die Granularität für Ablaufverfolgungsereignisse erhöhen.  
  
|Schlüsselwort|Beschreibung|  
|-------------|-----------------|  
|`HealthMonitoring`|Sehr einfache, minimale Ablaufverfolgung, mit der Sie die Aktivität des Diensts überwachen können.|  
|`EndToEndMonitoring`|Ereignisse, die zum Unterstützen der Ablaufverfolgung des Nachrichtenflusses verwendet werden.|  
|`Troubleshooting`|Genauere Ereignisse in Bezug auf die Erweiterbarkeits Punkte von WCF.|  
  
 Die zweite Gruppe von Schlüsselwörtern definiert, welche Komponente des .NET Framework das Ereignis ausgegeben hat.  
  
|Schlüsselwort|Beschreibung|  
|-------------|-----------------|  
|`UserEvents`|Ereignisse, die vom Benutzercode ausgegeben werden, und nicht die .NET Framework.|  
|`ServiceModel`|Ereignisse, die von der WCF-Laufzeit ausgegeben werden.|  
|`ServiceHost`|Vom Diensthost ausgegebene Ereignisse.|  
|`WCFMessageLogging`|Ereignisse der WCF-Nachrichten Protokollierung.|  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
