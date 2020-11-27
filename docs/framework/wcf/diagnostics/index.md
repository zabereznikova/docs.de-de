---
title: Verwaltung und Diagnose
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
ms.openlocfilehash: 703724c3040f2508f011e002c22fa45dd3197884
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285563"
---
# <a name="administration-and-diagnostics"></a>Verwaltung und Diagnose

Windows Communication Foundation (WCF) stellt einen umfangreichen Satz von Funktionen bereit, mit deren Hilfe Sie die verschiedenen Phasen der Anwendungs Lebensdauer überwachen können. Beispielsweise können Sie die Konfiguration verwenden, um Dienste und Clients bei der Bereitstellung einzurichten. WCF enthält eine große Anzahl von Leistungsindikatoren, mit denen Sie die Leistung Ihrer Anwendung messen können. WCF macht auch Inspektionsdaten eines Dienstanbieters zur Laufzeit über einen WCF-Windows-Verwaltungsinstrumentation (WMI)-Anbieter verfügbar. Trifft die Anwendung auf einen Fehler oder funktioniert die Anwendung nicht ordnungsgemäß, können Sie das Ereignisprotokoll nutzen, um festzustellen, ob etwas Schwerwiegendes eingetreten ist. Darüber hinaus können Sie die Nachrichtenprotokollierung und -ablaufverfolgung nutzen, um festzustellen, welche End-to-End-Ereignisse in Ihrer Anwendung stattfinden. Diese Features unterstützen sowohl Entwickler als auch IT-Experten bei der Problembehandlung einer WCF-Anwendung, wenn Sie sich nicht korrekt verhält.  
  
> [!NOTE]
> Wenn Sie Fehler ohne spezifische Detailinformationen erhalten, sollten Sie das- `includeExceptionDetailInFaults` Attribut des- [\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) Konfigurations Elements aktivieren. Dies weist WCF an, Ausnahme Details an Clients zu senden, sodass Sie viele häufige Probleme erkennen können, ohne dass eine erweiterte Diagnose erforderlich ist. Weitere Informationen finden Sie unter [senden und empfangen von Fehlern](../sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Durch WCF bereitgestellte Diagnosefunktionen  

 WCF stellt die folgenden Diagnosefunktionen bereit:  
  
- End-To-End-Ablaufverfolgung bietet Instrumentierungsdaten für die Fehlerbehebung einer Anwendung ohne die Verwendung eines Debuggers. WCF gibt Ablauf Verfolgungen für Prozess Meilensteine sowie Fehlermeldungen aus. Dies kann das Öffnen einer Kanalfactory oder das Senden und Empfangen von Nachrichten durch einen Diensthost einschließen. Die Ablaufverfolgung kann aktiviert werden, damit eine Anwendung während der Ausführung ihren Status überwachen kann. Weitere Informationen finden Sie im Thema Ablauf [Verfolgung](./tracing/index.md) . Informationen dazu, wie Sie die Ablauf Verfolgung zum Debuggen Ihrer Anwendung verwenden können, finden Sie im Thema Verwenden der Ablauf [Verfolgung zur Problembehandlung bei Ihrer Anwendung](./tracing/using-tracing-to-troubleshoot-your-application.md) .  
  
- Mit der Nachrichtenprotokollierung können Sie die Darstellung der Nachrichten vor und nach der Übertragung überprüfen. Weitere Informationen finden Sie im Thema [Nachrichten Protokollierung](message-logging.md) .  
  
- Die reignisablaufverfolgung schreibt Ereignisse für jeden Hauptaspekt in das Ereignisprotokoll. Sie können dann mit der Ereignisanzeige Anomalien untersuchen. Weitere Informationen finden Sie im Thema zur [Ereignisprotokollierung](./event-logging/index.md) .  
  
- Über den Systemmonitor verfügbar gemachte Leistungsindikatoren ermöglichen es Ihnen, die Anwendung und die Systemintegrität zu überwachen. Weitere Informationen finden Sie im Thema [Leistungsindikatoren](./performance-counters/index.md) .  
  
- Der <xref:System.ServiceModel.Configuration>-Namespace ermöglicht Ihnen das Laden von Konfigurationsdateien und die Einrichtung eines Diensts oder eines Clientendpunkts. Sie können das Objektmodell verwenden, um Änderungen auf viele Anwendungen anzuwenden, wenn Updates für diverse Computer durchgeführt werden müssen. Alternativ können Sie das- [Konfigurations-Editor-Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) verwenden, um die Konfigurationseinstellungen mithilfe eines GUI-Assistenten zu bearbeiten. Weitere Informationen finden Sie im Thema [Konfigurieren Ihrer Anwendung](configuring-your-application.md) .  
  
- Mit WMI können Sie ermitteln, welche Dienste auf einem Computer lauschen und welche Bindungen verwendet werden. Weitere Informationen finden Sie im Thema [Verwenden von Windows-Verwaltungsinstrumentation für die Diagnose](./wmi/index.md) .  
  
 WCF bietet außerdem verschiedene GUI-und Befehlszeilen Tools, die Ihnen das Erstellen, bereitstellen und Verwalten von WCF-Anwendungen erleichtern. Weitere Informationen finden Sie unter [Windows Communication Foundation Tools](../tools.md). Beispielsweise können Sie das- [Konfigurations-Editor-Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) verwenden, um WCF-Konfigurationseinstellungen zu erstellen und zu bearbeiten, indem Sie einen Assistenten verwenden, anstatt XML direkt zu bearbeiten. Sie können auch das [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) verwenden, um Ablauf Verfolgungs Meldungen anzuzeigen, zu gruppieren und zu filtern, sodass Sie Probleme mit WCF-Diensten diagnostizieren, reparieren und überprüfen können.  
  
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren der Anwendung](configuring-your-application.md)
- [Bereitstellen von Diensten](deploying-services.md)
- [Ausnahmen Referenz](./exceptions-reference/index.md)
- [Ereignisprotokollierung](./event-logging/index.md)
- [Nachrichtenprotokollierung](message-logging.md)
- [Configuration Editor-Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)
- [ServiceModel-Registrierungstool](servicemodel-registration-tool.md)
- [Ablaufverfolgung](./tracing/index.md)
- [Verwenden von Windows-Verwaltungsinstrumentation für die Diagnose](./wmi/index.md)
- [Leistungsindikatoren](./performance-counters/index.md)
- [Windows Communication Foundation-Tools](../tools.md)
