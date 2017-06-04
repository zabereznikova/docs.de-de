---
title: "WIF-Sitzungsverwaltung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98bce126-18a9-401b-b20d-67ee462a5f8a
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# WIF-Sitzungsverwaltung
Wenn ein Client zuerst versucht, auf eine geschützte Ressource zuzugreifen, die von einem vertrauender Seite gehostet wird, muss der Client zu einem Sicherheitstokendienst \(STS\) zuerst authentifizieren der durch das vertrauender Seite vertraut wird.  Das STS gibt dann ein Sicherheitstoken an den Client aus.  Der Client stellt dieses Token dem vertrauender Seite dar, das dann den Clientzugriff auf die geschützte Ressource gewährt.  Allerdings soll der Client zum STS für jede Anforderung erneut authentifizieren müssen nicht besonders, da sie möglicherweise nicht einmal auf dem gleichen Computer oder in der gleichen Domäne wie das vertrauender Seite ist.  Stattdessen können Windows Identity Foundation \(WIF\) den Client und vertrauender Seite eine Sitzung anlegen, in der der Client ein Sitzungssicherheitstoken verwendet, um den vertrauender Seite für alle Anforderungen zu authentifizieren nach der ersten Anforderung.  Das vertrauender Seite kann dieses Sitzungssicherheitstoken verwenden, das in einem Cookie gespeichert wird, um <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> des Clients erneut zu erstellen.  
  
 Das STS definiert, welche Authentifizierung der Client bereitstellen muss.  Allerdings kann der Client mehrere Anmeldeinformationen, mit denen es sich um STS authentifizieren kann.  Beispielsweise kann es ein Token von Windows Live, ein Benutzername und ein Kennwort ein, und ein Zertifikat smartkey.  In diesem Fall gewährt das STS dem Client mehrere Identitäten, mit jeder Identität entsprechend einer der Anmeldeinformationen, die vom Client darstellt.  Das vertrauender Seite kann eine oder mehrere dieser Identitäten verwenden, wenn der Entscheidung, welche Zugriffsebene, um des Clients zu gewähren.  
  
 <xref:System.IdentityModel.Tokens.SessionSecurityToken?displayProperty=fullName> wird verwendet, um <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> des Clients erneut zu erstellen, das die Identitäten alle Clients in <xref:System.Security.Claims.ClaimsPrincipal.Identities%2A> enthält.  Jedes <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> in der Auflistung enthält die Bootstraptoken, die mit dieser Identität zugeordnet werden.  
  
 Wenn ein neues Sitzungstoken mit der Sitzungs\-ID des ursprünglichen Sitzungstoken ausgegeben wird, aktualisiert <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler?displayProperty=fullName> nicht das Sitzungstoken im Scheincachen.  Sie sollten ein Sitzungstoken mit einer eindeutigen Sitzungs\-ID immer instanziieren  
  
> [!NOTE]
>  Session.SecurityTokenHandler.ReadToken <xref:System.Xml.XmlException> löst eine Ausnahme aus, wenn ungültige Eingaben empfängt; wenn beispielsweise das Cookie, das das Sitzungstoken enthält, beschädigt ist.  Es wird empfohlen, diese Ausnahme abfangen und stellen anwendungsspezifisches Verhalten bereit.  
  
 Wenn eine geschützte Webseite viele Ressourcen enthält \(wie kleine Grafiken\) die auch in der geschützten Domäne befinden, muss der Client zu vertrauender Seite erneut authentifizieren, um jedes dieser Ressourcen herunterzuladen.  Verwendung eines Sitzungsauthentifizierungstoken wird vermieden, z STS für jede Anforderung authentifiziert werden, jedoch noch bedeutet, dass viele Cookies von gesendet werden.  Sie sollten die Webseite installieren, damit die wichtigen Daten und die Ressourcen in der geschützten Domäne gespeichert werden, während kleine Elemente in einer Domäne ungeschützten gespeichert sind und von der wichtigsten Webseite verknüpft.  Außerdem legen Sie den Cookiepfad fest, um nur die geschützte Domäne zu verweisen.  
  
 Um im Bezugsmodus zu bearbeiten, empfiehlt sich Microsoft einen Handler für das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SessionSecurityTokenCreated>\-Ereignis in der Datei **global.asax.cs** bereitzustellen und die **IsReferenceMode**\-Eigenschaft im Token fest, das in die <xref:System.IdentityModel.Services.SessionSecurityTokenCreatedEventArgs.SessionToken%2A>\-Eigenschaft übergeben wird.  Diese Updates sicherzustellen, dass das Sitzungstoken im Bezugsmodus für jede Anforderung funktioniert und über die <xref:System.IdentityModel.Services.SessionAuthenticationModule.IsReferenceMode%2A>\-Eigenschaft auf dem Sitzungs\-Authentifizierungs\-Modul lediglich festlegen bevorzugt wird.  
  
## Erweiterbarkeit  
 Sie können den Sitzungsverwaltungsmechanismus erweitern.  Ein Grund hierfür ist, die Leistung zu verbessern sein.  Beispielsweise können Sie einen benutzerdefinierten Cookiehandler erstellen, der das Sitzungssicherheitstoken zwischen seinen Zustand im Arbeitsspeicher oder Transformationen optimiert und was in das Cookie wechselt.  Hierzu, können Sie die <xref:System.IdentityModel.Services.SessionAuthenticationModule.CookieHandler%2A?displayProperty=fullName>\-Eigenschaft <xref:System.IdentityModel.Services.SessionAuthenticationModule?displayProperty=fullName> konfigurieren um einen benutzerdefinierten Cookiehandler verwendet der von <xref:System.IdentityModel.Services.CookieHandler?displayProperty=fullName> abgeleitet.  <xref:System.IdentityModel.Services.ChunkedCookieHandler?displayProperty=fullName> ist der Standardwert Cookiehandler, da die Cookies die zulässige Größe für Hypertext Transfer Protocol \(HTTP\) überschreiten; Wenn Sie einen benutzerdefinierten Cookiehandler stattdessen verwenden, müssen Sie Segmentieren implementieren.  
  
 Weitere Informationen finden Sie im [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=248408\)\-Beispiel.  In diesem Beispiel wird eine Farm Bereit Sitzungscache an \(im Gegensatz zu einem tokenreplycache\) für Sie Sitzungen durch Verweis verwenden können, anstatt, große Cookies auszutauschen; dieses Beispiel wird auch eine einfachere Möglichkeit des Sicherns von Cookies in einer Farm.  Der Sitzungscache ist WCF\-basiert.  Hinsichtlich der sichernden Sitzung, zeigt das Beispiel eine neue Funktion in WIF 4.5 einer Cookietransformation auf Grundlage von MachineKey, das aktiviert werden kann, durch den geeigneten Ausschnitt im web.config einfach einfügen.  Das Beispiel selbst wird nicht "bewirtschaftet", aber es zeigt, was Sie zur Durchführung der App Farm\-betriebsbereit erfordern.