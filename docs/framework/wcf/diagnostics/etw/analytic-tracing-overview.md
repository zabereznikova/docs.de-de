---
title: Übersicht über die analytische Ablaufverfolgung
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: f1a24e34375e98d4bfb48c1e2fd84290e08f6eea
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544749"
---
# <a name="analytic-tracing-overview"></a>Übersicht über die analytische Ablaufverfolgung
Die analytische Ablaufverfolgung in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] ist eine Ablaufverfolgungsfunktion mit hoher Leistung und geringer Ausführlichkeit, die auf ETW (Ereignisablaufverfolgung für Windows) aufbaut. ETW wird auf Kernelebene ausgeführt, um den Mehraufwand durch Ablaufverfolgungsvorgänge so weit wie möglich zu reduzieren. Dabei werden Benutzer- und Kernelmodusereignisse auf effiziente Weise gepuffert, und das dynamische Aktivieren ist ohne Neustarts des Diensts möglich. Die Ablaufverfolgungsdaten sind in den Ereignisprotokollen verfügbar, nachdem sie ausgegeben und empfangen wurden.  
  
 Weitere Informationen zu etw finden Sie unter verbessertes [Debugging und Leistungsoptimierung mit etw](https://go.microsoft.com/fwlink/?LinkId=164781).  
  
 Zusätzlich zur Verwendung der Windows-System-, Sicherheits-und Anwendungs Ereignisprotokolle zur Analyse der Anwendung wurden in Windows Vista und Windows Server 2008 weitere Protokolle unter dem Knoten der obersten Ebene der Anwendungs-und Dienst Protokolle eingeführt. Der Zweck dieser neuen Protokolle ist das Speichern von Ereignissen für eine bestimmte Anwendung oder eine bestimmte Komponente anstelle von globalen Ereignissen, die systemweite Auswirkungen haben (z. B. der Typ von Ereignissen, die das Sicherheitsereignisprotokoll ggf. aufzeichnet). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] vereinheitlicht und korreliert die Protokollierung von WCF-Ablauf Verfolgungs Ereignissen, WCF-Nachrichten Protokollen und [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] nach Verfolgungs Datensätzen mit den Anwendungs-und Dienst Protokollen.  
  
## <a name="concepts-and-capabilities"></a>Konzepte und Funktionen  
 Die folgenden Konzepte und Funktionen gelten für die analytische WCF-Ablauf Verfolgung.  
  
### <a name="enabling-wcf-diagnostics-settings"></a>Aktivieren von WCF-Diagnoseeinstellungen  
 Die WCF-Diagnose ist im Abschnitt \<System. Service Model >\<Diagnose > Konfiguration aktiviert.  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 Die WCF-Diagnoseeinstellungen für eine im Web gehostete virtuelle IIS-Anwendung werden in der dazugehörigen Web.config-Datei aktiviert. Eine andere Möglichkeit besteht darin, innerhalb der Anwendung in einem Unterverzeichnis eine Web.config-Datei zu erstellen.  Bei dieser Auswahl werden die Einstellungen auf alle Dienste innerhalb eines Unterverzeichnisses angewendet.  Um sicherzustellen, dass die Diagnoseeinstellungen innerhalb der Anwendung für alle Dienste gleich initialisiert werden, sollten sich diese Einstellungen im Anwendungsverzeichnis innerhalb der Datei „Web.config“ befinden, und nicht in einem der individuellen Unterverzeichnisse innerhalb der Anwendung.  
  
### <a name="channels"></a>Kanäle  
 ETW ermöglicht Softwarekomponenten mithilfe von Kanälen (Channels) das direkte Weiterleiten von Ereignissen an eine bestimmte Zielgruppe. Beispielsweise können Sie Ereignisse für Systemadministratoren an einen Kanal senden, und Ereignisse, die für Anwendungsentwickler wichtig sind, an einen anderen Kanal senden. Kanäle werden unter Windows benannt und registriert, damit Consumer die Ereignisse eines Kanals mithilfe der Ereignisanzeige anzeigen können.  
  
 Die analytische Ablauf Verfolgungs Funktion für WCF in [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] schreibt in den Channel Microsoft-Windows-Application-Server-Applications. Dieser Kanal wurde speziell für Benutzer entwickelt, die die Integrität der WCF-Dienste in der Produktionsumgebung überwachen möchten. Es wird ein kleiner Satz von Ereignissen definiert, die in vielen Systemüberwachungs- und Problembehandlungsszenarios verwendet werden können.  
  
 Um Ereignisablaufverfolgung für ein Windows-Manifest zu aktivieren, damit Meldungen im Ereignisprotokoll ordnungsgemäß decodiert werden, verwenden Sie in der Befehlszeile das ServiceModelReg-Tool wie folgt:  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>Dynamische Konfiguration  
 Die ETW-Infrastruktur ermöglicht das dynamische Aktivieren und Konfigurieren der Ablaufverfolgung mit Windows-Standardtools. Weitere Informationen finden Sie unter [dynamisches Aktivieren der analytischen Ablauf Verfolgung](dynamically-enabling-analytic-tracing.md).  
  
### <a name="message-flow-tracing"></a>Ablaufverfolgung des Nachrichtenflusses  
 Weitere Informationen zum Aktivieren der Ablauf Verfolgung für den Nachrichtenfluss finden Sie unter [Konfigurieren der Ablauf Verfolgung für den Nachrichtenfluss](configuring-message-flow-tracing.md).  
  
### <a name="keywords"></a>Stichwörter  
 Schlüsselwörter werden verwendet, um Ablauf Verfolgungs Meldungen zu filtern und zu definieren, welche Komponente des .NET Framework das Ereignis ausgegeben hat. Weitere Informationen finden Sie unter [dynamisches Aktivieren der analytischen Ablauf Verfolgung](dynamically-enabling-analytic-tracing.md).
