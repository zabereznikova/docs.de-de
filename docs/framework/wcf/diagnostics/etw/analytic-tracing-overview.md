---
title: "&#220;bersicht &#252;ber die analytische Ablaufverfolgung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Analytische Ablaufverfolgung [WCF], Übersicht"
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# &#220;bersicht &#252;ber die analytische Ablaufverfolgung
Die analytische Ablaufverfolgung in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] ist eine Ablaufverfolgungsfunktion mit hoher Leistung und geringer Ausführlichkeit, die auf ETW \(Ereignisablaufverfolgung für Windows\) aufbaut. ETW wird auf Kernelebene ausgeführt, um den Mehraufwand durch Ablaufverfolgungsvorgänge so weit wie möglich zu reduzieren. Dabei werden Benutzer\- und Kernelmodusereignisse auf effiziente Weise gepuffert, und das dynamische Aktivieren ist ohne Neustarts des Diensts möglich. Die Ablaufverfolgungsdaten sind in den Ereignisprotokollen verfügbar, nachdem sie ausgegeben und empfangen wurden.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] zu ETW finden Sie unter [Verbessertes Debugging und Leistungsoptimierung mit ETW](http://go.microsoft.com/fwlink/?LinkId=164781).  
  
 Zusätzlich zur Verwendung der Windows\-Ereignisprotokolle für System, Sicherheit und Anwendung zum Analysieren der Anwendung wurden mit [!INCLUDE[wv](../../../../../includes/wv-md.md)] und [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] unter dem Knoten "Anwendungs\- und Dienstprotokolle" der obersten Ebene zusätzliche Protokolle eingeführt. Der Zweck dieser neuen Protokolle ist das Speichern von Ereignissen für eine bestimmte Anwendung oder eine bestimmte Komponente anstelle von globalen Ereignissen, die systemweite Auswirkungen haben \(z. B. der Typ von Ereignissen, die das Sicherheitsereignisprotokoll ggf. aufzeichnet\).[!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] vereinheitlicht und korreliert die Protokollierung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Ablaufverfolgungsereignissen, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Nachrichtenprotokollen und [!INCLUDE[wf1](../../../../../includes/wf1-md.md)]\-Nachverfolgungsdatensätzen mit den Anwendungs\- und Dienstprotokollen.  
  
## Konzepte und Funktionen  
 Die folgenden Konzepte und Funktionen gelten für die analytische Ablaufverfolgung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].  
  
### Aktivieren von WCF\-Diagnoseeinstellungen  
 Die WCF\-Diagnose wird innerhalb des Konfigurationsabschnitts \<system.serviceModel\>\<diagnostics\> aktiviert.  
  
```  
  
<system.serviceModel>  
  <diagnostics>  
  
```  
  
 Die WCF\-Diagnoseeinstellungen für eine im Web gehostete virtuelle IIS\-Anwendung werden in der dazugehörigen Web.config\-Datei aktiviert. Eine andere Möglichkeit besteht darin, innerhalb der Anwendung in einem Unterverzeichnis eine Web.config\-Datei zu erstellen.  Bei dieser Auswahl werden die Einstellungen auf alle Dienste innerhalb eines Unterverzeichnisses angewendet.  Um sicherzustellen, dass die Diagnoseeinstellungen innerhalb der Anwendung für alle Dienste gleich initialisiert werden, sollten sich diese Einstellungen im Anwendungsverzeichnis innerhalb der Datei „Web.config“ befinden, und nicht in einem der individuellen Unterverzeichnisse innerhalb der Anwendung.  
  
### Channels  
 ETW ermöglicht Softwarekomponenten mithilfe von Kanälen \(Channels\) das direkte Weiterleiten von Ereignissen an eine bestimmte Zielgruppe. Beispielsweise können Sie Ereignisse für Systemadministratoren an einen Kanal senden, und Ereignisse, die für Anwendungsentwickler wichtig sind, an einen anderen Kanal senden. Kanäle werden unter Windows benannt und registriert, damit Consumer die Ereignisse eines Kanals mithilfe der Ereignisanzeige anzeigen können.  
  
 Die analytische Ablaufverfolgungsfunktion für [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] schreibt in den Kanal Microsoft\-Windows\-Application\-Server\-Applications. Dieser Kanal wurde speziell für Benutzer entworfen, die den Zustand der [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienste während der Produktion überwachen möchten. Es wird ein kleiner Satz von Ereignissen definiert, die in vielen Systemüberwachungs\- und Problembehandlungsszenarios verwendet werden können.  
  
 Um Ereignisablaufverfolgung für ein Windows\-Manifest zu aktivieren, damit Meldungen im Ereignisprotokoll ordnungsgemäß decodiert werden, verwenden Sie in der Befehlszeile das ServiceModelReg\-Tool wie folgt:  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### Dynamische Konfiguration  
 Die ETW\-Infrastruktur ermöglicht das dynamische Aktivieren und Konfigurieren der Ablaufverfolgung mit Windows\-Standardtools.[!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][Dynamisches Aktivieren der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).  
  
### Ablaufverfolgung des Nachrichtenflusses  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] zur Aktivierung der Ablaufverfolgung des Nachrichtenflusses finden Sie unter [Konfigurieren der Ablaufverfolgung des Nachrichtenflusses](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md).  
  
### Stichwörter  
 Schlüsselwörter werden verwendet, um Ablaufverfolgungsnachrichten zu filtern und zu definieren, welche Komponente von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] das Ereignis ausgegeben hat.[!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Dynamisches Aktivieren der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).