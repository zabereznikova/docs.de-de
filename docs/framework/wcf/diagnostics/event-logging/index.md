---
title: Die Ereignisprotokollierung in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4028772caef8e5c0301ab3a6a0bde2f180d821ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="event-logging-in-wcf"></a>Die Ereignisprotokollierung in WCF
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] verfolgt interne Ereignisse im Windows-Ereignisprotokoll.  
  
## <a name="viewing-event-logs"></a>Anzeigen von Ereignisprotokollen  
 Die Ereignisprotokollierung wird standardmäßig automatisch aktiviert. Es gibt keinen Mechanismus, um sie zu deaktivieren. In [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] protokollierte Ereignisse können in der Ereignisanzeige angezeigt werden. Klicken Sie zum Starten dieses Tools auf **starten**, klicken Sie auf **Systemsteuerung**, doppelklicken Sie auf **Verwaltung**, und doppelklicken Sie dann auf **Ereignisanzeige**.  
  
### <a name="application-event-log"></a>Anwendungsereignisprotokoll  
 Die **Anwendungsereignisprotokoll** enthält die meisten von der generierte Ereignisse [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. Die meiste Einträge geben an, dass eine bestimmte Funktion für eine Anwendung nicht gestartet werden konnte. Beispiele:  
  
-   Nachrichtenprotokollierung/Ablaufverfolgung: [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] schreibt ein Ereignis in das Ereignisprotokoll, wenn die Ablaufverfolgung und Nachrichtenprotokollierung fehlschlägt. Nicht jeder Fehler der Ablaufverfolgung löst jedoch ein Ereignis aus. Damit das Ereignisprotokoll nicht vollständig mit Ablaufverfolgungsfehlern gefüllt wird, implementiert [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] eine 10-minütige Auszeit für solche Ereignisse. Das heißt, dass nachdem in [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ein Ablaufverfolgungsfehler in das Ereignisprotokoll geschrieben wurde, der nächste Fehler erst nach mindesten 10 Minuten aufgenommen wird.  
  
-   Freigegebene Listener: Der WCF TCP-Portfreigabedienst protokolliert ein Ereignis, wenn er nicht gestartet werden kann.  
  
-   [!INCLUDE[infocard](../../../../../includes/infocard-md.md)]: Ereignisse werden protokolliert, wenn der Dienst nicht gestartet werden kann.  
  
-   Schwerwiegende und Fehlerereignisse, wie Startfehler oder Abstürze  
  
-   Nachrichtenprotokollierung aktiviert: Ereignisse werden protokolliert, wenn die Nachrichtenprotokollierung aktiviert ist. Damit soll der Administrator informiert werden, dass sensible, anwendungsspezifische Informationen möglicherweise in Nachrichtenheadern und -texten protokolliert werden.  
  
-   Ein Ereignis wird protokolliert, wenn das `enableLoggingKnownPII`-Attribut im `machineSettings`-Element der Datei `machine.config` festgelegt ist. Dieses Attribut gibt an, ob eine Anwendung, die auf dem Computer ausgeführt wird, persönlich identifizierbare Informationen (Personally Identifiable Information, PII) protokollieren darf.  
  
-   Wenn das `logKnownPii`-Attribut in der Datei `app.config` oder der Datei `web.config` auf `true` für eine bestimmte Anwendung festgelegt ist, um die PII-Protokollierung zu aktivieren, jedoch das `enableLoggingKnownPII`-Attribut im `machineSettings`-Element der Datei `machine.config` auf `false` festgelegt ist, wird ein Ereignis protokolliert. Wenn `logKnownPii` und `enableLoggingKnownPII` auf `true` festgelegt sind, wird ebenfalls ein Ereignis protokolliert. Weitere Informationen zu diesen Konfigurationseinstellungen finden Sie unter der im Abschnitt Sicherheit die [Konfigurieren der Nachrichtenprotokollierung](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) Thema.  
  
### <a name="security-event-log"></a>Sicherheitsereignisprotokoll  
 Die **Sicherheitsereignisprotokoll** enthält Sicherheitsüberwachungsereignisse, die von WCF protokolliert werden.  
  
### <a name="system-event-log"></a>Systemereignisprotokoll  
 WCF protokolliert nichts die **Systemereignisprotokoll**.  
  
### <a name="event-log-entries"></a>Ereignisprotokolleinträge  
 Die **Quelle** eines Ereignisses wird der Name der Assembly, die den Protokolleintrag generiert.  
  
 Mit dem Typ eines Ereignisprotokolleintrags wird der Schweregrad eines Ereignisses angegeben. Jedes Ereignis muss von einem Typ sein, der von der Anwendung beim Melden des Ereignisses angegeben wird. Mithilfe dieses Typs wird von der Ereignisanzeige bestimmt, welches Symbol in der Listenansicht des Protokolls angezeigt werden soll. Informationen zu den verschiedenen Ereignistypen eines Ereignisprotokolleintrags finden Sie unter <xref:System.Diagnostics.EventLogEntryType>.  
  
 Beim Klicken auf "Weitere Informationen" Wenn Sie ein Ereignis in der Ereignisanzeige anzeigen, kann die Ereignisanzeige Informationen über das Internet senden. Weitere Informationen finden Sie in der Hilfe zur Ereignisanzeige.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Allgemeine Referenz zu Ereignissen](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
