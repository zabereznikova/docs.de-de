---
title: Die Ereignisprotokollierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
ms.openlocfilehash: ea0e6f3dc66bf40d631077c0dce20ea46f3a6688
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="event-logging-in-wcf"></a>Die Ereignisprotokollierung in WCF
Windows Communication Foundation (WCF) verfolgt interne Ereignisse im Windows-Ereignisprotokoll.  
  
## <a name="viewing-event-logs"></a>Anzeigen von Ereignisprotokollen  
 Die Ereignisprotokollierung wird standardmäßig automatisch aktiviert. Es gibt keinen Mechanismus, um sie zu deaktivieren. Ereignisse, die von WCF protokolliert werden, können mithilfe der Ereignisanzeige angezeigt werden. Klicken Sie zum Starten dieses Tools auf **starten**, klicken Sie auf **Systemsteuerung**, doppelklicken Sie auf **Verwaltung**, und doppelklicken Sie dann auf **Ereignisanzeige**.  
  
### <a name="application-event-log"></a>Anwendungsereignisprotokoll  
 Die **Anwendungsereignisprotokoll** enthält die meisten der vom WCF generierte Ereignisse. Die meiste Einträge geben an, dass eine bestimmte Funktion für eine Anwendung nicht gestartet werden konnte. Beispiele:  
  
-   Nachrichtenprotokollierung/Ablaufverfolgung: Bei WCF schreibt ein Ereignis in das Ereignisprotokoll geschrieben, wenn die Ablaufverfolgung und nachrichtenprotokollierung fehlschlägt. Nicht jeder Fehler der Ablaufverfolgung löst jedoch ein Ereignis aus. Um zu verhindern, dass das Ereignisprotokoll vollständig mit ablaufverfolgungsfehlern gefüllt wird, implementiert WCF ein 10-minütigen Auszeit für solche Ereignisse. Dies bedeutet, dass wenn WCF einen Fehler in das Ereignisprotokoll schreibt, es daher erneut auf mindestens 10 Minuten nicht vorgesehen ist.  
  
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
