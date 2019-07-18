---
title: Liste der Aktivitäten
ms.date: 03/30/2017
ms.assetid: 5540e185-ce8e-4db3-83b0-2b9f5bf71829
ms.openlocfilehash: f96aab037e86b05096df7ffc82a0be3f6cce1ad2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998035"
---
# <a name="activity-list"></a>Liste der Aktivitäten
Dieses Thema enthält alle Aktivitäten, die von Windows Communication Foundation (WCF) definiert.  
  
> [!NOTE]
>  Sie können Aktivitäten auch programmgesteuert definieren, um Benutzerablaufverfolgungen zu gruppieren. Weitere Informationen finden Sie unter [Ausgeben von Benutzercode-Ablaufverfolgungen](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md).  
  
## <a name="servicemodel-activities"></a>ServiceModel-Aktivitäten  
 In der folgenden Tabelle werden alle Aktivitäten für die wichtigsten Verwendungsszenarien aufgeführt.  
  
|Bezeichnung|Name der Aktivität|Aktivitätstyp|Beschreibung|  
|-----------|-------------------|-------------------|-----------------|  
|A, M|Ambient-Aktivität|-/- (wird nicht über ServiceModel gesteuert)|Die Aktivität, deren ID in TLS festgelegt wird, bevor Aufrufe an ServiceModel-Code (client- oder serverseitig) stattfinden.<br /><br /> Beispiel: Wird aufgerufen, eine Aktivität, öffnen Sie auf dem WCF-Client oder serviceHost.open aufgerufen wird.|  
|B|Konstrukt<br /><br /> erstellen. Vertragstyp: "[Typ]".|Konstrukt||  
|C|Öffnen<br /><br /> [ClientBase&#124;ChannelFactory]. Vertragstyp: "[Typ]".|Öffnen||  
|I|Schließen [ClientBase&#124;ChannelFactory]. Vertragstyp: "[Typ]".|Schließen||  
|M|ServiceHost erstellen. ServiceType: "[Typ]".|Konstrukt||  
|N|ServiceHost öffnen. ServiceType: "[Typ]".|Öffnen||  
|Z|ServiceHost schließen. ServiceType: "[Typ]".|Schließen||  
|O|Abhören von "[Adresse]".|ListenAt|Diese und die folgende Aktivität sind transportspezifisch. Die ListenAt-Aktivität repräsentiert den Inhalt, der der Adresse zugeordnet wird, die vom Kanallistener abgehört wird. Im Fall von MSMQ ist dies die Warteschlange selbst, da die Warteschlange einer Adresse zugeordnet wird. Bei dieser Aktivität werden im Fall von verbindungsorientierten Transporten ankommende Verbindungen und im Fall von MSMQ MSMQ-Nachrichten abgehört. Diese Aktivität wird während ServiceHost.Open() erstellt. Sie enthält die Ablaufverfolgungen für die Erstellung und Entfernung des Listeners und überträgt an alle ReceiveBytes-Aktivitäten.|  
|P|Bytes auf Verbindung "[Adresse]" empfangen. MSMQ-Nachricht empfangen.|ReceiveBytes|In dieser Aktivität werden die Daten, die letztendlich eine WCF-Nachricht verarbeitet. Ankommende Bytes werden im Fall eines verbindungsorientierten Transports oder von HTTP erwartet. Bei TCP/Named Pipes (benannten Pipes) entspricht die Lebensdauer dieser Aktivität der Lebensdauer der Verbindung, da sie gemeinsam mit der Verbindung erstellt wird. Bei HTTP entspricht die Lebensdauer der Aktivität der Lebensdauer einer Nachrichtenanforderung. Sie wird beim Senden der Nachricht erstellt. Diese Aktivität enthält ggf. die Ablaufverfolgungen für die Erstellung und Entfernung der Verbindung und überträgt an alle Aktivitäten, die Nachrichten (Objekte) verarbeiten.<br /><br /> Im Fall von MSMQ ist dies die Aktivität, in der die MSMQ-Nachricht abgerufen wird.|  
|Q|Nachricht [Nummer] verarbeiten. (Hinweis: [Nummer] ist ein ausgehend von 1 kontinuierlich ansteigender Wert.)|ProcessMessage|Es wird eine ankommende Nachricht verarbeitet. Diese Aktivität beginnt, wenn alle Daten (Bytes, MSMQ-Nachricht) empfangen werden, um ein WCF-Nachrichtenobjekt zu erstellen. Die Ablaufverfolgungen in dieser Aktivität befassen sich mit der Headerverarbeitung.<br /><br /> Sobald eine verteilbare Nachricht gebildet wurde, wird zur ServiceHost-ProcessAction-Aktivität gewechselt, nachdem die entsprechende Aktivitäts-ID in Erfahrung gebracht wurde.|  
|D, S|Aktion "[Aktion]" verarbeiten.|ProcessAction|Die Nachricht wird über einen Transport-/Sicherheits-/RM-Stapel verarbeitet und bei Eingang bzw. Ausgang an Benutzercode verteilt.<br /><br /> Auf dem Server verwendet diese Aktivität die weitergegebene Aktivitäts-ID, wenn sie im Nachrichtenheader mittels "Aktivitätspropagierung" gesendet wird Andernfalls wird eine neue GUID erstellt.<br /><br /> Die Antwortnachricht wird bei Anforderung-/Antwortverträgen ebenfalls in dieser Aktivität verarbeitet.|  
|T|"[IContract.Operation]" ausführen.|ExecuteUserCode|Benutzercode wird dienstseitig nach dem Verteilen ausgeführt. Diese Aktivität stellt eine Grenze zwischen ServiceHost-Code und Benutzercode bereit.|  
  
## <a name="security-activities"></a>Sicherheitsaktivitäten  
 In der folgenden Tabelle werden alle sicherheitsbezogenen Aktivitäten aufgeführt.  
  
|Name der Aktivität|Aktivitätstyp|Beschreibung|  
|-------------------|-------------------|-----------------|  
|Sichere Sitzung einrichten|SetupSecurity|Nur clientseitig vorhanden. Enthält alle RST*-/SCT-Austauschvorgänge für die Authentifizierung und Einrichtung des Sicherheitskontexts. Wenn `propagateActivity` = `true`, diese Aktivität mit des Diensts die entsprechenden Prozess Aktion RST zusammengeführt\*/SCT Aktivitäten.|  
|Sichere Sitzung schließen|SetupSecurity|Clientseitig vorhanden. Enthält den "Cancel"-Nachrichtenaustausch zum Schließen der sicheren Sitzung. Wenn `propagateActivity` = `true`, diese Aktivität wird mit der Verarbeitungsaktion "Cancel" des Diensts zusammengeführt.|  
  
 In der folgenden Tabelle werden alle COM+-bezogenen Aktivitäten aufgeführt.  
  
|Name der Aktivität|Aktivitätstyp|Beschreibung|  
|-------------------|-------------------|-----------------|  
|COM+-Instanz erstellen|TransferToCOMPlus|für jede COM + 1 Aktivitätsinstanz Aufrufen von WCF-code|  
|Führen Sie die COM+- \<Vorgang >|TransferToCOMPlus|für jede COM + 1 Aktivitätsinstanz Aufrufen von WCF-code|  
  
## <a name="wmi-activities"></a>WMI-Aktivitäten  
 In der folgenden Tabelle werden alle WMI-bezogenen Aktivitäten aufgeführt.  
  
|Name der Aktivität|Aktivitätstyp|Beschreibung|  
|-------------------|-------------------|-----------------|  
|WMI-GET-Anforderung|WMIGetObject|Benutzer ruft Daten von WMI ab.|  
|WMI-PUT-Anforderung|WmiPutInstance|Benutzer aktualisiert Daten mit WMI.|
