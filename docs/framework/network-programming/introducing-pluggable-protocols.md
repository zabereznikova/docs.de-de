---
title: Einführung in austauschbare Protokolle
description: Hier erfahren Sie mehr über austauschbare Protokolle, die die Entwicklung von Anwendungen unterstützen, die unabhängig von den von Ressourcen verwendeten Protokolldetails Internetressourcen verwenden.
ms.date: 03/30/2017
helpviewer_keywords:
- data requests, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- URI
- Windows Sockets
- request/response model
- sending data, pluggable protocols
- pluggable protocols
- WebClient class, about WebClient class
- pluggable protocols, about pluggable protocols
- Internet, pluggable protocols
- path identifiers
- Uniform Resource Identifier
- application development [.NET Framework], pluggable protocols
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
- server identifiers
- scheme identifiers
ms.assetid: 4b48e22d-e4e5-48f0-be80-d549bda97415
ms.openlocfilehash: 0bc2d0d005e50b04aff360866a146f6fe6b0ea02
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502352"
---
# <a name="introducing-pluggable-protocols"></a>Einführung in austauschbare Protokolle
Microsoft .NET Framework stellt eine mehrschichtige, erweiterbare und verwaltete Implementierung von Internetdiensten zur Verfügung. Die Internetdienste können schnell und auf einfache Weise in Ihre Anwendungen integriert werden. Die Internetzugriffsklassen in den Namespaces <xref:System.Net> und <xref:System.Net.Sockets> können zur Implementierung von sowohl webbasierten als auch internetbasierten Anwendungen verwendet werden.  
  
## <a name="internet-applications"></a>Internetanwendungen  
 Internetanwendungen können grob in zwei Kategorien eingeteilt werden: Clientanwendungen, die Informationen anfordern, und Serveranwendungen, die auf Informationsanforderungen von Clients reagieren. Die klassische Client-Server-Internetanwendung ist das World Wide Web. Hier greifen Personen mithilfe eines Browsers auf Dokumente und andere Daten zu, die auf Webservern in der ganzen Welt gespeichert sind.  
  
 Anwendungen sind nicht auf eine dieser Rollen beschränkt. So antwortet der bekannte Middle-Tier-Anwendungsserver beispielsweise auf Clientanfragen, indem er Daten von einem anderen Server anfordert. Dadurch agiert er gleichzeitig als Server und Client.  
  
 Die Clientanwendung sendet eine Anforderung durch Identifizieren der angeforderten Internetressource und des Kommunikationsprotokolls, die dann für die Anforderung und die Antwort verwendet werden. Der Client stellt bei Bedarf auch alle zusätzlichen Daten bereit, die zum Abschließen der Anforderung erforderlich sind, wie z.B. Informationen zum Proxystandort oder der Authentifizierung (Benutzername, Kennwort usw.). Sobald die Anforderung formuliert ist, kann sie an den Server gesendet werden.  
  
## <a name="identifying-resources"></a>Identifizieren von Ressourcen  
 .NET Framework verwendet zum Identifizieren der angeforderten Internetressource und des Kommunikationsprotokolls einen Uniform Resource Identifier (URI). Der URI besteht aus mindestens drei, eventuell vier Fragmenten: dem Schemabezeichner, der das Kommunikationsprotokoll für Anforderung und Antwort identifiziert; dem Serverbezeichner, der entweder aus einem DNS-Hostnamen (Domain Name System) oder einer TCP-Adresse zur eindeutigen Identifizierung des Servers im Internet besteht; dem Pfadbezeichner, der die angeforderte Information auf dem Server sucht; sowie der optionalen Abfragezeichenfolge, die Informationen vom Client an den Server übergibt. Der URI `http://www.contoso.com/whatsnew.aspx?date=today` besteht beispielsweise aus dem Schemabezeichner `http`, dem Serverbezeichner `www.contoso.com`, dem Pfad `/whatsnew.aspx` und der Abfragezeichenfolge `?date=today`.  
  
 Nachdem der Server die Anforderung empfangen und die Antwort verarbeitet hat, gibt er die Antwort an die Clientanwendung zurück. Die Antwort enthält zusätzliche Informationen, wie etwa den Inhaltstyp (z.B. unformatierter Text oder XML-Daten).  
  
## <a name="requests-and-responses-in-the-net-framework"></a>Anforderungen und Antworten in .NET Framework  
 .NET Framework verwendet spezifische Klassen zum Bereitstellen der drei Informationen, die für den Zugriff auf Internetressourcen über das Anforderungs-/Antwortmodell erforderlich sind: die Klasse <xref:System.Uri>, die den URI der von Ihnen gesuchten Internetressource enthält; die Klasse <xref:System.Net.WebRequest>, die eine Anforderung für die Ressource enthält; sowie die Klasse <xref:System.Net.WebResponse>, die einen Container für die eingehende Antwort bereitstellt.  
  
 Clientanwendungen erstellen `WebRequest`-Instanzen durch Übergeben des URI der Netzwerkressource an die Methode <xref:System.Net.WebRequest.Create%2A>. Diese statische Methode erstellt für ein bestimmtes Protokoll, wie z.B. HTTP, eine `WebRequest`. Die zurückgegebene `WebRequest` ermöglicht den Zugriff auf Eigenschaften, mit denen sowohl die Anforderung an den Server als auch der Zugriff auf den beim Stellen der Anforderung gesendeten Datenstrom gesteuert wird. Die Methode <xref:System.Net.WebRequest.GetResponse%2A> auf der `WebRequest` sendet die Anforderung von der Clientanwendung an den im URI identifizierten Server. Bei verzögerter Antwort kann die Anforderung durch Anwenden der Methode <xref:System.Net.WebRequest.BeginGetResponse%2A> auf die **WebRequest** asynchron erstellt werden. Die Antwort kann zu einem späteren Zeitpunkt mithilfe der Methode <xref:System.Net.WebRequest.EndGetResponse%2A> zurückgegeben werden.  
  
 Mit den Methoden **GetResponse** und **EndGetResponse** wird eine **WebResponse** zurückgegeben, die Zugriff auf die vom Server zurückgegebenen Daten ermöglicht. Die Methode <xref:System.Net.WebResponse.GetResponseStream%2A> stellt der anfordernden Anwendung diese Daten als Stream bereit. Daher können sie überall dort in der Anwendung verwendet werden, wo Datenströme genutzt werden.  
  
 Die Klassen **WebRequest** und **WebResponse** bilden die Grundlage für die austauschbaren Protokolle. Austauschbare Protokolle stellen eine Implementierung von Netzwerkdiensten zur Entwicklung von Anwendungen dar, bei denen man sich keine Gedanken über die spezifischen Details des Protokolls machen muss, das die jeweilige Internetressource verwendet. Abgeleitete Klassen von **WebRequest** werden mit der **WebRequest**-Klasse registriert, um die Einzelheiten der tatsächlichen Verbindungsherstellung zu Internetressourcen zu verwalten.  
  
 Die Klasse <xref:System.Net.HttpWebRequest> verwaltet beispielsweise die Einzelheiten zur Verbindung mit einer Internetressource mithilfe von HTTP. Erkennt die **WebRequest.Create**-Methode einen URI, der mit „http:“ oder „https:“ beginnt (den Protokollbezeichnern für HTTP und sicheres HTTP), kann die zurückgegebene **WebRequest** standardmäßig so verwendet werden, wie sie ist oder für einen Zugriff auf protokollspezifische Eigenschaften in **HttpWebRequest** umgewandelt werden. In den meisten Fällen stellt die **WebRequest** alle für eine Anforderung erforderlichen Informationen bereit.  
  
 In einer **WebRequest** kann jedes Protokoll verwendet werden, das als Anforderungs-/Antworttransaktion dargestellt werden kann. Sie können protokollspezifische Klassen von **WebRequest** und **WebResponse** ableiten und sie anschließend mit der statischen Methode <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> zur Verwendung durch die Anwendung registrieren.  
  
 Ist für Internetanforderungen eine Clientautorisierung erforderlich, werden die benötigten Anmeldeinformationen durch die Eigenschaft <xref:System.Net.WebRequest.Credentials%2A> der **WebRequest** bereitgestellt. Diese Anmeldeinformationen können ein einfaches Benutzername-Kennwort-Paar für eine Standard-HTTP- oder Digestauthentifizierung sein oder ein Satz bestehend aus Name/Kennwort/Domäne für eine NTLM- oder Kerberos-Authentifizierung. Ein Satz Anmeldeinformationen kann in einer <xref:System.Net.NetworkCredential>-Instanz gespeichert werden, mehrere Sätze können gleichzeitig in einer <xref:System.Net.CredentialCache>-Instanz gespeichert werden. Der URI der Anforderung und das vom Server unterstütze Authentifizierungsschema werden vom **CredentialCache** zur Bestimmung der Anmeldeinformationen verwendet, die an den Server gesendet werden sollen.  
  
## <a name="simple-requests-with-webclient"></a>Einfache Anforderungen mit WebClient  
 Für Anwendungen, die einfache Anforderungen für Internetressourcen erstellen müssen, stellt die Klasse <xref:System.Net.WebClient> allgemeine Methoden für das Hochladen oder Herunterladen von Daten zu oder von einem Internetserver bereit. **WebClient** verwendet für den Zugriff auf Internetressourcen die **WebRequest**-Klasse. Aus diesem Grund kann die **WebClient**-Klasse jedes registrierte austauschbare Protokoll verwenden.  
  
 Für Anwendungen, die das Anforderungs-/Antwortmodell nicht verwenden können oder die das Netzwerk überwachen und Anforderungen senden müssen, stellt der **System.Net.Sockets**-Namespace die Klassen <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> und <xref:System.Net.Sockets.UdpClient> bereit. Diese Klassen behandeln die Details für die Verbindungsherstellung mithilfe verschiedener Transportprotokolle und machen der Anwendung die Netzwerkverbindung als Stream verfügbar.  
  
 Die **System.Net.Sockets**-Klassen erweisen sich besonders für Entwickler als nützlich, die mit der Windows Sockets-Schnittstelle vertraut sind oder die die Kontrolle durch das Programmieren auf Socketebene benötigen. Die **System.Net.Sockets**-Klassen stellen innerhalb der **System.Net**-Klassen einen Übergangspunkt von verwaltetem zu nativem Code dar. In den meisten Fällen marshallen **System.Net.Sockets**-Klassen Daten in ihre jeweilige Windows-32-Bit-Entsprechung und führen alle erforderlichen Sicherheitsüberprüfungen durch.  
  
## <a name="see-also"></a>Siehe auch

- [Programmieren austauschbarer Protokolle](programming-pluggable-protocols.md)
- [Netzwerkprogrammierung in .NET Framework](index.md)
- [Beispiele zur Netzwerkprogrammierung](network-programming-samples.md)
