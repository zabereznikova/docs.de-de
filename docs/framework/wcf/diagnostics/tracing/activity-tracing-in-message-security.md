---
title: "Aktivit&#228;tsablaufverfolgung in der Nachrichtensicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# Aktivit&#228;tsablaufverfolgung in der Nachrichtensicherheit
In diesem Thema wird die Aktivitätsablaufverfolgung für die Sicherheitsverarbeitung beschrieben, die in den folgenden drei Phasen erfolgt.  
  
-   Aushandlung\/SCT\-Austausch.Das kann später auf der Transportebene stattfinden \(über binären Datenaustausch\) oder auf der Nachrichtenebene \(über SOAP\-Nachrichtenaustausch\).  
  
-   Nachrichtenverschlüsselung\/\-entschlüsselung mit Signaturüberprüfung und Authentifizierung.Ablaufverfolgungen werden in der Umgebungsaktivität, in der Regel "Aktion verarbeiten", angezeigt.  
  
-   Autorisierung und Überprüfung.Dies kann lokal geschehen oder bei der Kommunikation zwischen Endpunkten.  
  
## Aushandlung\/SCT\-Austausch  
 In der Phase Aushandlung\/SCT\-Austausch werden zwei Aktivitätstypen auf dem Client erstellt: "Sicherheitssitzung einrichten" und "Sicherheitssitzung schließen". "Sicherheitssitzung einrichten" umfasst die Ablaufverfolgung für den RST\/RSTR\/SCT\-Nachrichtenaustausch, während "Sicherheitssitzung schließen" die Ablaufverfolgung der Cancel\-Nachricht einschließt.  
  
 Auf dem Server wird jede Anforderung\/Antwort zu RST\/RSTR\/SCT in einer eigenen Aktivität angezeigt.Wenn auf dem Server und dem Client `propagateActivity`\=`true` ist, weisen Aktivitäten auf dem Server die gleiche ID auf. Außerdem werden die Aktivitäten bei der Anzeige über Service Trace Viewer zusammen in "Sicherheitssitzung einrichten" angezeigt.  
  
 Dieses Aktivitätsablaufverfolgungsmodell ist bei der Benutzernamen\-\/Kennwortauthentifizierung, der Zertifikatsauthentifizierung und der NTLM\-Authentifizierung wirksam.  
  
 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Aushandlung und den SCT\-Austausch aufgeführt.  
  
||Zeitpunkt von Aushandlung\-\/SCT\-Austausch|Aktivitäten|Ablaufverfolgungen|  
|-|-------------------------------------------------|-----------------|------------------------|  
|Sicherer Transport<br /><br /> \(HTTPS, SSL\)|Bei der ersten empfangenen Nachricht.|Ablaufverfolgungen werden in der Umgebungsaktivität ausgegeben.|-   Ablaufverfolgungen zu Austauschinformationen<br />-   Sicherer Kanal wurde hergestellt.<br />-   Geheime Schlüssel wurden abgerufen.|  
|Sichere Nachrichtenebene<br /><br /> \(WSHTTP\)|Bei der ersten empfangenen Nachricht.|Auf dem Client:<br /><br /> -   "Sicherheitssitzung einrichten" aus "Aktion verarbeiten" dieser ersten Nachricht für jede Anforderung\/Antwort zu RST\/RSTR\/SCT.<br />-   "Sicherheitssitzung schließen" für den CANCEL\-Austausch aus der Aktivität "Proxy schließen". Diese Aktivität kann aus einer anderen Umgebungsaktivität erfolgen, je nachdem, wann die Sicherheitssitzung geschlossen wird.<br /><br /> Auf dem Server:<br /><br /> -   Eine Aktivität "Aktion verarbeiten" für jede Anforderung\/Antwort zu RST\/SCT\/Cancel auf dem Server.Wenn `propagateActivity`\=`true`, werden RST\/RSTR\/SCT\-Aktivitäten mit "Sicherheitssitzung einrichten" und Cancel wird mit der Aktivität "Schließen" zusammengeführt.<br /><br /> "Sicherheitssitzung einrichten" erfolgt in zwei Stufen:<br /><br /> 1.  Aushandlung der Authentifizierung.Dies ist optional, wenn der Client bereits über die richtigen Anmeldeinformationen verfügt.Diese Stufe kann über den sicheren Transport oder über den Nachrichtenaustausch erfolgen.In letzterem Fall, kann der RST\-\/RSTR\-Austausch ein\- oder zweimal stattfinden.Bei diesem Austausch werden Ablaufverfolgungen in neuen zuvor entworfenen Anforderungs\-\/Antwortaktivitäten ausgegeben.<br />2.  Einrichtung der Sicherheitssitzung \(SCT\), wobei ein RST\/RSTR\-Austausch erfolgt.Dieser weist dieselben, bereits beschriebenen Umgebungsaktivitäten auf.|-   Ablaufverfolgungen zu Austauschinformationen<br />-   Sicherer Kanal wurde hergestellt.<br />-   Geheime Schlüssel wurden abgerufen.|  
  
> [!NOTE]
>  Im gemischten Sicherheitsmodus erfolgt die Aushandlung der Authentifizierung in einem binären Austausch, SCT erfolgt jedoch im Nachrichtenaustausch.Im reinen Transportmodus findet die Aushandlung nur beim Transport ohne weitere Aktivitäten statt.  
  
## Nachrichtenverschlüsselung und \-entschlüsselung  
 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Verschlüsselung\/Entschlüsselung von Nachrichten und die Signaturauthentifizierung aufgeführt.  
  
||Sicherer Transport<br /><br /> \(HTTPS, SSL\) und sichere Nachrichtenebene<br /><br /> \(WSHTTP\)|  
|-|---------------------------------------------------------------------------------------|  
|Zeitpunkt der Nachrichtenverschlüsselung\/\-entschlüsselung sowie der Signatur als Nachricht Verschlüsselung\/Entschlüsselung sowie die Signaturauthentifizierung|Beim Empfang der Nachricht|  
|Aktivitäten|Ablaufverfolgungen werden in der Aktivität "Aktion verarbeiten" auf dem Client und dem Server ausgegeben.|  
|Ablaufverfolgungen|-   sendSecurityHeader \(Absender\):<br />-   Signieren der Nachricht<br />-   Verschlüsseln der Anforderungsdaten<br />-   receiveSecurityHeader \(Empfänger\):<br />-   Überprüfen der Signatur<br />-   Entschlüsseln der Antwortdaten<br />-   Authentifizierung|  
  
> [!NOTE]
>  Im reinen Transportmodus findet die Verschlüsselung\/Entschlüsselung nur beim Transport ohne weitere Aktivitäten statt.  
  
## Autorisierung und Überprüfung.  
 In der folgenden Tabelle werden die Aktivitäten und Ablaufverfolgungen für die Autorisierung aufgeführt.  
  
||Zeitpunkt der Autorisierung|Aktivitäten|Ablaufverfolgungen|  
|-|---------------------------------|-----------------|------------------------|  
|Lokal \(Standard\)|Nachdem die Nachricht auf den Server entschlüsselt wurde.|Ablaufverfolgungen werden in der Aktivität "Aktion verarbeiten" auf dem Server ausgegeben.|Für Benutzer autorisiert.|  
|Remote|Nachdem die Nachricht auf den Server entschlüsselt wurde.|Ablaufverfolgungen werden in einer neuen von der Aktivität "Aktion verarbeiten" aufgerufenen Aktivität ausgegeben.|Für Benutzer autorisiert.|