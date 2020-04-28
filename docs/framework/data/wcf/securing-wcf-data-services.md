---
title: Sichern von WCF Data Services
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- securing application [WCF Data Services]
- WCF Data Services, security
ms.assetid: 99fc2baa-a040-4549-bc4d-f683d60298af
ms.openlocfilehash: 4dbfe286099ebd0da269ca7ec6e4587d0d8b2e03
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200066"
---
# <a name="securing-wcf-data-services"></a>Sichern von WCF Data Services

In diesem Artikel werden die Sicherheitsaspekte beschrieben, die für die Entwicklung, Bereitstellung und Ausführung von WCF Data Services und Anwendungen gelten, die auf Dienste zugreifen, die die Open Data Protocol (odata) unterstützen. Außerdem sollten Sie die Empfehlungen zum Erstellen von sicheren .NET Framework-Anwendungen befolgen.  
  
Wenn Sie planen, wie Sie einen WCF Data Services basierten odata-Dienst sichern, müssen Sie sowohl die Authentifizierung als auch das ermitteln und Überprüfen der Identität eines Prinzipals und die Autorisierung berücksichtigen. Dies ist der Prozess der Bestimmung, ob ein authentifizierter Prinzipal auf die angeforderten Ressourcen zugreifen darf. Beachten Sie auch, ob die Nachricht mithilfe von SSL verschlüsselt werden soll.  
  
## <a name="authenticating-client-requests"></a>Authentifizieren von Clientanforderungen  
WCF Data Services implementiert keine eigene Authentifizierung, sondern basiert auf den Authentifizierungs Bestimmungen des Datendienst Hosts. Dies bedeutet, dass der Dienst annimmt, dass jede empfangene Anforderung vom Netzwerk Host bereits authentifiziert wurde und dass der Host das Prinzip für die Anforderung ordnungsgemäß über die von WCF Data Services bereitgestellten Schnittstellen identifiziert hat. Diese Authentifizierungs Optionen und-Methoden werden in der mehrteiligen [odata-und Authentifizierungs Reihe](https://devblogs.microsoft.com/odata/?s=%22OData+and+authentication%22)beschrieben.  
  
### <a name="authentication-options-for-a-wcf-data-service"></a>Authentifizierungsoptionen für WCF Data Services  
 Die folgende Tabelle enthält einige der Authentifizierungsmechanismen, die für das Authentifizieren von Anforderungen an einen WCF Data Service verfügbar sind.  
  
|Authentifizierungsoptionen|Beschreibung|  
|----------------------------|-----------------|  
|Anonyme Authentifizierung|Wenn die anonyme HTTP-Authentifizierung aktiviert ist, kann jeder Prinzipal eine Verbindung mit dem Datendienst herstellen. Anmeldeinformationen sind für den anonymen Zugriff nicht erforderlich. Verwenden Sie diese Option nur, wenn alle Benutzer Zugriff auf den Datendienst haben sollen.|  
|Standard- und Hashwertauthentifizierung|Für die Authentifizierung sind aus Benutzername und Kennwort bestehende Anmeldeinformationen erforderlich. Unterstützt die Authentifizierung von Nicht-Windows-Clients. **Sicherheitshinweis:**  Grundlegende Anmelde Informationen für die Authentifizierung (Benutzername und Kennwort) werden im Klartext gesendet und können abgefangen werden. Bei der Hashwertauthentifizierung wird ein auf den angegebenen Anmeldeinformationen basierender Hash gesendet. Sie ist daher sicherer als die Standardauthentifizierung. Beide Authentifizierungstypen sind für "Man-in-the-Middle"-Angriffe anfällig. Bei der Verwendung dieser Authentifizierungsmethoden sollte die Kommunikation zwischen Client und Datendienst ggf. mit SSL (Secure Sockets Layer) verschlüsselt werden. <br /><br /> Microsoft Internetinformationsdienste (IIS) stellt eine Implementierung sowohl der Standard-als auch der Digest-Authentifizierung für HTTP-Anforderungen in einer ASP.NET-Anwendung bereit. Diese Windows-Authentifizierungsanbieterimplementierung ermöglicht es einer .NET Framework-Clientanwendung, Anmeldeinformationen im HTTP-Header der Anforderung an den Datendienst bereitzustellen, um die Authentifizierung eines Windows-Benutzers problemlos auszuhandeln. Weitere Informationen finden Sie unter [Technische Referenz zur Digest-Authentifizierung](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782794(v=ws.10)).<br /><br /> Wenn Sie möchten, dass Ihr Datendienst die Standard Authentifizierung basierend auf einem benutzerdefinierten Authentifizierungsdienst und nicht mit Windows-Anmelde Informationen verwendet, müssen Sie ein benutzerdefiniertes ADP.net-http-Modul für die Authentifizierung implementieren.<br /><br /> Ein Beispiel für die Verwendung eines benutzerdefinierten Standard Authentifizierungs Schemas mit WCF Data Services finden Sie im Blogbeitrag [odata und Authentication – Part 6 – Custom Standard Authentication](https://devblogs.microsoft.com/odata/odata-and-authentication-part-6-custom-basic-authentication/).|  
|Windows-Authentifizierung|Windows-basierte Anmeldeinformationen werden mit NTLM oder Kerberos ausgetauscht. Dieser Mechanismus ist sicherer als die Standard- oder Hashwertauthentifizierung, erfordert jedoch, dass es sich beim Client um eine Windows-basierte Anwendung handelt. IIS bietet auch eine Implementierung der Windows-Authentifizierung für HTTP-Anforderungen in einer ASP.NET-Anwendung. Weitere Informationen finden Sie unter [Übersicht über die ASP.NET-Formular Authentifizierung](https://docs.microsoft.com/previous-versions/aspnet/7t6b43z4(v=vs.100)).<br /><br /> Ein Beispiel für die Verwendung der Windows-Authentifizierung mit WCF Data Services finden Sie im Blogbeitrag [odata und Authentication – Part 2 – Windows-Authentifizierung](https://devblogs.microsoft.com/odata/odata-and-authentication-part-2-windows-authentication/).|  
|ASP.NET-Formular Authentifizierung|Die Formularauthentifizierung ermöglicht es Ihnen, Benutzer mit eigenem Code zu authentifizieren und anschließend ein Authentifizierungstoken in einem Cookie oder in der Seiten-URL beizubehalten. Der Benutzername und das Kennwort der Benutzer werden mit einem von Ihnen erstellten Anmeldeformular authentifiziert. Nicht authentifizierte Anforderungen werden zu einer Anmeldeseite umgeleitet, auf der der Benutzer Anmeldeinformationen eingibt und das Formular übermittelt. Wenn die Anwendung die Anforderung authentifiziert, stellt das System ein Ticket aus, das einen Schlüssel zum Wiederherstellen der Identität für nachfolgende Anforderungen enthält. Weitere Informationen finden Sie unter [Formular Authentifizierungs Anbieter](https://docs.microsoft.com/previous-versions/aspnet/9wff0kyh(v=vs.100)). **Sicherheitshinweis:**  Standardmäßig wird das Cookie, das das Formular Authentifizierungs Ticket enthält, nicht gesichert, wenn Sie die Formular Authentifizierung in einer ASP.NET-Webanwendung verwenden. Legen Sie ggf. fest, dass das Authentifizierungsticket und die anfänglichen Anmeldeinformationen mit SSL geschützt werden müssen. <br /><br /> Ein Beispiel für die Verwendung der Formular Authentifizierung mit WCF Data Services finden Sie im Blogbeitrag [odata und Authentication – Part 7 – Forms Authentication](https://devblogs.microsoft.com/odata/odata-and-authentication-part-7-forms-authentication/).|  
|Anspruchbasierte Authentifizierung|Bei der Anspruchs basierten Authentifizierung basiert der Datendienst auf einem vertrauenswürdigen "Drittanbieter"-Identitäts Anbieter Dienst, um den Benutzer zu authentifizieren. Der Identitätsanbieter nimmt eine positive Authentifizierung des Benutzers vor, der Zugriff auf Datendienstressourcen anfordert, und stellt ein Token aus, das Zugriff auf die angeforderten Ressourcen gewährt. Dieses Token wird dann an den Datendienst übergeben, und der Datendienst gewährt dem Benutzer basierend auf der Vertrauensstellung mit dem Identitätsdienst, von dem das Zugriffstoken ausgestellt wurde, Zugriff.<br /><br /> Der Vorteil der anspruchbasierten Authentifizierung besteht darin, dass mit dieser Methode verschiedene Clienttypen vertrauensdomänenübergreifend authentifiziert werden können. Durch die Verwendung eines Drittanbieter-Identitätsanbieters kann der Datendienst die Anforderungen für die Verwaltung und Authentifizierung von Benutzern abladen. OAuth 2,0 ist ein Anspruchs basiertes Authentifizierungsprotokoll, das von Azure AppFabric Access Control für Verbund Autorisierung als Dienst unterstützt wird. Dieses Protokoll unterstützt REST-basierte Dienste. Ein Beispiel für die Verwendung von OAuth 2,0 mit WCF Data Services finden Sie im Blogbeitrag [odata und Authentication – Part 8 – OAuth Wrap](https://devblogs.microsoft.com/odata/odata-and-authentication-part-8-oauth-wrap/).|  
  
<a name="clientAuthentication"></a>
### <a name="authentication-in-the-client-library"></a>Authentifizierung in der Clientbibliothek  
 Standardmäßig stellt die WCF Data Services Client Bibliothek keine Anmelde Informationen bereit, wenn Sie eine Anforderung an einen odata-Dienst senden. Wenn der Datendienst für die Authentifizierung eines Benutzers Anmeldeinformationen erfordert, können diese Anmeldeinformationen wie im folgenden Beispiel in einem <xref:System.Net.NetworkCredential>-Objekt bereitgestellt werden, auf das von der <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A>-Eigenschaft des <xref:System.Data.Services.Client.DataServiceContext> zugegriffen wird:  
  
```csharp  
// Set the client authentication credentials.  
context.Credentials =  
    new NetworkCredential(userName, password, domain);  
```  
  
```vb  
' Set the client authentication credentials.  
context.Credentials = _  
    New NetworkCredential(userName, password, domain)  
```  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Angeben von Client Anmelde Informationen für eine Datendienst Anforderung](specify-client-creds-for-a-data-service-request-wcf.md).  
  
 Wenn der Datendienst Anmeldeinformationen erfordert, die nicht mithilfe eines <xref:System.Net.NetworkCredential>-Objekts angegeben werden können (z. B. ein anspruchbasiertes Token oder Cookie), müssen Sie manuell Header in der HTTP-Anforderung festlegen (normalerweise die Header `Authorization` und `Cookie`). Weitere Informationen zu dieser Art von Authentifizierungs Szenario finden Sie im Blogbeitrag [odata und Authentication – Part 3 – Clientside Hooks](https://devblogs.microsoft.com/odata/odata-and-authentication-part-3-clientside-hooks/). Ein Beispiel zum Festlegen von HTTP-Headern in einer Anforderungs Nachricht finden Sie unter Gewusst [wie: Festlegen von Headern in der Client Anforderung](how-to-set-headers-in-the-client-request-wcf-data-services.md).  
  
## <a name="impersonation"></a>Identitätswechsel  
 Im Allgemeinen greift der Datendienst anhand der Anmeldeinformationen des Arbeitsprozesses, der den Datendienst hostet, auf erforderliche Ressourcen zu (z. B. Dateien auf dem Server oder eine Datenbank). Wenn Identitätswechsel verwendet werden, können ASP.NET-Anwendungen mit der Windows-Identität (Benutzerkonto) des Benutzers, der die Anforderung ausführt, ausgeführt werden. Ein Identitätswechsel wird für gewöhnlich in Anwendungen verwendet, bei denen die Benutzerauthentifizierung über IIS erfolgt und die Anmeldeinformationen dieses Prinzipals für den Zugriff auf die benötigten Ressourcen verwendet werden. Weitere Informationen finden Sie unter [ASP.net](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100))Identitätswechsel.  
  
## <a name="configuring-data-service-authorization"></a>Konfigurieren der Datendienstautorisierung  
 Durch die Autorisierung wird einem Prinzipal oder Prozess, der mittels einer vorherigen erfolgreichen Authentifizierung identifiziert wurde, Zugriff auf Anwendungsressourcen gewährt. Im Allgemeinen sollten Benutzern des Datendiensts nur die Rechte gewährt werden, die zur Ausführung der von Clientanwendungen benötigten Vorgänge erforderlich sind.  
  
### <a name="restrict-access-to-data-service-resources"></a>Einschränken des Zugriffs auf Datendienstressourcen  
 Standardmäßig können Sie mit WCF Data Services einem beliebigen Benutzer, der auf den Datendienst zugreifen kann, allgemeinen Lese-und Schreibzugriff auf Datendienst Ressourcen (Entitätenmenge und Dienst Vorgänge) gewähren. Für jede vom Datendienst verfügbar gemachte Entitätenmenge und alle Dienstvorgänge können separat Regeln zum Definieren des Lese- und Schreibzugriffs eingerichtet werden. Es wird empfohlen, sowohl den Lese- als auch den Schreibzugriff auf die Ressourcen zu beschränken, die von der Clientanwendung benötigt werden. Weitere Informationen finden Sie unter [Mindestanforderungen für den Ressourcen Zugriff](configuring-the-data-service-wcf-data-services.md#accessRequirements).  
  
### <a name="implement-role-based-interceptors"></a>Implementieren rollenbasierter Interceptors  
 Interceptors ermöglichen es Ihnen, Anforderungen für Datendienstressourcen abzufangen, bevor sie vom Datendienst verarbeitet werden. Weitere Informationen finden Sie unter [Interceptors](interceptors-wcf-data-services.md). Mithilfe von Interceptors können Sie Autorisierungsentscheidungen auf Grundlage des authentifizierten Benutzers treffen, von dem die Anforderung stammt. Ein Beispiel für das Einschränken des Zugriffs auf Datendienst Ressourcen basierend auf einer authentifizierten Benutzeridentität finden Sie unter Gewusst [wie: Abfangen von Datendienst Nachrichten](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
### <a name="restrict-access-to-the-persisted-data-store-and-local-resources"></a>Einschränken des Zugriffs auf den persistenten Datenspeicher und lokale Ressourcen  
 Den für den Zugriff auf den persistenten Datenspeicher verwendeten Konten sollten nur die Rechte für eine Datenbank oder das Dateisystem gewährt werden, die zum Erfüllen der Anforderungen des Datendiensts erforderlich sind. Bei Verwendung der anonymen Authentifizierung ist dies das Konto, unter dem die Hostanwendung ausgeführt wird. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md). Wenn Identitätswechsel verwendet werden, muss authentifizierten Benutzern Zugriff auf diese Ressourcen gewährt werden (dazu wird normalerweise eine Windows-Gruppe verwendet).  
  
## <a name="other-security-considerations"></a>Sonstige Sicherheitsüberlegungen  
  
### <a name="secure-the-data-in-the-payload"></a>Sichern der Daten in der Nutzlast  
Odata basiert auf dem HTTP-Protokoll. Abhängig von der vom Datendienst implementierten Authentifizierung kann der Header in einer HTTP-Nachricht wertvolle Benutzeranmeldeinformationen enthalten. Der Nachrichtentext kann ebenfalls wichtige Kundendaten enthalten, die geschützt werden müssen. In beiden Fällen wird empfohlen, den Austausch dieser Informationen mit SSL zu schützen.  
  
### <a name="ignored-message-headers-and-cookies"></a>Ignorierte Nachrichtenheader und Cookies  
 Mit Ausnahme der Header, die Inhaltstypen und Ressourcenpfade deklarieren, werden HTTP-Anforderungsheader ignoriert und nie vom Datendienst festgelegt.  
  
 Cookies können als Teil eines Authentifizierungs Schemas verwendet werden, z. b. bei der ASP.NET-Formular Authentifizierung. Alle HTTP-Cookies, die für eine eingehende Anforderung festgelegt wurden, werden jedoch von WCF DataServices ignoriert. Der Host eines Daten Diensts kann das Cookie verarbeiten, aber die WCF Data Services Runtime analysiert oder gibt Cookies nie aus. Die WCF Data Services Client Bibliothek verarbeitet auch keine Cookies, die in der Antwort gesendet werden.  
  
### <a name="custom-hosting-requirements"></a>Benutzerdefinierte Hostanforderungen  
 Standardmäßig wird WCF Data Services als ASP.NET-Anwendung erstellt, die in IIS gehostet wird. Dies ermöglicht es dem Datendienst, die sicheren Verhalten dieser Plattform zu nutzen. Sie können WCF Data Services definieren, die von einem benutzerdefinierten Host gehostet werden. Weitere Informationen finden Sie unter [Hosting the Data Service](hosting-the-data-service-wcf-data-services.md). Die Komponenten und die Plattform, von denen ein Datendienst gehostet wird, müssen Angriffe auf den Datendienst durch die folgenden Sicherheitsverhalten verhindern:  
  
- Begrenzen Sie die Länge des in einer Datendienstanforderung akzeptierten URI für alle möglichen Vorgänge.  
  
- Begrenzen Sie die Größe ein- und ausgehender HTTP-Nachrichten.  
  
- Begrenzen Sie die Gesamtanzahl von Anforderungen, die gleichzeitig ausstehen können.  
  
- Begrenzen Sie die Größe von HTTP-Headern und deren Werten, und stellen Sie WCF Data Services Zugriff auf Header Daten bereit.  
  
- Richten Sie eine Erkennung und Verteidigungsmaßnahmen für bekannte Angriffe wie TCP-SYN und Nachrichtenreplay ein.  
  
### <a name="values-are-not-further-encoded"></a>Keine weitere Codierung von Werten  
 Eigenschaftswerte, die an den Datendienst gesendet werden, werden von der WCF Data Services Laufzeit nicht weiter codiert. Wenn z. B. eine string-Eigenschaft einer Entität formatierten HTML-Inhalt enthält, werden die Tags vom Datendienst nicht HTML-codiert. Eigenschaftenwerte in der Antwort werden vom Datendienst ebenfalls nicht weiter codiert. Von der Clientbibliothek wird auch keine zusätzliche Codierung ausgeführt.  
  
### <a name="considerations-for-client-applications"></a>Überlegungen für Clientanwendungen  
 Die folgenden Sicherheitsüberlegungen gelten für Anwendungen, die den WCF Data Services-Client für den Zugriff auf odata-Dienste verwenden:  
  
- Die Clientbibliothek geht davon aus, dass die für den Zugriff auf den Datendienst verwendeten Protokolle eine geeignete Sicherheitsebene bereitstellen.  
  
- Die Clientbibliothek verwendet alle Standardwerte für Timeouts und Analyseoptionen der Transportstapel der zugrunde liegenden Plattform.  
  
- Die Clientbibliothek liest keine Einstellungen aus Anwendungskonfigurationsdateien.  
  
- Die Clientbibliothek implementiert keine domänenübergreifenden Zugriffsmechanismen. Sie verwendet stattdessen die vom zugrunde liegenden HTTP-Stapel bereitgestellten Mechanismen.  
  
- Die Clientbibliothek verfügt nicht über Benutzeroberflächenelemente und versucht nie, die empfangenen oder gesendeten Daten anzuzeigen oder zu rendern.  
  
- Benutzereingaben und akzeptierte Daten von nicht vertrauenswürdigen Diensten sollten immer von Clientanwendungen überprüft werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
