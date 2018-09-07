---
title: Übersicht über die analytische Ablaufverfolgung
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: 9918f07d9c26c1779a1eedfbc423c31e61659334
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44070120"
---
# <a name="analytic-tracing-overview"></a>Übersicht über die analytische Ablaufverfolgung
Die analytische Ablaufverfolgung in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] ist eine Ablaufverfolgungsfunktion mit hoher Leistung und geringer Ausführlichkeit, die auf ETW (Ereignisablaufverfolgung für Windows) aufbaut. ETW wird auf Kernelebene ausgeführt, um den Mehraufwand durch Ablaufverfolgungsvorgänge so weit wie möglich zu reduzieren. Dabei werden Benutzer- und Kernelmodusereignisse auf effiziente Weise gepuffert, und das dynamische Aktivieren ist ohne Neustarts des Diensts möglich. Die Ablaufverfolgungsdaten sind in den Ereignisprotokollen verfügbar, nachdem sie ausgegeben und empfangen wurden.  
  
 Weitere Informationen zu ETW finden Sie unter [verbessertes Debugging und Leistungsoptimierung mit ETW](https://go.microsoft.com/fwlink/?LinkId=164781).  
  
 Zusätzlich zur Verwendung der Windows-Ereignisprotokolle für System, Sicherheit und Anwendung zum Analysieren der Anwendung wurden mit [!INCLUDE[wv](../../../../../includes/wv-md.md)] und [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] unter dem Knoten "Anwendungs- und Dienstprotokolle" der obersten Ebene zusätzliche Protokolle eingeführt. Der Zweck dieser neuen Protokolle ist das Speichern von Ereignissen für eine bestimmte Anwendung oder eine bestimmte Komponente anstelle von globalen Ereignissen, die systemweite Auswirkungen haben (z. B. der Typ von Ereignissen, die das Sicherheitsereignisprotokoll ggf. aufzeichnet). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] vereinheitlicht und korreliert die Protokollierung von WCF-Ablaufverfolgung-Ereignisse, Protokolle für WCF-Nachricht, und [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] Verfolgen der Datensätze mit den Anwendungs- und Dienstprotokolle.  
  
## <a name="concepts-and-capabilities"></a>Konzepte und Funktionen  
 Die folgenden Konzepte und Funktionen gelten für die WCF-analytische Ablaufverfolgung.  
  
### <a name="enabling-wcf-diagnostics-settings"></a>Aktivieren von WCF-Diagnoseeinstellungen  
 Die WCF-Diagnose aktiviert sind, in der \<system.serviceModel >\<Diagnose > Konfigurationsabschnitt.  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 Die WCF-Diagnoseeinstellungen für eine im Web gehostete virtuelle IIS-Anwendung werden in der dazugehörigen Web.config-Datei aktiviert. Eine andere Möglichkeit besteht darin, innerhalb der Anwendung in einem Unterverzeichnis eine Web.config-Datei zu erstellen.  Bei dieser Auswahl werden die Einstellungen auf alle Dienste innerhalb eines Unterverzeichnisses angewendet.  Um sicherzustellen, dass die Diagnoseeinstellungen innerhalb der Anwendung für alle Dienste gleich initialisiert werden, sollten sich diese Einstellungen im Anwendungsverzeichnis innerhalb der Datei „Web.config“ befinden, und nicht in einem der individuellen Unterverzeichnisse innerhalb der Anwendung.  
  
### <a name="channels"></a>Channels  
 ETW ermöglicht Softwarekomponenten mithilfe von Kanälen (Channels) das direkte Weiterleiten von Ereignissen an eine bestimmte Zielgruppe. Beispielsweise können Sie Ereignisse für Systemadministratoren an einen Kanal senden, und Ereignisse, die für Anwendungsentwickler wichtig sind, an einen anderen Kanal senden. Kanäle werden unter Windows benannt und registriert, damit Consumer die Ereignisse eines Kanals mithilfe der Ereignisanzeige anzeigen können.  
  
 Die analytische Ablaufverfolgungsfunktion für WCF in [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] schreibt in den Kanal Microsoft-Windows-Anwendungsserver-Anwendungen. Dieser Kanal ist insbesondere für Benutzer gedacht, die den Zustand des WCF-Dienste in der Produktion überwachen möchten. Es wird ein kleiner Satz von Ereignissen definiert, die in vielen Systemüberwachungs- und Problembehandlungsszenarios verwendet werden können.  
  
 Um Ereignisablaufverfolgung für ein Windows-Manifest zu aktivieren, damit Meldungen im Ereignisprotokoll ordnungsgemäß decodiert werden, verwenden Sie in der Befehlszeile das ServiceModelReg-Tool wie folgt:  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>Dynamische Konfiguration  
 Die ETW-Infrastruktur ermöglicht das dynamische Aktivieren und Konfigurieren der Ablaufverfolgung mit Windows-Standardtools. Weitere Informationen finden Sie unter [dynamisch das Aktivieren der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).  
  
### <a name="message-flow-tracing"></a>Ablaufverfolgung des Nachrichtenflusses  
 Weitere Informationen zum Aktivieren der Ablaufverfolgung des Nachrichtenflusses finden Sie unter [Configuring Message Flow Tracing](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md).  
  
### <a name="keywords"></a>Stichwörter  
 Schlüsselwörter werden verwendet, um Ablaufverfolgungsnachrichten zu filtern und zu definieren, welche Komponente von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] das Ereignis ausgegeben hat. Weitere Informationen finden Sie unter [dynamisch das Aktivieren der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).
