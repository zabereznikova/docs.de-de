---
title: Die Ereignisprotokollierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
ms.openlocfilehash: 535b3570f41cbfb277eeb14fb07242b528acea46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236155"
---
# <a name="event-logging-in-wcf"></a>Die Ereignisprotokollierung in WCF

Windows Communication Foundation (WCF) verfolgt interne Ereignisse im Windows-Ereignisprotokoll.  
  
## <a name="viewing-event-logs"></a>Anzeigen von Ereignisprotokollen  

 Die Ereignisprotokollierung wird standardmäßig automatisch aktiviert. Es gibt keinen Mechanismus, um sie zu deaktivieren. Ereignisse, die von WCF protokolliert werden, können mit dem-Ereignisanzeige angezeigt werden. Um dieses Tool zu starten, klicken Sie auf **Start**, klicken Sie auf **Systemsteuerung**, doppelklicken Sie auf **Verwaltung**, und doppelklicken Sie dann auf **Ereignisanzeige**.  
  
### <a name="application-event-log"></a>Anwendungsereignisprotokoll  

 Das **Anwendungs Ereignisprotokoll** enthält die meisten von WCF generierten Ereignisse. Die meiste Einträge geben an, dass eine bestimmte Funktion für eine Anwendung nicht gestartet werden konnte. Beispiele:  
  
- Nachrichten Protokollierung/Ablauf Verfolgung: WCF schreibt ein Ereignis in das Ereignisprotokoll, wenn die Ablauf Verfolgung und Nachrichten Protokollierung fehlschlägt. Nicht jeder Fehler der Ablaufverfolgung löst jedoch ein Ereignis aus. Um zu verhindern, dass das Ereignisprotokoll vollständig mit Ablauf Verfolgungs Fehlern gefüllt wird, implementiert WCF einen 10-minütigen Blackout-Zeitraum für ein derartiges Ereignis. Dies bedeutet Folgendes: Wenn WCF einen Ablauf Verfolgungs Fehler in das Ereignisprotokoll schreibt, wird dies nicht für mindestens 10 Minuten wiederholt.  
  
- Freigegebene Listener: Der WCF TCP-Portfreigabedienst protokolliert ein Ereignis, wenn er nicht gestartet werden kann.  
  
- CardSpace: protokolliert Ereignisse, wenn der Dienst nicht gestartet werden kann.  
  
- Schwerwiegende und Fehlerereignisse, wie Startfehler oder Abstürze  
  
- Nachrichtenprotokollierung aktiviert: Ereignisse werden protokolliert, wenn die Nachrichtenprotokollierung aktiviert ist. Damit soll der Administrator informiert werden, dass sensible, anwendungsspezifische Informationen möglicherweise in Nachrichtenheadern und -texten protokolliert werden.  
  
- Ein Ereignis wird protokolliert, wenn das `enableLoggingKnownPII`-Attribut im `machineSettings`-Element der Datei `machine.config` festgelegt ist. Dieses Attribut gibt an, ob eine Anwendung, die auf dem Computer ausgeführt wird, persönlich identifizierbare Informationen (Personally Identifiable Information, PII) protokollieren darf.  
  
- Wenn das `logKnownPii`-Attribut in der Datei `app.config` oder der Datei `web.config` auf `true` für eine bestimmte Anwendung festgelegt ist, um die PII-Protokollierung zu aktivieren, jedoch das `enableLoggingKnownPII`-Attribut im `machineSettings`-Element der Datei `machine.config` auf `false` festgelegt ist, wird ein Ereignis protokolliert. Wenn `logKnownPii` und `enableLoggingKnownPII` auf `true` festgelegt sind, wird ebenfalls ein Ereignis protokolliert. Weitere Informationen zu diesen Konfigurationseinstellungen finden Sie im Abschnitt "Sicherheit" des Themas [Konfigurieren der Nachrichten Protokollierung](../configuring-message-logging.md) .  
  
### <a name="security-event-log"></a>Sicherheitsereignisprotokoll  

 Das **Sicherheits Ereignisprotokoll** enthält Sicherheits Überwachungs Ereignisse, die von WCF protokolliert werden.  
  
### <a name="system-event-log"></a>Systemereignisprotokoll  

 WCF protokolliert nichts im **System Ereignisprotokoll**.  
  
### <a name="event-log-entries"></a>Ereignisprotokolleinträge  

 Die **Quelle** eines Ereignisses ist der Name der Assembly, die den Protokolleintrag generiert.  
  
 Mit dem Typ eines Ereignisprotokolleintrags wird der Schweregrad eines Ereignisses angegeben. Jedes Ereignis muss von einem Typ sein, der von der Anwendung beim Melden des Ereignisses angegeben wird. Mithilfe dieses Typs wird von der Ereignisanzeige bestimmt, welches Symbol in der Listenansicht des Protokolls angezeigt werden soll. Informationen zu den verschiedenen Ereignistypen eines Ereignisprotokolleintrags finden Sie unter <xref:System.Diagnostics.EventLogEntryType>.  
  
 Wenn Sie auf "Weitere Informationen" klicken, wenn Sie ein Ereignis im Ereignisanzeige anzeigen, sendet der Ereignisanzeige möglicherweise Informationen über das Internet. Weitere Informationen finden Sie in der Hilfe zur Ereignisanzeige.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwaltung und Diagnose](../index.md)
- [Allgemeine Referenz zu Ereignissen](events-general-reference.md)
