---
title: Aktivitätsablaufverfolgung in der Nachrichtensicherheit
ms.date: 03/30/2017
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
ms.openlocfilehash: 65b2842c57da8e17c7280a2becd755ba2aae8364
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656450"
---
# <a name="activity-tracing-in-message-security"></a>Aktivitätsablaufverfolgung in der Nachrichtensicherheit
In diesem Thema wird die Aktivitätsablaufverfolgung für die Sicherheitsverarbeitung beschrieben, die in den folgenden drei Phasen erfolgt.  
  
- Aushandlung/SCT-Austausch. Das kann später auf der Transportebene stattfinden (über binären Datenaustausch) oder auf der Nachrichtenebene (über SOAP-Nachrichtenaustausch).  
  
- Nachrichtenverschlüsselung/-entschlüsselung mit Signaturüberprüfung und Authentifizierung. Ablaufverfolgungen werden in der Umgebungsaktivität, in der Regel "Aktion verarbeiten", angezeigt.  
  
- Autorisierung und Überprüfung. Dies kann lokal geschehen oder bei der Kommunikation zwischen Endpunkten.  
  
## <a name="negotiationsct-exchange"></a>Aushandlung/SCT-Austausch  
 In der Phase Aushandlung/SCT Exchange werden zwei Aktivitätstypen auf dem Client erstellt: "Sicherheitssitzung einrichten" und "Sicherheitssitzung schließen." "Sicherheitssitzung einrichten" umfasst die Ablaufverfolgung für den RST/RSTR/SCT-Nachrichtenaustausch, während "Sicherheitssitzung schließen" die Ablaufverfolgung der Cancel-Nachricht einschließt.  
  
 Auf dem Server wird jede Anforderung/Antwort zu RST/RSTR/SCT in einer eigenen Aktivität angezeigt. Wenn `propagateActivity` = `true` auf dem Server und Client Aktivitäten auf dem Server dieselbe ID haben, und in der "Sicherheitssitzung einrichten" bei der Anzeige über Service Trace Viewer zusammen angezeigt werden.  
  
 Dieses Aktivitätsablaufverfolgungsmodell ist bei der Benutzernamen-/Kennwortauthentifizierung, der Zertifikatsauthentifizierung und der NTLM-Authentifizierung wirksam.  
  
 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Aushandlung und den SCT-Austausch aufgeführt.  
  
||Zeitpunkt von Aushandlung-/SCT-Austausch|Aktivitäten|Ablaufverfolgungen|  
|-|-------------------------------------------------|----------------|------------|  
|Sicherer Transport<br /><br /> (HTTPS, SSL)|Bei der ersten empfangenen Nachricht.|Ablaufverfolgungen werden in der Umgebungsaktivität ausgegeben.|-Ablaufverfolgungen zu Austauschinformationen<br />– Sicherer Kanal wurde hergestellt<br />-Geheime Schlüssel wurden abgerufen.|  
|Sichere Nachrichtenebene<br /><br /> (WSHTTP)|Bei der ersten empfangenen Nachricht.|Auf dem Client:<br /><br /> -"Sicherheitssitzung einrichten" aus "Aktion verarbeiten" dieser ersten Nachricht, für jede Anforderung/Antwort zu RST/RSTR/SCT.<br />-"Sicherheitssitzung schließen" für die CANCEL-Austausch aus der Aktivität"Proxy schließen." Diese Aktivität kann aus einer anderen Umgebungsaktivität erfolgen, je nachdem, wann die Sicherheitssitzung geschlossen wird.<br /><br /> Auf dem Server:<br /><br /> -Eine "Aktion verarbeiten"-Aktivität für jede Anforderung/Antwort zu RST/SCT/Cancel auf dem Server. Wenn `propagateActivity` = `true`RST/RSTR/SCT-Aktivitäten werden zusammengeführt, mit "Sicherheitssitzung einrichten" und "Abbrechen" ist mit der Aktivität "Schließen" auf dem Client zusammengeführt.<br /><br /> "Sicherheitssitzung einrichten" erfolgt in zwei Stufen:<br /><br /> 1.  Aushandlung der Authentifizierung. Dies ist optional, wenn der Client bereits über die richtigen Anmeldeinformationen verfügt. Diese Stufe kann über den sicheren Transport oder über den Nachrichtenaustausch erfolgen. In letzterem Fall, kann der RST-/RSTR-Austausch ein- oder zweimal stattfinden. Bei diesem Austausch werden Ablaufverfolgungen in neuen zuvor entworfenen Anforderungs-/Antwortaktivitäten ausgegeben.<br />2.  Einrichtung der Sicherheitssitzung (SCT), wobei ein RST/RSTR-Austausch erfolgt. Dieser weist dieselben, bereits beschriebenen Umgebungsaktivitäten auf.|-Ablaufverfolgungen zu Austauschinformationen<br />– Sicherer Kanal wurde hergestellt<br />-Geheime Schlüssel wurden abgerufen.|  
  
> [!NOTE]
>  Im gemischten Sicherheitsmodus erfolgt die Aushandlung der Authentifizierung in einem binären Austausch, SCT erfolgt jedoch im Nachrichtenaustausch. Im reinen Transportmodus findet die Aushandlung nur beim Transport ohne weitere Aktivitäten statt.  
  
## <a name="message-encryption-and-decryption"></a>Nachrichtenverschlüsselung und -entschlüsselung  
 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Verschlüsselung/Entschlüsselung von Nachrichten und die Signaturauthentifizierung aufgeführt.  
  
||Sicherer Transport<br /><br /> (HTTPS, SSL) und sichere Nachrichtenebene<br /><br /> (WSHTTP)|  
|-|---------------------------------------------------------------------------------|  
|Zeitpunkt der Nachrichtenverschlüsselung/-entschlüsselung sowie der Signatur als Nachricht Verschlüsselung/Entschlüsselung sowie die Signaturauthentifizierung|Beim Empfang der Nachricht|  
|Aktivitäten|Ablaufverfolgungen werden in der Aktivität "Aktion verarbeiten" auf dem Client und dem Server ausgegeben.|  
|Ablaufverfolgungen|-SendSecurityHeader (Absender):<br />: Nachricht signieren<br />-Verschlüsseln der Anforderungsdaten<br />-ReceiveSecurityHeader (Empfänger):<br />: Überprüfen der Signatur<br />-Entschlüsseln der Antwortdaten<br />-Authentifizierung|  
  
> [!NOTE]
>  Im reinen Transportmodus findet die Verschlüsselung/Entschlüsselung nur beim Transport ohne weitere Aktivitäten statt.  
  
## <a name="authorization-and-verification"></a>Autorisierung und Überprüfung.  
 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Autorisierung aufgeführt.  
  
||Zeitpunkt der Autorisierung|Aktivitäten|Ablaufverfolgungen|  
|-|-------------------------------------|----------------|------------|  
|Lokal (Standard)|Nachdem die Nachricht auf den Server entschlüsselt wurde.|Ablaufverfolgungen werden in der Aktivität "Aktion verarbeiten" auf dem Server ausgegeben.|Für Benutzer autorisiert.|  
|Remoteelement|Nachdem die Nachricht auf den Server entschlüsselt wurde.|Ablaufverfolgungen werden in einer neuen von der Aktivität "Aktion verarbeiten" aufgerufenen Aktivität ausgegeben.|Für Benutzer autorisiert.|
