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
ms.openlocfilehash: 351d133215343e07e849ad1045eba601dd8cce56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797521"
---
# <a name="administration-and-diagnostics"></a>Verwaltung und Diagnose
Windows Communication Foundation (WCF) bietet einen umfangreichen Satz von Funktionen, mit die Sie die verschiedenen Phasen der Lebensdauer einer Anwendung überwachen können. Beispielsweise können Sie die Konfiguration verwenden, um Dienste und Clients bei der Bereitstellung einzurichten. WCF umfasst eine große Anzahl von Leistungsindikatoren können Sie die Leistung Ihrer Anwendung zu messen. WCF macht auch inspektionsdaten eines Diensts zur Laufzeit über einen WCF (Windows Management Instrumentation, WMI) Anbieter verfügbar. Trifft die Anwendung auf einen Fehler oder funktioniert die Anwendung nicht ordnungsgemäß, können Sie das Ereignisprotokoll nutzen, um festzustellen, ob etwas Schwerwiegendes eingetreten ist. Darüber hinaus können Sie die Nachrichtenprotokollierung und -ablaufverfolgung nutzen, um festzustellen, welche End-to-End-Ereignisse in Ihrer Anwendung stattfinden. Diese Features unterstützen sowohl Entwickler und IT-Experten, um eine WCF-Anwendung zu beheben, wenn es sich nicht richtig verhält.  
  
> [!NOTE]
>  Wenn Sie Fehler mit ohne einschlägige Detailinformationen erhalten, müssen Sie aktivieren die `includeExceptionDetailInFaults` Attribut der [ \<ServiceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) Konfigurationselement. Dies weist WCF Ausnahmedetail an Clients gesendet, der Sie viele gängige Probleme zu erkennen, ohne erweiterte Diagnosefunktionen einsetzen kann. Weitere Informationen finden Sie unter [Sending and Receiving Faults](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Durch WCF bereitgestellte Diagnosefunktionen  
 WCF stellt die folgenden Diagnosefunktionen bereit:  
  
- End-To-End-Ablaufverfolgung bietet Instrumentierungsdaten für die Fehlerbehebung einer Anwendung ohne die Verwendung eines Debuggers. WCF gibt ablaufverfolgungen für prozessmeilensteine sowie Fehlermeldungen aus. Dies kann das Öffnen einer Kanalfactory oder das Senden und Empfangen von Nachrichten durch einen Diensthost einschließen. Die Ablaufverfolgung kann aktiviert werden, damit eine Anwendung während der Ausführung ihren Status überwachen kann. Weitere Informationen finden Sie unter den [Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/index.md) Thema. Um zu verstehen, wie Sie Ablaufverfolgung verwenden können, Ihre Anwendung debuggen, finden Sie unter den [mithilfe der Ablaufverfolgung Ihrer Anwendung beheben](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) Thema.  
  
- Mit der Nachrichtenprotokollierung können Sie die Darstellung der Nachrichten vor und nach der Übertragung überprüfen. Weitere Informationen finden Sie unter den [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md) Thema.  
  
- Die reignisablaufverfolgung schreibt Ereignisse für jeden Hauptaspekt in das Ereignisprotokoll. Sie können dann mit der Ereignisanzeige Anomalien untersuchen. Weitere Informationen finden Sie unter den [Ereignisprotokollierung](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) Thema.  
  
- Über den Systemmonitor verfügbar gemachte Leistungsindikatoren ermöglichen es Ihnen, die Anwendung und die Systemintegrität zu überwachen. Weitere Informationen finden Sie unter den [Leistungsindikatoren](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) Thema.  
  
- Der <xref:System.ServiceModel.Configuration>-Namespace ermöglicht Ihnen das Laden von Konfigurationsdateien und die Einrichtung eines Diensts oder eines Clientendpunkts. Sie können das Objektmodell verwenden, um Änderungen auf viele Anwendungen anzuwenden, wenn Updates für diverse Computer durchgeführt werden müssen. Alternativ können Sie die [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) so bearbeiten Sie die Konfigurationseinstellungen mithilfe ein GUI-Assistenten. Weitere Informationen finden Sie unter den [Konfigurieren Ihrer Anwendung](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) Thema.  
  
- Mit WMI können Sie ermitteln, welche Dienste auf einem Computer lauschen und welche Bindungen verwendet werden. Weitere Informationen finden Sie unter den [mithilfe von Windows-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md) Thema.  
  
 WCF bietet auch verschiedene grafische Benutzeroberfläche und über die Befehlszeile für die Sie erstellen, bereitstellen und Verwalten von WCF-Anwendungen zu erleichtern. Weitere Informationen finden Sie unter [Verwaltungstools für Windows Communication Foundation](../../../../docs/framework/wcf/tools.md). Beispielsweise können Sie die [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) erstellen und Bearbeiten von WCF-Konfigurationseinstellungen mithilfe eines Assistenten anstatt XML-Code direkt bearbeiten. Sie können auch die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zum Anzeigen, gruppieren und Filtern von Ablaufverfolgungsnachrichten, damit Sie diagnostizieren, reparieren und prüfen Sie Probleme mit WCF-Diensten.  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren der Anwendung](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
- [Bereitstellen von Diensten](../../../../docs/framework/wcf/diagnostics/deploying-services.md)
- [Ausnahmenreferenz](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)
- [Ereignisprotokollierung](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md)
- [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [ServiceModel-Registrierungstool](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)
- [Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Windows-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md)
- [Leistungsindikatoren](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
- [Windows Communication Foundation-Tools](../../../../docs/framework/wcf/tools.md)
