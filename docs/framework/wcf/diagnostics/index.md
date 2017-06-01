---
title: "Verwaltung und Diagnose | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Verwaltung [WCF]"
  - "Diagnose [WCF]"
  - "WCF, Verwaltung"
  - "WCF, Diagnose"
  - "Windows Communication Foundation, Verwaltung"
  - "Windows Communication Foundation, Diagnose"
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Verwaltung und Diagnose
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet einen umfangreichen Satz an Funktionen, über die Sie die unterschiedlichen Phasen der Lebensdauer einer Anwendung überwachen können.Beispielsweise können Sie die Konfiguration verwenden, um Dienste und Clients bei der Bereitstellung einzurichten.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] beinhaltet einen umfangreichen Satz von Leistungsindikatoren zur Messung der Anwendungsleistung.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] macht zur Laufzeit Inspektionsdaten eines Diensts über einen Windows\-Verwaltungsinstrumentation außerdem \(WMI\)\-Anbieter von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verfügbar.Trifft die Anwendung auf einen Fehler oder funktioniert die Anwendung nicht ordnungsgemäß, können Sie das Ereignisprotokoll nutzen, um festzustellen, ob etwas Schwerwiegendes eingetreten ist.Darüber hinaus können Sie die Nachrichtenprotokollierung und \-ablaufverfolgung nutzen, um festzustellen, welche End\-to\-End\-Ereignisse in Ihrer Anwendung stattfinden.Diese Funktionen unterstützen sowohl Entwickler als auch IT\-Profis bei der Fehlerbehebung einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung im Falle von nicht ordnungsgemäßem Verhalten.  
  
> [!NOTE]
>  Wenn Sie Fehler ohne einschlägige Detailinformationen erhalten, sollten Sie das `includeExceptionDetailInFaults`\-Attribut des [\<serviceDebug\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)\-Konfigurationselements aktivieren.Damit wird [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] angewiesen, den Clients nähere Angaben zu Ausnahmen zu senden. Dies ermöglicht es Ihnen, viele gängige Probleme zu erkennen, ohne erweiterte Diagnosefunktionen einsetzen zu müssen.Weitere Informationen finden Sie unter [Senden und Empfangen von Fehlern](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## Durch WCF bereitgestellte Diagnosefunktionen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt die folgenden Diagnosefunktionen bereit:  
  
-   End\-To\-End\-Ablaufverfolgung bietet Instrumentationsdaten für die Fehlerbehebung einer Anwendung ohne die Verwendung eines Debuggers.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Ausgaben verfolgen Prozessmeilensteine sowie Fehlernachrichten.Dies kann das Öffnen einer Kanalfactory oder das Senden und Empfangen von Nachrichten durch einen Diensthost einschließen.Ablaufverfolgung kann aktiviert werden, damit eine laufende Anwendung ihren Status überwachen kann.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem folgenden Thema: [Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/index.md).Informationen dazu, wie Sie die Ablaufverfolgung für das Debugging Ihrer Anwendung verwenden können, finden Sie unter [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).  
  
-   Über Nachrichtenprotokollierung können Sie einsehen, wie Nachrichten sowohl vor als auch nach der Übertragung aussehen.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem folgenden Thema: [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md).  
  
-   Die reignisablaufverfolgung schreibt Ereignisse für jeden Hauptaspekt in das Ereignisprotokoll.Sie können dann Anomalien über die Ereignisanzeige prüfen.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem folgenden Thema: [Ereignisprotokollierung](../../../../docs/framework/wcf/diagnostics/event-logging/index.md).  
  
-   Durch Performance Monitor offengelegte Leistungsindikatoren ermöglichen es Ihnen, Ihre Anwendung und die Systemgesundheit zu überwachen.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem folgenden Thema: [Leistungsindikatoren](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md).  
  
-   Der <xref:System.ServiceModel.Configuration>\-Namespace ermöglicht Ihnen das Laden von Konfigurationsdateien und die Einrichtung eines Diensts oder eines Clientendpunkts.Sie können das Objektmodell verwenden, um Änderungen auf viele Anwendungen anzuwenden, wenn Updates für diverse Computer durchgeführt werden müssen.Alternativ können Sie [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) nutzen, um Konfigurationseinstellungen mithilfe eines GUI\-Assistenten zu bearbeiten.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem folgenden Thema: [Konfigurieren der Anwendung](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md).  
  
-   WMI ermöglicht es Ihnen, herauszufinden, welche Dienste auf dem Computer überwachen und welche Bindungen verwendet werden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem folgenden Thema: [Verwenden der Windows\-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet darüber hinaus diverse GUI\- und Befehlszeilentools, um Ihnen die Erstellung, Einbindung und Verwaltung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen zu erleichtern.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Windows Communication Foundation\-Tools](../../../../docs/framework/wcf/tools.md).Beispielsweise können Sie das [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) nutzen, um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Konfigurationseinstellungen mithilfe eines Assistenten anstatt direkt in XML zu erstellen und zu bearbeiten.Darüber hinaus können Sie [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) nutzen, um Ablaufverfolgungsnachrichten einzusehen, zu gruppieren und zu filtern, sodass Sie alle Probleme bei [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten diagnostizieren, reparieren und prüfen können.  
  
## Siehe auch  
 [Konfigurieren der Anwendung](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)   
 [Bereitstellen von Diensten](../../../../docs/framework/wcf/diagnostics/deploying-services.md)   
 [Ausnahmenreferenz](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)   
 [Ereignisprotokollierung](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md)   
 [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)   
 [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)   
 [ServiceModel\-Registrierungstool](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)   
 [Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Windows\-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md)   
 [Leistungsindikatoren](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)   
 [Windows Communication Foundation\-Tools](../../../../docs/framework/wcf/tools.md)