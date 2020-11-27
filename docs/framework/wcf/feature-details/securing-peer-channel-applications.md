---
title: Sichern von Peerkanalanwendungen
ms.date: 03/30/2017
ms.assetid: d4a0311d-3f78-4525-9c4b-5c93c4492f28
ms.openlocfilehash: 21bec1279d0f0172aa0e8acbcc05adf30a97c5b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288423"
---
# <a name="securing-peer-channel-applications"></a>Sichern von Peerkanalanwendungen

Wie bei anderen Bindungen unter WinFX `NetPeerTcpBinding` ist Sicherheit standardmäßig aktiviert und bietet sowohl Transport-als auch Nachrichten basierte Sicherheit (oder beides). In diesem Thema werden diese beiden Typen von Sicherheit erläutert. Der Typ der Sicherheit wird vom Sicherheitsmodus-Tag in der Bindungsspezifikation (<xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>`Mode`) angegeben.  
  
## <a name="transport-based-security"></a>Transportbasierte Sicherheit  

 Peerkanal unterstützt zwei Arten von Authentifizierungs-Anmeldeinformationen für die Transportsicherung, die beide das Festlegen der `ClientCredentialSettings.Peer`-Eigenschaft auf die zugeordnete `ChannelFactory` erfordern:  
  
- Password: Clients verwenden das Wissen eines geheimen Kennworts, um Verbindungen zu authentifizieren. Wenn dieser Anmeldeinformationstyp verwendet wird, muss `ClientCredentialSettings.Peer.MeshPassword` ein gültiges Kennwort enthalten und optional eine `X509Certificate2`-Instanz.  
  
- Zertifikat Eine bestimmte Anwendungsauthentifizierung wird verwendet. Wenn dieser Anmeldeinformationstyp verwendet wird, müssen Sie eine konkrete Implementierung von <xref:System.IdentityModel.Selectors.X509CertificateValidator> in `ClientCredentialSettings.Peer.PeerAuthentication` verwenden.  
  
## <a name="message-based-security"></a>Nachrichtenbasierte Sicherheit  

 Mit der Nachrichtensicherheit kann eine Anwendung ausgehende Nachrichten signieren, sodass alle Empfänger überprüfen können, dass die Nachricht von einer vertrauenswürdigen Partei gesendet und nicht manipuliert wurde. Derzeit unterstützt Peerkanal nur X.509-Anmeldeinformations-Nachrichtensignierung.  
  
## <a name="best-practices"></a>Bewährte Methoden  
  
- In diesem Abschnitt wird die empfohlene Vorgehensweise zum Sichern von Peerkanalanwendungen erläutert.  
  
### <a name="enable-security-with-peer-channel-applications"></a>Aktivieren von Sicherheit mit Peerkanalanwendungen  

 Aufgrund der Verteilungseigenschaft der Peerkanalprotokolle ist es schwierig, Netzmitgliedschaft, Vertraulichkeit und Datenschutz in einem ungesicherten Netz zu erzwingen. Es ist auch wichtig, die Kommunikation zwischen Clients und dem Auflösungsdienst zu sichern. Verwenden Sie unter Peer Name Resolution-Protokoll (PNRP) sichere Namen, um Spoofing und andere häufige Angriffe zu vermeiden. Sichern Sie einen benutzerdefinierten Auflösungsdienst durch Aktivieren der Sicherheit auf den Verbindungsclients, die den Auflösungsdienst kontaktieren, einschließlich der nachrichten- und transportbasierten Sicherheit.  
  
### <a name="use-the-strongest-possible-security-model"></a>Verwenden des möglichst stärksten Sicherheitsmodells  

 Verwenden Sie z. B. das zertifikatbasierte Authentifizierungsmodell, wenn jeder Mesh-Member einzeln identifiziert werden muss. Wenn das nicht möglich ist, verwenden Sie die kennwortbasierte Authentifizierung, die aktuellen Empfehlungen folgt, um sie sicher zu halten. Dies umfasst die Freigabe von Kennwörtern nur für vertrauenswürdige Benutzer, die Übertragung von Kennwörtern in einem sicheren Medium, häufiges Ändern von Kennwörtern und Verwenden sicherer Kennwörter (mindestens acht Zeichen, mit mindestens einem Buchstaben in Groß- und Kleinschreibung, einer Ziffer und einem Sonderzeichen).  
  
### <a name="never-accept-self-signed-certificates"></a>Kein Akzeptieren selbstsignierter Zertifikate  

 Akzeptieren Sie nie auf Antragstellernamen basierende Zertifikatanmeldeinformationen. Beachten Sie, dass jeder Benutzer ein Zertifikat erstellen kann, und jeder einen Namen auswählen kann, den Sie überprüfen. Überprüfen Sie Zertifikate basierend auf dem Ausgeben von Autoritätsanmeldeinformationen (entweder ein vertrauenswürdiger Aussteller oder eine Stammzertifizierungsstelle), um mögliches Spoofing zu vermeiden.  
  
### <a name="use-message-authentication"></a>Verwenden der Nachrichtenauthentifizierung  

 Verwenden Sie die Nachrichtenauthentifizierung, um zu überprüfen, ob eine Nachricht von einer vertrauenswürdigen Quelle stammt und bei der Übertragung nicht manipuliert wurde. Ohne Nachrichtenauthentifizierung ist es für einen böswilligen Client einfach, Nachrichten im Mesh zu spoofen oder zu manipulieren.  
  
## <a name="peer-channel-code-examples"></a>Peerkanal-Codebeispiele  

 [Peerkanalszenarien](peer-channel-scenarios.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Peerkanalsicherheit](peer-channel-security.md)
- [Erstellen einer Peerkanalanwendung](building-a-peer-channel-application.md)
