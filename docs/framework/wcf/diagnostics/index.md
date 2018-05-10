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
ms.openlocfilehash: c69d5681b186fdfae168ceea8b35f5786eaf02c9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="administration-and-diagnostics"></a>Verwaltung und Diagnose
Windows Communication Foundation (WCF) bietet einen umfangreichen Satz von Funktionen, mit die Sie die verschiedenen Phasen der Lebensdauer einer Anwendung überwachen können. Beispielsweise können Sie die Konfiguration verwenden, um Dienste und Clients bei der Bereitstellung einzurichten. WCF umfasst eine Reihe von Leistungsindikatoren zur Messung der Leistung Ihrer Anwendung. WCF macht auch inspektionsdaten eines Diensts zur Laufzeit über einen WCF (Windows Management Instrumentation, WMI)-Anbieter verfügbar. Trifft die Anwendung auf einen Fehler oder funktioniert die Anwendung nicht ordnungsgemäß, können Sie das Ereignisprotokoll nutzen, um festzustellen, ob etwas Schwerwiegendes eingetreten ist. Darüber hinaus können Sie die Nachrichtenprotokollierung und -ablaufverfolgung nutzen, um festzustellen, welche End-to-End-Ereignisse in Ihrer Anwendung stattfinden. Diese Funktionen unterstützen sowohl Entwickler und IT-Spezialisten eine WCF-Anwendung zu beheben, wenn es nicht ordnungsgemäß verhält.  
  
> [!NOTE]
>  Wenn Sie mit keine Detailinformationen für bestimmte Fehler empfangen, sollten Sie aktivieren die `includeExceptionDetailInFaults` Attribut von der [ \<ServiceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) Konfigurationselement. Dies weist WCF Ausnahmedetails an Clients gesendet, die Ihnen ermöglicht, viele gängige Probleme zu erkennen, ohne erweiterte Diagnosefunktionen einsetzen. Weitere Informationen finden Sie unter [senden und Empfangen von Fehlern](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Durch WCF bereitgestellte Diagnosefunktionen  
 WCF bietet die folgenden Diagnosefunktionen:  
  
-   End-To-End-Ablaufverfolgung bietet Instrumentierungsdaten für die Fehlerbehebung einer Anwendung ohne die Verwendung eines Debuggers. WCF gibt ablaufverfolgungen für verarbeitungsmeilensteine sowie Fehlermeldungen aus. Dies kann das Öffnen einer Kanalfactory oder das Senden und Empfangen von Nachrichten durch einen Diensthost einschließen. Die Ablaufverfolgung kann aktiviert werden, damit eine Anwendung während der Ausführung ihren Status überwachen kann. Weitere Informationen finden Sie unter der [Tracing](../../../../docs/framework/wcf/diagnostics/tracing/index.md) Thema. Um zu verstehen, wie Sie zum Debuggen Ihrer Anwendung verwenden können tracing, finden Sie unter der [mithilfe der Ablaufverfolgung an Ihre Anwendung beheben](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) Thema.  
  
-   Mit der Nachrichtenprotokollierung können Sie die Darstellung der Nachrichten vor und nach der Übertragung überprüfen. Weitere Informationen finden Sie unter der [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md) Thema.  
  
-   Die reignisablaufverfolgung schreibt Ereignisse für jeden Hauptaspekt in das Ereignisprotokoll. Sie können dann mit der Ereignisanzeige Anomalien untersuchen. Weitere Informationen finden Sie unter der [Ereignisprotokollierung](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) Thema.  
  
-   Über den Systemmonitor verfügbar gemachte Leistungsindikatoren ermöglichen es Ihnen, die Anwendung und die Systemintegrität zu überwachen. Weitere Informationen finden Sie unter der [Leistungsindikatoren](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) Thema.  
  
-   Der <xref:System.ServiceModel.Configuration>-Namespace ermöglicht Ihnen das Laden von Konfigurationsdateien und die Einrichtung eines Diensts oder eines Clientendpunkts. Sie können das Objektmodell verwenden, um Änderungen auf viele Anwendungen anzuwenden, wenn Updates für diverse Computer durchgeführt werden müssen. Alternativ können Sie die [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) so bearbeiten Sie die Konfigurationseinstellungen, die mit einem GUI-Assistenten. Weitere Informationen finden Sie unter der [Konfigurieren Ihrer Anwendung](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) Thema.  
  
-   Mit WMI können Sie ermitteln, welche Dienste auf einem Computer lauschen und welche Bindungen verwendet werden. Weitere Informationen finden Sie unter der [mithilfe von Windows-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md) Thema.  
  
 WCF bietet auch mehrere GUI und der Befehlszeilen-Tools zu erstellen, bereitstellen und Verwalten von WCF-Anwendungen vereinfachen. Weitere Informationen finden Sie unter [Windows Communication Foundation-Tools](../../../../docs/framework/wcf/tools.md). Beispielsweise können Sie die [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) erstellen und Bearbeiten von WCF-Konfigurationseinstellungen, die mithilfe eines Assistenten anstelle von XML-Code direkt bearbeiten. Sie können auch die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zum Anzeigen, gruppieren und Filtern von Ablaufverfolgungsnachrichten, sodass zu diagnostizieren, reparieren und prüfen Sie die Probleme mit WCF-Diensten.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren der Anwendung](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)  
 [Bereitstellen von Diensten](../../../../docs/framework/wcf/diagnostics/deploying-services.md)  
 [Ausnahmenreferenz](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)  
 [Ereignisprotokollierung](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md)  
 [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [ServiceModel-Registrierungstool](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)  
 [Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Windows-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md)  
 [Leistungsindikatoren](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)  
 [Windows Communication Foundation-Tools](../../../../docs/framework/wcf/tools.md)
