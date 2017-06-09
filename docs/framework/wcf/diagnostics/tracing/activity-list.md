---
title: "Liste der Aktivit&#228;ten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5540e185-ce8e-4db3-83b0-2b9f5bf71829
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Liste der Aktivit&#228;ten
In diesem Thema werden alle von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] definierten Aktivitäten aufgeführt.  
  
> [!NOTE]
>  Sie können Aktivitäten auch programmgesteuert definieren, um Benutzerablaufverfolgungen zu gruppieren.Weitere Informationen finden Sie unter [Ausgeben von Benutzercode\-Ablaufverfolgungen](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md).  
  
## ServiceModel\-Aktivitäten  
 In der folgenden Tabelle werden alle Aktivitäten für die wichtigsten Verwendungsszenarien aufgeführt.  
  
|Bezeichnung|Name der Aktivität|Aktivitätstyp|Beschreibung|  
|-----------------|------------------------|-------------------|------------------|  
|A, M|Ambient\-Aktivität|\-\/\- \(wird nicht über ServiceModel gesteuert\)|Die Aktivität, deren ID in TLS festgelegt wird, bevor Aufrufe an ServiceModel\-Code \(client\- oder serverseitig\) stattfinden.<br /><br /> Beispiel: Eine Aktivität, bei der "open" auf dem [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Client oder "serviceHost.open" aufgerufen wird.|  
|B|Construct<br /><br /> erstellen.Vertragstyp: "\[Typ\]".|Construct||  
|C|Open<br /><br /> öffnen.Vertragstyp: "\[Typ\]".|Open||  
|I|\[ClientBase&#124;ChannelFactory\] schließen.Vertragstyp: "\[Typ\]".|Close||  
|M|ServiceHost erstellen.ServiceType: "\[Typ\]".|Construct||  
|N|ServiceHost öffnen.ServiceType: "\[Typ\]".|Öffnen Sie .||  
|Z|ServiceHost schließen.ServiceType: "\[Typ\]".|Close||  
|O|Lauschen von "\[Adresse\]".|ListenAt|Diese und die folgende Aktivität sind transportspezifisch.Die ListenAt\-Aktivität repräsentiert den Inhalt, der der Adresse zugeordnet wird, die vom Kanallistener abgehört wird.Im Fall von MSMQ ist dies die Warteschlange selbst, da die Warteschlange einer Adresse zugeordnet wird.Bei dieser Aktivität werden im Fall von verbindungsorientierten Transporten ankommende Verbindungen und im Fall von MSMQ MSMQ\-Nachrichten abgehört.Diese Aktivität wird während ServiceHost.Open\(\) erstellt. Sie enthält die Ablaufverfolgungen für die Erstellung und Entfernung des Listeners und überträgt an alle ReceiveBytes\-Aktivitäten.|  
|P|Bytes auf Verbindung "\[Adresse\]" empfangen.MSMQ\-Nachricht empfangen.|ReceiveBytes|Bei dieser Aktivität werden Daten, die letztendlich eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Nachricht empfangen, verarbeitet.Ankommende Bytes werden im Fall eines verbindungsorientierten Transports oder von HTTP erwartet.Bei TCP\/Named Pipes \(benannten Pipes\) entspricht die Lebensdauer dieser Aktivität der Lebensdauer der Verbindung, da sie gemeinsam mit der Verbindung erstellt wird.Bei HTTP entspricht die Lebensdauer der Aktivität der Lebensdauer einer Nachrichtenanforderung. Sie wird beim Senden der Nachricht erstellt.Diese Aktivität enthält ggf. die Ablaufverfolgungen für die Erstellung und Entfernung der Verbindung und überträgt an alle Aktivitäten, die Nachrichten \(Objekte\) verarbeiten.<br /><br /> Im Fall von MSMQ ist dies die Aktivität, in der die MSMQ\-Nachricht abgerufen wird.|  
|Q|Nachricht \[Nummer\] verarbeiten.\(Hinweis: \[Nummer\] ist ein ausgehend von 1 kontinuierlich ansteigender Wert.\)|ProcessMessage|Es wird eine ankommende Nachricht verarbeitet.Diese Aktivität beginnt, wenn alle Daten \(Bytes, MSMQ\-Nachricht\) empfangen wurden und diese ein [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Nachrichtenobjekt bilden.Die Ablaufverfolgungen in dieser Aktivität befassen sich mit der Headerverarbeitung.<br /><br /> Sobald eine verteilbare Nachricht gebildet wurde, wird zur ServiceHost\-ProcessAction\-Aktivität gewechselt, nachdem die entsprechende Aktivitäts\-ID in Erfahrung gebracht wurde.|  
|D, S|Aktion "\[Aktion\]" verarbeiten.|ProcessAction|Die Nachricht wird über einen Transport\-\/Sicherheits\-\/RM\-Stapel verarbeitet und bei Eingang bzw. Ausgang an Benutzercode verteilt.<br /><br /> Auf dem Server verwendet diese Aktivität die weitergegebene Aktivitäts\-ID, sofern diese im Nachrichtenheader mittels "Aktivitätspropagierung" gesendet wurde. Andernfalls wird eine neue GUID erstellt.<br /><br /> Die Antwortnachricht wird bei Anforderung\-\/Antwortverträgen ebenfalls in dieser Aktivität verarbeitet.|  
|T|"\[IContract.Operation\]" ausführen.|ExecuteUserCode|Benutzercode wird dienstseitig nach dem Verteilen ausgeführt.Diese Aktivität stellt eine Grenze zwischen ServiceHost\-Code und Benutzercode bereit.|  
  
## Sicherheitsaktivitäten  
 In der folgenden Tabelle werden alle sicherheitsbezogenen Aktivitäten aufgeführt.  
  
|Name der Aktivität|Aktivitätstyp|Beschreibung|  
|------------------------|-------------------|------------------|  
|Sichere Sitzung einrichten|SetupSecurity|Nur clientseitig vorhanden.Enthält alle RST\*\-\/SCT\-Austauschvorgänge für die Authentifizierung und Einrichtung des Sicherheitskontexts.Falls `propagateActivity` auf `true` gesetzt ist, wird diese Aktivität mit den entsprechenden RST\*\-\/SCT\-Verarbeitungsaktionsaktivitäten des Diensts zusammengeführt.|  
|Sichere Sitzung schließen|SetupSecurity|Clientseitig vorhanden.Enthält den "Cancel"\-Nachrichtenaustausch zum Schließen der sicheren Sitzung.Falls `propagateActivity` auf `true` gesetzt ist, wird diese Aktivität mit der Verarbeitungsaktion "Cancel" des Diensts zusammengeführt.|  
  
 In der folgenden Tabelle werden alle COM\+\-bezogenen Aktivitäten aufgeführt.  
  
|Name der Aktivität|Aktivitätstyp|Beschreibung|  
|------------------------|-------------------|------------------|  
|COM\+\-Instanz erstellen|TransferToCOMPlus|Eine Aktivitätsinstanz pro COM\+\-Aufruf über [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Code|  
|COM\+\-\<Vorgang\> ausführen|TransferToCOMPlus|Eine Aktivitätsinstanz pro COM\+\-Aufruf über [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Code|  
  
## WMI\-Aktivitäten  
 In der folgenden Tabelle werden alle WMI\-bezogenen Aktivitäten aufgeführt.  
  
|Name der Aktivität|Aktivitätstyp|Beschreibung|  
|------------------------|-------------------|------------------|  
|WMI\-GET\-Anforderung|WMIGetObject|Benutzer ruft Daten von WMI ab.|  
|WMI\-PUT\-Anforderung|WmiPutInstance|Benutzer aktualisiert Daten mit WMI.|