---
title: Grundlagen der HTTP-Authentifizierung
ms.date: 03/30/2017
ms.assetid: 9376309a-39e3-4819-b47b-a73982b57620
ms.openlocfilehash: 430b0ddb98514b605178124f331e5152605a2b89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918904"
---
# <a name="understanding-http-authentication"></a>Grundlagen der HTTP-Authentifizierung
Die Authentifizierung besteht in der Identifizierung, ob ein Client berechtigt ist, auf eine Ressource zuzugreifen. Das HTTP-Protokoll unterstützt die Authentifizierung zum Aushandeln des Zugriffs auf eine sichere Ressource.  
  
 Die anfängliche Anforderung von einem Client ist normalerweise eine anonyme Anforderung, die keine Authentifizierungsinformationen enthält. Die HTTP-Serveranwendungen können die anonyme Anforderung ablehnen, während angegeben wird, dass eine Authentifizierung erforderlich ist. Die Serveranwendung sendet WWW-Authentifizierungsheader, um die unterstützten Authentifizierungsschemen anzugeben. Dieses Dokument beschreibt mehrere Authentifizierungsschemen für HTTP und erläutert deren Unterstützung in Windows Communication Foundation (WCF).  
  
## <a name="http-authentication-schemes"></a>HTTP-Authentifizierungsschemen  
 Der Server kann mehrere Authentifizierungsschemen für den Client zur Auswahl angeben. Die folgende Tabelle beschreibt einige der Authentifizierungsschemas, die häufig in Windows-Anwendungen gefunden werden.  
  
|Authentifizierungsschema|Beschreibung|  
|---------------------------|-----------------|  
|Anonym|Eine anonyme Anforderung enthält keine Authentifizierungsinformationen. Dies entspricht der Freigabe des Zugriffs auf die Ressource für alle Benutzer.|  
|Standard|Die Basic-Authentifizierung sendet eine Base64-codierte Zeichenfolge mit einem Benutzernamen und einem Kennwort für den Client. Base64 ist keine Verschlüsselung und kann wie der Versand des Benutzernamens und des Kennworts im Klartext verstanden werden. Wenn eine Ressource geschützt werden muss, sollten Sie möglicherweise ein anderes Authentifizierungsschema als die Basic-Authentifizierung verwenden.|  
|Digest|Die Hashwertauthentifizierung ist ein Abfrage/Rückmeldungsschema, das die Basic-Authentifizierung ersetzen soll. Der Server sendet eine Zeichenfolge zufälliger Daten, die Namen einer *Nonce* an den Client als eine Herausforderung dar. Der Client reagiert mit einem Hash, das neben anderen Informationen den Benutzernamen, das Kennwort und die Nonce enthält. Die Komplexität dieses Austauschs und der Datenhash erschweren die Wiederverwendung der Benutzeranmeldeinformationen mit diesem Authentifizierungsschema.<br /><br /> Für die Hashwertauthentifizierung ist die Verwendung von Windows-Domänenkonten erforderlich. Der Digest *Bereich* ist der Windows-Domänenname. Aus diesem Grund können Sie keinen Server auf ein Betriebssystem installiert ist, die keine Windows-Domänen, z. B. Windows XP Home Edition, mit der Digest-Authentifizierung unterstützt. Umgekehrt muss ein Domänenkonto explizit während der Authentifizierung angegeben werden, wenn der Client unter einem Betriebssystem ausgeführt wird, das keine Windows-Domänen unterstützt.|  
|NTLM|Die NT LAN Manager (NTLM)-Authentifizierung ist ein Abfrage/Rückmeldungsschema, das eine sicherere Variante der Hashwert-Authentifizierung darstellt. NTLM verwendet die Windows-Anmeldeinformationen, um die Abfragedaten anstelle des unverschlüsselten Benutzernamens und Kennworts zu transformieren. Die NTLM-Authentifizierung erfordert mehrere Austausche zwischen dem Client und dem Server. Der Server sowie dazwischen liegende Proxys müssen beständige Verbindungen unterstützen, um die Authentifizierung erfolgreich abzuschließen.|  
|Negotiate|Beim Aushandeln der Authentifizierung wird automatisch, je nach Verfügbarkeit, zwischen dem Kerberos-Protokoll und der NTLM-Authentifizierung gewählt. Das Kerberos-Protokoll wird verwendet, wenn es zur Verfügung steht, anderenfalls wird versucht NTML zu verwenden. Die Kerberos-Authentifizierung stellt eine wesentliche Verbesserung der NTLM-Authentifizierung dar. Die Kerberos-Authentifizierung ist schneller als NTLM und ermöglicht den Einsatz einer gegenseitigen Authentifizierung und die Weiterleitung der Anmeldeinformationen an Remote-Computer.|  
|Windows Live ID|Der zugrunde liegende Windows-HTTP-Dienst umfasst die Authentifizierung mit Verbundprotokollen. Allerdings unterstützen die standard-HTTP-Transporte in WCF nicht die Verwendung von verbundsauthentifizierungsschemen wie Microsoft Windows Live ID an. Support für diese Funktion steht derzeit durch die Verwendung der Nachrichtensicherheit zur Verfügung. Weitere Informationen finden Sie unter [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|  
  
## <a name="choosing-an-authentication-scheme"></a>Auswählen eines Authentifizierungsschemas  
 Bei potenziellen Authentifizierungsschemen für einen HTTP-Server müssen u. a. die folgenden Aspekte beachtet werden:  
  
- Überprüfen Sie, ob die Ressourcen geschützt werden müssen. Für die HTTP-Authentifizierung müssen mehr Daten übertragen werden, zudem kann die Interoperabilität mit Clients eingeschränkt werden. Lassen Sie den anonymen Zugriff auf Ressourcen zu, die nicht geschützt werden müssen.  
  
- Wenn die Ressource geschützt werden muss, überlegen Sie, welche Authentifizierungsschemen die gewünschte Sicherheitsstufe bieten. Das "schwächste", hier erläuterte Standardauthentifizierungsschema ist die Basic-Authentifizierung. Die Basic-Authentifizierung schützt nicht die Benutzeranmeldeinformationen. Das "stärkste" Standardauthentifizierungsschema ist die Negotiate-Authentifizierung, die zum Kerberos-Protokoll führt.  
  
- Ein Server sollte kein Schema enthalten (in den WWW-Authentifizierungsheadern), das die geschützten Ressourcen nicht akzeptieren bzw. angemessen sichern kann. Clients können aus den unterschiedlichen Authentifizierungsschemen des Servers wählen. Einige Clients wählen standardmäßig ein schwaches Authentifizierungsschema oder das erste Authentifizierungsschema in der Liste des Servers.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)
- [Verwenden von Identitätswechsel mit Transportsicherheit](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)
- [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
