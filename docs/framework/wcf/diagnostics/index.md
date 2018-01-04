---
title: Verwaltung und Diagnose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d26386a0669c92b1b21559474c8f5f61862e6de7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="administration-and-diagnostics"></a>Verwaltung und Diagnose
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet einen umfangreichen Satz an Funktionen, über die Sie die unterschiedlichen Phasen der Lebensdauer einer Anwendung überwachen können. Beispielsweise können Sie die Konfiguration verwenden, um Dienste und Clients bei der Bereitstellung einzurichten. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] beinhaltet einen umfangreichen Satz von Leistungsindikatoren zur Messung der Anwendungsleistung. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] macht außerdem zur Laufzeit über einen WMI (Windows Management Instrumentation)-Anbieter von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Inspektionsdaten eines Diensts verfügbar. Trifft die Anwendung auf einen Fehler oder funktioniert die Anwendung nicht ordnungsgemäß, können Sie das Ereignisprotokoll nutzen, um festzustellen, ob etwas Schwerwiegendes eingetreten ist. Darüber hinaus können Sie die Nachrichtenprotokollierung und -ablaufverfolgung nutzen, um festzustellen, welche End-to-End-Ereignisse in Ihrer Anwendung stattfinden. Diese Funktionen unterstützen sowohl Entwickler als auch IT-Profis bei der Fehlerbehebung einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendung im Falle von nicht ordnungsgemäßem Verhalten.  
  
> [!NOTE]
>  Wenn Sie mit keine Detailinformationen für bestimmte Fehler empfangen, sollten Sie aktivieren die `includeExceptionDetailInFaults` Attribut von der [ \<ServiceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) Konfigurationselement. Damit wird [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] angewiesen, den Clients nähere Angaben zu Ausnahmen zu senden. Dies ermöglicht es Ihnen, viele gängige Probleme zu erkennen, ohne erweiterte Diagnosefunktionen einsetzen zu müssen. Weitere Informationen finden Sie unter [senden und Empfangen von Fehlern](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Durch WCF bereitgestellte Diagnosefunktionen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt die folgenden Diagnosefunktionen bereit:  
  
-   End-To-End-Ablaufverfolgung bietet Instrumentierungsdaten für die Fehlerbehebung einer Anwendung ohne die Verwendung eines Debuggers. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-gibt Ablaufverfolgungen für Prozessmeilensteine sowie Fehlermeldungen aus. Dies kann das Öffnen einer Kanalfactory oder das Senden und Empfangen von Nachrichten durch einen Diensthost einschließen. Die Ablaufverfolgung kann aktiviert werden, damit eine Anwendung während der Ausführung ihren Status überwachen kann. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die [Tracing](../../../../docs/framework/wcf/diagnostics/tracing/index.md) Thema. Um zu verstehen, wie Sie zum Debuggen Ihrer Anwendung verwenden können tracing, finden Sie unter der [mithilfe der Ablaufverfolgung an Ihre Anwendung beheben](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) Thema.  
  
-   Mit der Nachrichtenprotokollierung können Sie die Darstellung der Nachrichten vor und nach der Übertragung überprüfen. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md) Thema.  
  
-   Die reignisablaufverfolgung schreibt Ereignisse für jeden Hauptaspekt in das Ereignisprotokoll. Sie können dann mit der Ereignisanzeige Anomalien untersuchen. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die [Ereignisprotokollierung](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) Thema.  
  
-   Über den Systemmonitor verfügbar gemachte Leistungsindikatoren ermöglichen es Ihnen, die Anwendung und die Systemintegrität zu überwachen. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die [Leistungsindikatoren](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) Thema.  
  
-   Der <xref:System.ServiceModel.Configuration>-Namespace ermöglicht Ihnen das Laden von Konfigurationsdateien und die Einrichtung eines Diensts oder eines Clientendpunkts. Sie können das Objektmodell verwenden, um Änderungen auf viele Anwendungen anzuwenden, wenn Updates für diverse Computer durchgeführt werden müssen. Alternativ können Sie die [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) so bearbeiten Sie die Konfigurationseinstellungen, die mit einem GUI-Assistenten. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die [Konfigurieren Ihrer Anwendung](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) Thema.  
  
-   Mit WMI können Sie ermitteln, welche Dienste auf einem Computer lauschen und welche Bindungen verwendet werden. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die [mithilfe von Windows-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md) Thema.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet darüber hinaus diverse GUI- und Befehlszeilentools, um Ihnen die Erstellung, Einbindung und Verwaltung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen zu erleichtern. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Windows Communication Foundation-Tools](../../../../docs/framework/wcf/tools.md). Beispielsweise können Sie die [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) zu erstellen und Bearbeiten von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Konfigurationseinstellungen mithilfe ein Assistenten anstelle von XML-Code direkt bearbeiten. Sie können auch die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zum Anzeigen, gruppieren und Filtern von Ablaufverfolgungsnachrichten, sodass zu diagnostizieren, reparieren und prüfen Sie die Probleme mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienste.  
  
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
