---
title: Dynamisches Aktivieren der analytischen Ablaufverfolgung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d070c66eebbf1a067254c38c6e5bfc7f40742863
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="dynamically-enabling-analytic-tracing"></a>Dynamisches Aktivieren der analytischen Ablaufverfolgung
Mit Tools, die im Lieferumfang des Windows-Betriebssystems enthalten sind, können Sie die Ablaufverfolgung mithilfe der Ereignisablaufverfolgung für Windows (ETW) aktivieren und deaktivieren. Die analytische Ablaufverfolgung kann für alle [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] -Dienste dynamisch aktiviert und deaktiviert werden, ohne dass die Web.config-Datei der Anwendung geändert oder der Dienst neu gestartet werden muss. Auf diese Weise wird die Anwendung, die die Ablaufverfolgungsereignisse ausgibt, nicht beeinträchtigt.  
  
 Die Ablaufverfolgungsoptionen von[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] können auf ähnliche Weise konfiguriert werden. Sie können z. B. den Schweregrad von **Error** in **Information** ändern, ohne die Anwendung zu beeinträchtigen. Sie können dafür die folgenden Tools verwenden:  
  
-   **Logman** – Ein Befehlszeilentool zum Konfigurieren, Steuern und Abfragen von Ablaufverfolgungsdaten. Weitere Informationen finden Sie unter [Logman erstellen Trace](http://go.microsoft.com/fwlink/?LinkId=165426) und [Logman Update Trace](http://go.microsoft.com/fwlink/?LinkId=165427).  
  
-   **Ereignisanzeige (EventViewer)** – Grafisches Windows-Verwaltungstool zum Anzeigen der Ergebnisse einer Ablaufverfolgung. Weitere Informationen finden Sie unter [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md) und [Ereignisanzeige](http://go.microsoft.com/fwlink/?LinkId=165428).  
  
-   **Perfmon** – Grafisches Windows-Verwaltungstool, das Indikatoren zum Überwachen der Ablaufverfolgung und der Auswirkungen der Ablaufverfolgung auf die Leistung verwendet. Weitere Informationen finden Sie unter [Erstellen einer Data Collector manuell](http://go.microsoft.com/fwlink/?LinkId=165429).  
  
### <a name="keywords"></a>Stichwörter  
 Wenn Sie die <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> -Klasse verwenden, werden .NET Framework-Ablaufverfolgungsmeldungen im Allgemeinen nach dem Schweregrad gefiltert (z. B. "Error", "Warning" und "Information") gefiltert. ETW unterstützt das Schweregradkonzept, führt jedoch einen neuen, flexiblen Filtermechanismus mit Schlüsselwörtern ein. Schlüsselwörter sind beliebige Textwerte, über die Ablaufverfolgungsereignisse zusätzlichen Kontext zur Bedeutung eines Ereignisses bereitstellen können.  
  
 Bei der analytischen Ablaufverfolgung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] verfügt jedes Ablaufverfolgungsereignis über zwei Schlüsselworttypen. Erstens verfügt jedes Ereignis über ein oder mehrere Szenarioschlüsselwörter. Diese Schlüsselwörter bezeichnen die Szenarien, die das Ereignis unterstützen soll. Es gibt drei Szenarioschlüsselwörter, die jeweils einen bestimmten Zweck haben. Dies ist in der folgenden Tabelle beschrieben. Sie können das Filtern mit Schlüsselwörtern dynamisch ändern, ohne dabei den [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] -Dienst zu beeinträchtigen. Dies bedeutet, dass Sie das aktuelle Ablaufverfolgungsszenario und die Menge der erfassten Ablaufverfolgungsinformationen dynamisch ändern können. Sie können z. B. `HealthMonitoring` in `Troubleshooting` ändern und die Granularität für Ablaufverfolgungsereignisse erhöhen.  
  
|Stichwort|Beschreibung|  
|-------------|-----------------|  
|`HealthMonitoring`|Sehr einfache, minimale Ablaufverfolgung, mit der Sie die Aktivität des Diensts überwachen können.|  
|`EndToEndMonitoring`|Ereignisse, die zum Unterstützen der Ablaufverfolgung des Nachrichtenflusses verwendet werden.|  
|`Troubleshooting`|Genauere Ereignisse in Bezug auf die Erweiterbarkeitspunkte von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].|  
  
 Die zweite Gruppe von Schlüsselwörtern definiert, welche Komponente von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] das Ereignis ausgegeben hat.  
  
|Stichwort|Beschreibung|  
|-------------|-----------------|  
|`UserEvents`|Vom Benutzercode und nicht von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]ausgegebene Ereignisse.|  
|`ServiceModel`|Von der [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] -Laufzeit ausgegebene Ereignisse.|  
|`ServiceHost`|Vom Diensthost ausgegebene Ereignisse.|  
|`WCFMessageLogging`|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] -Ereignisse zur Nachrichtenprotokollierung.|  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
