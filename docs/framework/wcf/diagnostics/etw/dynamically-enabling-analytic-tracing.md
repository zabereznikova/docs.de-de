---
title: Dynamisches Aktivieren der analytischen Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: 2c213507f6ed4e9fff4f1385b10f22e96b0a41b4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282352"
---
# <a name="dynamically-enabling-analytic-tracing"></a>Dynamisches Aktivieren der analytischen Ablaufverfolgung

Mit Tools, die im Lieferumfang des Windows-Betriebssystems enthalten sind, können Sie die Ablaufverfolgung mithilfe der Ereignisablaufverfolgung für Windows (ETW) aktivieren und deaktivieren. Für alle [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] Windows Communication Foundation (WCF)-Dienste kann die analytische Ablauf Verfolgung dynamisch aktiviert und deaktiviert werden, ohne die Web.config Datei der Anwendung zu ändern oder den Dienst neu zu starten. Auf diese Weise wird die Anwendung, die die Ablaufverfolgungsereignisse ausgibt, nicht beeinträchtigt.  
  
 WCF-Ablauf Verfolgungs Optionen können auf ähnliche Weise konfiguriert werden. Sie können z. B. den Schweregrad von **Error** in **Information** ändern, ohne die Anwendung zu beeinträchtigen. Sie können dafür die folgenden Tools verwenden:  
  
- **Logman** – Ein Befehlszeilentool zum Konfigurieren, Steuern und Abfragen von Ablaufverfolgungsdaten. Weitere Informationen finden Sie unter [logman Create Trace](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc788036(v=ws.10)) und [logman update Trace](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc788128(v=ws.10)).  
  
- **Ereignisanzeige (EventViewer)** – Grafisches Windows-Verwaltungstool zum Anzeigen der Ergebnisse einer Ablaufverfolgung. Weitere Informationen finden Sie unter [WCF-Dienste und Ereignis Ablauf Verfolgung für Windows](../../samples/wcf-services-and-event-tracing-for-windows.md) und [Ereignisanzeige](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766042(v=ws.11)).  
  
- **Perfmon** – Grafisches Windows-Verwaltungstool, das Indikatoren zum Überwachen der Ablaufverfolgung und der Auswirkungen der Ablaufverfolgung auf die Leistung verwendet. Weitere Informationen finden Sie unter [Manuelles Erstellen eines Datensammler Satzes](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766404(v=ws.11)).  
  
### <a name="keywords"></a>Keywords  

 Wenn Sie die <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> -Klasse verwenden, werden .NET Framework-Ablaufverfolgungsmeldungen im Allgemeinen nach dem Schweregrad gefiltert (z. B. "Error", "Warning" und "Information") gefiltert. ETW unterstützt das Schweregradkonzept, führt jedoch einen neuen, flexiblen Filtermechanismus mit Schlüsselwörtern ein. Schlüsselwörter sind beliebige Textwerte, über die Ablaufverfolgungsereignisse zusätzlichen Kontext zur Bedeutung eines Ereignisses bereitstellen können.  
  
 Bei der analytischen WCF-Ablauf Verfolgung verfügt jedes Ablauf Verfolgungs Ereignis über zwei Arten von Schlüsselwörtern. Erstens verfügt jedes Ereignis über ein oder mehrere Szenarioschlüsselwörter. Diese Schlüsselwörter bezeichnen die Szenarien, die das Ereignis unterstützen soll. Es gibt drei Szenarioschlüsselwörter, die jeweils einen bestimmten Zweck haben. Dies ist in der folgenden Tabelle beschrieben. Das Filtern mit Schlüsselwörtern kann dynamisch geändert werden, ohne den WCF-Dienst zu beeinträchtigen. Dies bedeutet, dass Sie das aktuelle Ablaufverfolgungsszenario und die Menge der erfassten Ablaufverfolgungsinformationen dynamisch ändern können. Sie können z. B. `HealthMonitoring` in `Troubleshooting` ändern und die Granularität für Ablaufverfolgungsereignisse erhöhen.  
  
|Schlüsselwort|BESCHREIBUNG|  
|-------------|-----------------|  
|`HealthMonitoring`|Sehr einfache, minimale Ablaufverfolgung, mit der Sie die Aktivität des Diensts überwachen können.|  
|`EndToEndMonitoring`|Ereignisse, die zum Unterstützen der Ablaufverfolgung des Nachrichtenflusses verwendet werden.|  
|`Troubleshooting`|Genauere Ereignisse in Bezug auf die Erweiterbarkeits Punkte von WCF.|  
  
 Die zweite Gruppe von Schlüsselwörtern definiert, welche Komponente des .NET Framework das Ereignis ausgegeben hat.  
  
|Schlüsselwort|BESCHREIBUNG|  
|-------------|-----------------|  
|`UserEvents`|Ereignisse, die vom Benutzercode ausgegeben werden, und nicht die .NET Framework.|  
|`ServiceModel`|Ereignisse, die von der WCF-Laufzeit ausgegeben werden.|  
|`ServiceHost`|Vom Diensthost ausgegebene Ereignisse.|  
|`WCFMessageLogging`|Ereignisse der WCF-Nachrichten Protokollierung.|  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
