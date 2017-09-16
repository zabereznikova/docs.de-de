---
title: WIF-Sitzungsverwaltung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98bce126-18a9-401b-b20d-67ee462a5f8a
caps.latest.revision: 7
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d71b83231140dcc18e6d2351091fbfd4985e90a2
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="wif-session-management"></a>WIF-Sitzungsverwaltung
Wenn ein Client erstmals versucht auf eine geschützte Ressource zuzugreifen, die von einer vertrauenden Seite gehostet wird, muss sich der Client zunächst gegenüber einem Sicherheitstokendienst (STS) authentifizieren, der von der vertrauenden Seite als vertrauenswürdig eingestuft wird. Der STS stellt dem Client dann ein Sicherheitstoken aus. Der Client präsentiert dieses Token der vertrauenden Seite, die dem Client dann Zugriff auf die geschützte Ressource gewährt. Sie möchten jedoch nicht, dass der Client sich für jede Anfrage erneut gegenüber dem STS authentifizieren muss, vor allem, da er sich möglicherweise nicht auf demselben Computer oder in derselben Domäne wie die vertrauende Seite befindet. Stattdessen fordert die Windows Identity Foundation (WIF) den Client und die vertrauende Seite zur Erstellung einer Sitzung auf, in der der Client ein Sitzungssicherheitstoken verwendet, um sich gegenüber der vertrauenden Seite für alle Anforderungen nach der ersten Anforderung zu authentifizieren. Die vertrauende Seite kann dieses Sitzungssicherheitstoken, das in einem Cookie gespeichert wird, zur Rekonstruktion des <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> des Clients verwenden.  
  
 Der STS definiert, welche Authentifizierung der Client bereitstellen muss. Der Client kann jedoch möglicherweise über mehrere Anmeldeinformationen verfügen, mit denen er sich gegenüber des STS authentifizieren kann. Beispielsweise können ein Token von Windows Live, ein Benutzername und Kennwort, ein Zertifikat und ein Smartkey auftreten. In diesem Fall gewährt der STS dem Client mehrere Identitäten. Jede Identität entspricht einer der Anmeldeinformationen, die vom Client präsentiert wurden. Die vertrauende Seite kann eine oder mehrere dieser Identitäten verwenden, wenn sie entscheidet, welche Zugriffsebene sie dem Client gewährt.  
  
 Die <xref:System.IdentityModel.Tokens.SessionSecurityToken?displayProperty=fullName> wird verwendet, um <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> des Clients zu rekonstruieren, worin alle Clientidentitäten in <xref:System.Security.Claims.ClaimsPrincipal.Identities%2A> enthalten sind. Alle <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> der Auflistung enthalten die Bootstrap-Token, die dieser Identität zugeordnet sind.  
  
 Wenn ein neues Sitzungstoken mit der Sitzungs-ID des ursprünglichen Sitzungstokens ausgestellt wird, aktualisiert <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler?displayProperty=fullName> das Sitzungstoken im Tokencache nicht. Sie sollten immer ein Sitzungstoken mit einer eindeutigen Sitzungs-ID instanziieren.  
  
> [!NOTE]
>  Die Methode „Session.SecurityTokenHandler.ReadToken“ löst eine <xref:System.Xml.XmlException>-Ausnahme aus, wenn sie eine ungültige Eingabe erhält, z.B. wenn das Cookie, das das Sitzungstoken enthält, beschädigt ist. Es wird empfohlen, diese Ausnahme abzufangen und anwendungsspezifisches Verhalten bereitzustellen.  
  
 Wenn eine geschützte Webseite große Menge von Ressourcen (z.B. kleine Grafiken) enthält, die auch in der geschützten Domäne enthalten sind, muss sich der Client gegenüber der vertrauenden Seite erneut authentifizieren, um jede dieser Ressourcen herunterzuladen. Wenn Sie ein Sitzungsauthentifizierungstoken verwenden, müssen Sie sich nicht für jede Anforderung gegenüber dem STS authentifizieren, aber es werden dennoch viele Cookies gesendet werden. Sie sollten die Webseite möglicherweise so einrichten, dass wichtige Daten und Ressourcen in der geschützten Domäne gespeichert werden, während kleinere Elemente in einer ungeschützten Domäne gespeichert und mit der Web-Hauptseite verknüpft sind. Legen Sie den Cookiepfad so fest, dass er nur auf die geschützte Domäne verweist.  
  
 Für den Betrieb im Verweismodus empfiehlt Microsoft die Bereitstellung eines Handlers für das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SessionSecurityTokenCreated>-Ereignis in der Datei **global.asax.cs** sowie das Festlegen der **IsReferenceMode**-Eigenschaft im Token, das an die <xref:System.IdentityModel.Services.SessionSecurityTokenCreatedEventArgs.SessionToken%2A>-Eigenschaft übergeben wurde. Diese Updates stellen sicher, dass das Sitzungstoken für jede Anforderung im Verweismodus arbeitet und gegenüber dem Festlegen der <xref:System.IdentityModel.Services.SessionAuthenticationModule.IsReferenceMode%2A>-Eigenschaft für das Sitzungsauthentifizierungsmodul bevorzugt wird.  
  
## <a name="extensibility"></a>Erweiterungen  
 Sie können den Verwaltungsmechanismus der Sitzung erweitern. Ein Grund dafür wäre die Leistungsverbesserung. Beispielsweise könnten Sie einen benutzerdefinierten Cookiehandler erstellen, der das Sitzungssicherheitstoken zwischen dem cookie- und speicherinternen Zustand transformiert oder optimiert. Zu diesem Zweck können Sie die <xref:System.IdentityModel.Services.SessionAuthenticationModule.CookieHandler%2A?displayProperty=fullName>-Eigenschaft von <xref:System.IdentityModel.Services.SessionAuthenticationModule?displayProperty=fullName> mit einem benutzerdefinierten Cookiehandler konfigurieren, der von <xref:System.IdentityModel.Services.CookieHandler?displayProperty=fullName> abgeleitet wird. <xref:System.IdentityModel.Services.ChunkedCookieHandler?displayProperty=fullName> ist der Standardhandler für das Cookie, weil die Cookies die zulässige Größe für das Hypertext Transfer Protocol (HTTP) überschreiten. Wenn Sie stattdessen einen benutzerdefinierten Cookiehandler verwenden, müssen Sie die Segmentierung implementieren.  
  
 Weitere Informationen finden Sie im Beispiel [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) (http://go.microsoft.com/fwlink/?LinkID=248408). Dieses Beispiel veranschaulicht ein Sitzungscache, das in einer Farm verwendet werden kann (im Gegensatz zu einem Tokenreplycache), sodass Sie Sitzungen als Verweis verwenden können und keine großen Cookies austauschen müssen. Das Beispiel zeigt ebenfalls eine einfachere Sicherung von Cookies in einer Farm. Der Sitzungscache basiert auf WCF. Im Hinblick auf die Sitzungssicherung zeigt das Beispiel eine neue Funktion in WIF 4.5 einer Cookie-Transformation, die auf MachineKey basiert, die aktiviert werden kann, indem Sie einfach den entsprechenden Ausschnitt in der Datei „Web.config“ einfügen. Das Beispiel selbst ist nicht „ausgelagert“, aber es zeigt, was Sie tun müssen, um die Anwendung darauf vorzubereiten.

