---
title: Aktivitätsablaufverfolgung in der Nachrichtensicherheit
ms.date: 03/30/2017
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
ms.openlocfilehash: 4ab34e3a3ef8487a747c9f9dac71a22006ea515a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265010"
---
# <a name="activity-tracing-in-message-security"></a>Aktivitätsablaufverfolgung in der Nachrichtensicherheit

In diesem Thema wird die Aktivitätsablaufverfolgung für die Sicherheitsverarbeitung beschrieben, die in den folgenden drei Phasen erfolgt.  
  
- Aushandlung/SCT-Austausch. Das kann später auf der Transportebene stattfinden (über binären Datenaustausch) oder auf der Nachrichtenebene (über SOAP-Nachrichtenaustausch).  
  
- Nachrichtenverschlüsselung/-entschlüsselung mit Signaturüberprüfung und Authentifizierung. Ablaufverfolgungen werden in der Umgebungsaktivität, in der Regel "Aktion verarbeiten", angezeigt.  
  
- Autorisierung und Überprüfung. Dies kann lokal geschehen oder bei der Kommunikation zwischen Endpunkten.  
  
## <a name="negotiationsct-exchange"></a>Aushandlung/SCT-Austausch  

 In der Phase Aushandlung/SCT-Austausch werden zwei Aktivitätstypen auf dem Client erstellt: "Sicherheitssitzung einrichten" und "Sicherheitssitzung schließen". "Sicherheitssitzung einrichten" umfasst die Ablaufverfolgung für den RST/RSTR/SCT-Nachrichtenaustausch, während "Sicherheitssitzung schließen" die Ablaufverfolgung der Cancel-Nachricht einschließt.  
  
 Auf dem Server wird jede Anforderung/Antwort zu RST/RSTR/SCT in einer eigenen Aktivität angezeigt. Wenn `propagateActivity` = `true` sowohl auf dem Server als auch auf dem Client die gleiche ID auf dem Server vorhanden ist und Sie in der "sicheren Sitzung einrichten" angezeigt werden, wenn Sie über Service Trace Viewer angezeigt wird.  
  
 Dieses Aktivitätsablaufverfolgungsmodell ist bei der Benutzernamen-/Kennwortauthentifizierung, der Zertifikatsauthentifizierung und der NTLM-Authentifizierung wirksam.  
  
 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Aushandlung und den SCT-Austausch aufgeführt.  
  
||Zeitpunkt von Aushandlung-/SCT-Austausch|Aktivitäten|Traces|  
|-|-------------------------------------------------|----------------|------------|  
|Sicherer Transport<br /><br /> (HTTPS, SSL)|Bei der ersten empfangenen Nachricht.|Ablaufverfolgungen werden in der Umgebungsaktivität ausgegeben.|-Exchange-Ablauf Verfolgungen<br />-Sicherer Kanal eingerichtet<br />-Geben Sie geheime Schlüssel frei.|  
|Sichere Nachrichtenebene<br /><br /> (WSHTTP)|Bei der ersten empfangenen Nachricht.|Auf dem Client:<br /><br /> -"Sichere Sitzung einrichten" für jede Anforderung/Antwort für RST/RSTR/SCT von "Process Action" der ersten Nachricht<br />-"Sichere Sitzung schließen" für den Abbruch Austausch von der "Proxy Aktivität beenden". Diese Aktivität kann aus einer anderen Umgebungsaktivität erfolgen, je nachdem, wann die Sicherheitssitzung geschlossen wird.<br /><br /> Auf dem Server:<br /><br /> -Eine Aktivität "Prozess Aktion" für jede Anforderung/Antwort für RST/SCT/Cancel auf dem Server. Wenn `propagateActivity` = `true` der Wert ist, werden RST/RSTR/SCT-Aktivitäten mit "Sicherheits Sitzung einrichten" zusammengeführt, und "Abbrechen" wird mit der "Close"-Aktivität vom Client zusammengeführt.<br /><br /> "Sicherheitssitzung einrichten" erfolgt in zwei Stufen:<br /><br /> 1. Authentifizierungs Aushandlung. Dies ist optional, wenn der Client bereits über die richtigen Anmeldeinformationen verfügt. Diese Stufe kann über den sicheren Transport oder über den Nachrichtenaustausch erfolgen. In letzterem Fall, kann der RST-/RSTR-Austausch ein- oder zweimal stattfinden. Bei diesem Austausch werden Ablaufverfolgungen in neuen zuvor entworfenen Anforderungs-/Antwortaktivitäten ausgegeben.<br />2. die Einrichtung der sicheren Sitzung (SCT), in der ein RST/RSTR-Austausch erfolgt. Dieser weist dieselben, bereits beschriebenen Umgebungsaktivitäten auf.|-Exchange-Ablauf Verfolgungen<br />-Sicherer Kanal eingerichtet<br />-Geben Sie geheime Schlüssel frei.|  
  
> [!NOTE]
> Im gemischten Sicherheitsmodus erfolgt die Aushandlung der Authentifizierung in einem binären Austausch, SCT erfolgt jedoch im Nachrichtenaustausch. Im reinen Transportmodus findet die Aushandlung nur beim Transport ohne weitere Aktivitäten statt.  
  
## <a name="message-encryption-and-decryption"></a>Nachrichtenverschlüsselung und -entschlüsselung  

 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Verschlüsselung/Entschlüsselung von Nachrichten und die Signaturauthentifizierung aufgeführt.  
  
||Sicherer Transport<br /><br /> (HTTPS, SSL) und sichere Nachrichtenebene<br /><br /> (WSHTTP)|  
|-|---------------------------------------------------------------------------------|  
|Zeitpunkt der Nachrichtenverschlüsselung/-entschlüsselung sowie der Signatur als Nachricht Verschlüsselung/Entschlüsselung sowie die Signaturauthentifizierung|Beim Empfang der Nachricht|  
|Aktivitäten|Ablaufverfolgungen werden in der Aktivität "Aktion verarbeiten" auf dem Client und dem Server ausgegeben.|  
|Traces|-sendSecurityHeader (Absender):<br />-Nachricht signieren<br />-Anforderungs Daten verschlüsseln<br />-receiveSecurityHeader (Empfänger):<br />-Signatur überprüfen<br />-Entschlüsseln von Antwortdaten<br />-Authentifizierung|  
  
> [!NOTE]
> Im reinen Transportmodus findet die Verschlüsselung/Entschlüsselung nur beim Transport ohne weitere Aktivitäten statt.  
  
## <a name="authorization-and-verification"></a>Autorisierung und Überprüfung.  

 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Autorisierung aufgeführt.  
  
||Zeitpunkt der Autorisierung|Aktivitäten|Traces|  
|-|-------------------------------------|----------------|------------|  
|Lokal (Standard)|Nachdem die Nachricht auf den Server entschlüsselt wurde.|Ablaufverfolgungen werden in der Aktivität "Aktion verarbeiten" auf dem Server ausgegeben.|Für Benutzer autorisiert.|  
|Remote|Nachdem die Nachricht auf den Server entschlüsselt wurde.|Ablaufverfolgungen werden in einer neuen von der Aktivität "Aktion verarbeiten" aufgerufenen Aktivität ausgegeben.|Für Benutzer autorisiert.|
