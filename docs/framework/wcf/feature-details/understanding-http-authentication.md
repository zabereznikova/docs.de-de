---
title: Grundlagen der HTTP-Authentifizierung
description: Lesen Sie diese Einführung in die HTTP-Authentifizierung in WCF, einschließlich http-Authentifizierungs Schemas und Auswählen eines Authentifizierungs Schemas.
ms.date: 03/30/2017
ms.assetid: 9376309a-39e3-4819-b47b-a73982b57620
ms.openlocfilehash: 761ab7a92aa26ce1437eefa360e5b46df179e32d
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246518"
---
# <a name="understanding-http-authentication"></a>Grundlagen der HTTP-Authentifizierung
Die Authentifizierung besteht in der Identifizierung, ob ein Client berechtigt ist, auf eine Ressource zuzugreifen. Das HTTP-Protokoll unterstützt die Authentifizierung zum Aushandeln des Zugriffs auf eine sichere Ressource.  
  
 Die anfängliche Anforderung von einem Client ist normalerweise eine anonyme Anforderung, die keine Authentifizierungsinformationen enthält. Die HTTP-Serveranwendungen können die anonyme Anforderung ablehnen, während angegeben wird, dass eine Authentifizierung erforderlich ist. Die Serveranwendung sendet WWW-Authentifizierungsheader, um die unterstützten Authentifizierungsschemen anzugeben. In diesem Dokument werden mehrere Authentifizierungs Schemas für http beschrieben und deren Unterstützung in Windows Communication Foundation (WCF) erläutert.  
  
## <a name="http-authentication-schemes"></a>HTTP-Authentifizierungsschemen  
 Der Server kann mehrere Authentifizierungsschemen für den Client zur Auswahl angeben. Die folgende Tabelle beschreibt einige der Authentifizierungsschemas, die häufig in Windows-Anwendungen gefunden werden.  
  
|Authentifizierungsschema|BESCHREIBUNG|  
|---------------------------|-----------------|  
|Anonym|Eine anonyme Anforderung enthält keine Authentifizierungsinformationen. Dies entspricht der Freigabe des Zugriffs auf die Ressource für alle Benutzer.|  
|Basic|Die Basic-Authentifizierung sendet eine Base64-codierte Zeichenfolge mit einem Benutzernamen und einem Kennwort für den Client. Base64 ist keine Verschlüsselung und kann wie der Versand des Benutzernamens und des Kennworts im Klartext verstanden werden. Wenn eine Ressource geschützt werden muss, sollten Sie möglicherweise ein anderes Authentifizierungsschema als die Basic-Authentifizierung verwenden.|  
|Digest|Die Hashwertauthentifizierung ist ein Abfrage/Rückmeldungsschema, das die Basic-Authentifizierung ersetzen soll. Der Server sendet eine Zeichenfolge zufälliger Daten, die als *Nonce* bezeichnet wird, als Herausforderung an den Client. Der Client reagiert mit einem Hash, das neben anderen Informationen den Benutzernamen, das Kennwort und die Nonce enthält. Die Komplexität dieses Austauschs und der Datenhash erschweren die Wiederverwendung der Benutzeranmeldeinformationen mit diesem Authentifizierungsschema.<br /><br /> Für die Hashwertauthentifizierung ist die Verwendung von Windows-Domänenkonten erforderlich. Der Digest- *Bereich* ist der Windows-Domänen Name. Sie können daher einen Server verwenden, der unter einem Betriebssystem ausgeführt wird, das keine Windows-Domänen mit der Hashwertauthentifizierung unterstützt, z. B. Windows XP Home Edition. Umgekehrt muss ein Domänenkonto explizit während der Authentifizierung angegeben werden, wenn der Client unter einem Betriebssystem ausgeführt wird, das keine Windows-Domänen unterstützt.|  
|NTLM|Die NT LAN Manager (NTLM)-Authentifizierung ist ein Abfrage/Rückmeldungsschema, das eine sicherere Variante der Hashwert-Authentifizierung darstellt. NTLM verwendet die Windows-Anmeldeinformationen, um die Abfragedaten anstelle des unverschlüsselten Benutzernamens und Kennworts zu transformieren. Die NTLM-Authentifizierung erfordert mehrere Austausche zwischen dem Client und dem Server. Der Server sowie dazwischen liegende Proxys müssen beständige Verbindungen unterstützen, um die Authentifizierung erfolgreich abzuschließen.|  
|Aushandeln|Beim Aushandeln der Authentifizierung wird automatisch, je nach Verfügbarkeit, zwischen dem Kerberos-Protokoll und der NTLM-Authentifizierung gewählt. Das Kerberos-Protokoll wird verwendet, wenn es zur Verfügung steht, anderenfalls wird versucht NTML zu verwenden. Die Kerberos-Authentifizierung stellt eine wesentliche Verbesserung der NTLM-Authentifizierung dar. Die Kerberos-Authentifizierung ist schneller als NTLM und ermöglicht den Einsatz einer gegenseitigen Authentifizierung und die Weiterleitung der Anmeldeinformationen an Remote-Computer.|  
|Windows Live ID|Der zugrunde liegende Windows-HTTP-Dienst umfasst die Authentifizierung mit Verbundprotokollen. Die Standard-HTTP-Transporte in WCF unterstützen jedoch nicht die Verwendung von Verbund Authentifizierungs Schemas, z. b. Microsoft Windows Live ID. Support für diese Funktion steht derzeit durch die Verwendung der Nachrichtensicherheit zur Verfügung. Weitere Informationen finden Sie unter Verbund [-und ausgestellte Token](federation-and-issued-tokens.md).|  
  
## <a name="choosing-an-authentication-scheme"></a>Auswählen eines Authentifizierungsschemas  
 Bei potenziellen Authentifizierungsschemen für einen HTTP-Server müssen u. a. die folgenden Aspekte beachtet werden:  
  
- Überprüfen Sie, ob die Ressourcen geschützt werden müssen. Für die HTTP-Authentifizierung müssen mehr Daten übertragen werden, zudem kann die Interoperabilität mit Clients eingeschränkt werden. Lassen Sie den anonymen Zugriff auf Ressourcen zu, die nicht geschützt werden müssen.  
  
- Wenn die Ressource geschützt werden muss, überlegen Sie, welche Authentifizierungsschemen die gewünschte Sicherheitsstufe bieten. Das "schwächste", hier erläuterte Standardauthentifizierungsschema ist die Basic-Authentifizierung. Die Basic-Authentifizierung schützt nicht die Benutzeranmeldeinformationen. Das "stärkste" Standardauthentifizierungsschema ist die Negotiate-Authentifizierung, die zum Kerberos-Protokoll führt.  
  
- Ein Server sollte kein Schema enthalten (in den WWW-Authentifizierungsheadern), das die geschützten Ressourcen nicht akzeptieren bzw. angemessen sichern kann. Clients können aus den unterschiedlichen Authentifizierungsschemen des Servers wählen. Einige Clients wählen standardmäßig ein schwaches Authentifizierungsschema oder das erste Authentifizierungsschema in der Liste des Servers.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Transportsicherheit](transport-security-overview.md)
- [Identitätswechsel und Transportsicherheit](using-impersonation-with-transport-security.md)
- [Delegierung und Identitätswechsel](delegation-and-impersonation-with-wcf.md)
