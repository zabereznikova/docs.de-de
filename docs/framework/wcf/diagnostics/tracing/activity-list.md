---
title: Liste der Aktivitäten
ms.date: 03/30/2017
ms.assetid: 5540e185-ce8e-4db3-83b0-2b9f5bf71829
ms.openlocfilehash: 8d43cc878d54efbd4908f92c3405bef2c7956f94
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602166"
---
# <a name="activity-list"></a>Liste der Aktivitäten
In diesem Thema werden alle durch Windows Communication Foundation (WCF) definierten Aktivitäten aufgelistet.  
  
> [!NOTE]
> Sie können Aktivitäten auch programmgesteuert definieren, um Benutzerablaufverfolgungen zu gruppieren. Weitere Informationen finden Sie unter ausgeben von [Benutzer Code-](emitting-user-code-traces.md)Ablauf Verfolgungen.  
  
## <a name="servicemodel-activities"></a>ServiceModel-Aktivitäten  
 In der folgenden Tabelle werden alle Aktivitäten für die wichtigsten Verwendungsszenarien aufgeführt.  
  
|Bezeichnung|Activity Name|Activity Type|BESCHREIBUNG|  
|-----------|-------------------|-------------------|-----------------|  
|A, M|Ambient-Aktivität|-/- (wird nicht über ServiceModel gesteuert)|Die Aktivität, deren ID in TLS festgelegt wird, bevor Aufrufe an ServiceModel-Code (client- oder serverseitig) stattfinden.<br /><br /> Beispiel: eine Aktivität, bei der Open auf dem WCF-Client oder Service Host. Open aufgerufen wird, wird aufgerufen.|  
|B|Konstrukt<br /><br /> erstellen. Vertragstyp: "[Typ]".|Konstrukt||  
|C|Öffnen<br /><br /> [ClientBase&#124;ChannelFactory]. Vertragstyp: "[Typ]".|Öffnen||  
|I|Schließen Sie [ClientBase&#124;ChannelFactory]. Vertragstyp: "[Typ]".|Schließen||  
|M|ServiceHost erstellen. ServiceType: "[Typ]".|Konstrukt||  
|N|ServiceHost öffnen. ServiceType: "[Typ]".|Öffnen||  
|Z|ServiceHost schließen. ServiceType: "[Typ]".|Schließen||  
|O|Abhören von "[Adresse]".|ListenAt|Diese und die folgende Aktivität sind transportspezifisch. Die ListenAt-Aktivität repräsentiert den Inhalt, der der Adresse zugeordnet wird, die vom Kanallistener abgehört wird. Im Fall von MSMQ ist dies die Warteschlange selbst, da die Warteschlange einer Adresse zugeordnet wird. Bei dieser Aktivität werden im Fall von verbindungsorientierten Transporten ankommende Verbindungen und im Fall von MSMQ MSMQ-Nachrichten abgehört. Diese Aktivität wird während ServiceHost.Open() erstellt. Sie enthält die Ablaufverfolgungen für die Erstellung und Entfernung des Listeners und überträgt an alle ReceiveBytes-Aktivitäten.|  
|P|Bytes auf Verbindung "[Adresse]" empfangen. MSMQ-Nachricht empfangen.|ReceiveBytes|In dieser Aktivität werden Daten, die letztendlich eine WCF-Nachricht erhalten, verarbeitet. Ankommende Bytes werden im Fall eines verbindungsorientierten Transports oder von HTTP erwartet. Bei TCP/Named Pipes (benannten Pipes) entspricht die Lebensdauer dieser Aktivität der Lebensdauer der Verbindung, da sie gemeinsam mit der Verbindung erstellt wird. Bei HTTP entspricht die Lebensdauer der Aktivität der Lebensdauer einer Nachrichtenanforderung. Sie wird beim Senden der Nachricht erstellt. Diese Aktivität enthält ggf. die Ablaufverfolgungen für die Erstellung und Entfernung der Verbindung und überträgt an alle Aktivitäten, die Nachrichten (Objekte) verarbeiten.<br /><br /> Im Fall von MSMQ ist dies die Aktivität, in der die MSMQ-Nachricht abgerufen wird.|  
|Q|Nachricht [Nummer] verarbeiten. (Hinweis: [Nummer] ist ein ausgehend von 1 kontinuierlich ansteigender Wert.)|ProcessMessage|Es wird eine ankommende Nachricht verarbeitet. Diese Aktivität beginnt, wenn alle Daten (Bytes, MSMQ-Nachricht) empfangen werden, um ein WCF-Nachrichten Objekt zu bilden. Die Ablaufverfolgungen in dieser Aktivität befassen sich mit der Headerverarbeitung.<br /><br /> Sobald eine verteilbare Nachricht gebildet wurde, wird zur ServiceHost-ProcessAction-Aktivität gewechselt, nachdem die entsprechende Aktivitäts-ID in Erfahrung gebracht wurde.|  
|D, S|Aktion "[Aktion]" verarbeiten.|ProcessAction|Die Nachricht wird über einen Transport-/Sicherheits-/RM-Stapel verarbeitet und bei Eingang bzw. Ausgang an Benutzercode verteilt.<br /><br /> Auf dem-Server verwendet diese Aktivität die propagierte Aktivitäts-ID, wenn Sie im Nachrichten Header über "Aktivitäts Propagierung" gesendet wird. Andernfalls wird eine neue GUID erstellt.<br /><br /> Die Antwortnachricht wird bei Anforderung-/Antwortverträgen ebenfalls in dieser Aktivität verarbeitet.|  
|T|"[IContract.Operation]" ausführen.|ExecuteUserCode|Benutzercode wird dienstseitig nach dem Verteilen ausgeführt. Diese Aktivität stellt eine Grenze zwischen ServiceHost-Code und Benutzercode bereit.|  
  
## <a name="security-activities"></a>Sicherheitsaktivitäten  
 In der folgenden Tabelle werden alle sicherheitsbezogenen Aktivitäten aufgeführt.  
  
|Activity Name|Activity Type|BESCHREIBUNG|  
|-------------------|-------------------|-----------------|  
|Sichere Sitzung einrichten|SetupSecurity|Nur clientseitig vorhanden. Enthält alle RST*-/SCT-Austauschvorgänge für die Authentifizierung und Einrichtung des Sicherheitskontexts. Wenn der Wert ist `propagateActivity` = `true` , wird diese Aktivität mit den entsprechenden Process Action RST/SCT-Aktivitäten des dienstangs zusammengeführt \* .|  
|Sichere Sitzung schließen|SetupSecurity|Clientseitig vorhanden. Enthält den "Cancel"-Nachrichtenaustausch zum Schließen der sicheren Sitzung. Wenn der Wert ist `propagateActivity` = `true` , wird diese Aktivität mit der Verarbeitungs Aktion "Cancel" aus dem Dienst zusammengeführt.|  
  
 In der folgenden Tabelle werden alle COM+-bezogenen Aktivitäten aufgeführt.  
  
|Activity Name|Activity Type|BESCHREIBUNG|  
|-------------------|-------------------|-----------------|  
|COM+-Instanz erstellen|TransferToCOMPlus|1 Aktivitäts Instanz für jeden com+-Befehl von WCF-Code|  
|Com+ ausführen\<operation>|TransferToCOMPlus|1 Aktivitäts Instanz für jeden com+-Befehl von WCF-Code|  
  
## <a name="wmi-activities"></a>WMI-Aktivitäten  
 In der folgenden Tabelle werden alle WMI-bezogenen Aktivitäten aufgeführt.  
  
|Activity Name|Activity Type|BESCHREIBUNG|  
|-------------------|-------------------|-----------------|  
|WMI-GET-Anforderung|WMIGetObject|Benutzer ruft Daten von WMI ab.|  
|WMI-PUT-Anforderung|WmiPutInstance|Benutzer aktualisiert Daten mit WMI.|
