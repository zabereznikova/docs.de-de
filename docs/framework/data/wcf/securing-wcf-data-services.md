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
ms.openlocfilehash: e09007e786772e838a9aaa76eb8ef7a3fe2b7cca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174653"
---
# <a name="securing-wcf-data-services"></a>Sichern von WCF Data Services
In diesem Thema werden Sicherheitsüberlegungen beschrieben, die für die Entwicklung, Bereitstellung und Ausführung von WCF-Datendiensten und -anwendungen, die auf Dienste zugreifen, die das Open Data Protocol (OData) unterstützen, spezifisch sind. Sie sollten auch den Empfehlungen zum Erstellen sicherer .NET Framework-Anwendungen folgen.  
  
Bei der Planung zum Sichern eines WCF Data Services-basierten OData-Dienstes müssen Sie sowohl die Authentifizierung, den Prozess der Erkennung und Überprüfung der Identität eines Prinzipals als auch die Autorisierung des Prozesses berücksichtigen, bei dem festgestellt wird, ob ein authentifizierter Prinzipal Zugriff auf die angeforderten Ressourcen zugelassen. Sie sollten auch erwägen, die Nachricht mit SSL zu verschlüsseln.  
  
## <a name="authenticating-client-requests"></a>Authentifizieren von Clientanforderungen  
WCF Data Services implementiert keine eigene Authentifizierung, sondern stützt sich auf die Authentifizierungsbestimmungen des Datendiensthosts. Dies bedeutet, dass der Dienst davon ausgeht, dass jede Anforderung, die er empfängt, bereits vom Netzwerkhost authentifiziert wurde und dass der Host das Prinzip für die Anforderung ordnungsgemäß über die von WCF Data Services bereitgestellten Schnittstellen identifiziert hat. Diese Authentifizierungsoptionen und -ansätze sind in der mehrteiligen [OData- und Authentifizierungsreihe](https://devblogs.microsoft.com/odata/?s=%22OData+and+authentication%22)beschrieben.  
  
### <a name="authentication-options-for-a-wcf-data-service"></a>Authentifizierungsoptionen für WCF Data Services  
 Die folgende Tabelle enthält einige der Authentifizierungsmechanismen, die für das Authentifizieren von Anforderungen an einen WCF Data Service verfügbar sind.  
  
|Authentifizierungsoptionen|Beschreibung|  
|----------------------------|-----------------|  
|Anonyme Authentifizierung|Wenn die anonyme HTTP-Authentifizierung aktiviert ist, kann jeder Prinzipal eine Verbindung mit dem Datendienst herstellen. Anmeldeinformationen sind für den anonymen Zugriff nicht erforderlich. Verwenden Sie diese Option nur, wenn alle Benutzer Zugriff auf den Datendienst haben sollen.|  
|Standard- und Hashwertauthentifizierung|Für die Authentifizierung sind aus Benutzername und Kennwort bestehende Anmeldeinformationen erforderlich. Unterstützt die Authentifizierung von Nicht-Windows-Clients. **Sicherheitshinweis:**  Die Anmeldeinformationen für die Standardauthentifizierung (Benutzername und Kennwort) werden im Freitext gesendet und können abgefangen werden. Bei der Hashwertauthentifizierung wird ein auf den angegebenen Anmeldeinformationen basierender Hash gesendet. Sie ist daher sicherer als die Standardauthentifizierung. Beide Authentifizierungstypen sind für "Man-in-the-Middle"-Angriffe anfällig. Bei der Verwendung dieser Authentifizierungsmethoden sollte die Kommunikation zwischen Client und Datendienst ggf. mit SSL (Secure Sockets Layer) verschlüsselt werden. <br /><br /> Microsoft Internet Information Services (IIS) bietet eine Implementierung der Basis- und Digestauthentifizierung für HTTP-Anforderungen in einer ASP.NET Anwendung. Diese Windows-Authentifizierungsanbieterimplementierung ermöglicht es einer .NET Framework-Clientanwendung, Anmeldeinformationen im HTTP-Header der Anforderung an den Datendienst bereitzustellen, um die Authentifizierung eines Windows-Benutzers problemlos auszuhandeln. Weitere Informationen finden Sie unter [Technische Referenz für die Digestauthentifizierung](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782794(v=ws.10)).<br /><br /> Wenn Sie möchten, dass Ihr Datendienst die Standardauthentifizierung auf der Grundlage eines benutzerdefinierten Authentifizierungsdienstes und nicht der Windows-Anmeldeinformationen verwendet, müssen Sie eine benutzerdefinierte ADP.NET HTTP-Moduls für die Authentifizierung implementieren.<br /><br /> Ein Beispiel für die Verwendung eines benutzerdefinierten Standardauthentifizierungsschemas mit WCF Data Services finden Sie im Blogbeitrag [OData and Authentication – Part 6 – Custom Basic Authentication](https://devblogs.microsoft.com/odata/odata-and-authentication-part-6-custom-basic-authentication/).|  
|Windows-Authentifizierung|Windows-basierte Anmeldeinformationen werden mit NTLM oder Kerberos ausgetauscht. Dieser Mechanismus ist sicherer als die Standard- oder Hashwertauthentifizierung, erfordert jedoch, dass es sich beim Client um eine Windows-basierte Anwendung handelt. IIS stellt auch eine Implementierung der Windows-Authentifizierung für HTTP-Anforderungen in einer ASP.NET-Anwendung bereit. Weitere Informationen finden Sie unter [ASP.NET Formularauthentifizierungsübersicht](https://docs.microsoft.com/previous-versions/aspnet/7t6b43z4(v=vs.100)).<br /><br /> Ein Beispiel für die Verwendung der Windows-Authentifizierung mit WCF Data Services finden Sie im Blogbeitrag [OData and Authentication – Part 2 – Windows Authentication](https://devblogs.microsoft.com/odata/odata-and-authentication-part-2-windows-authentication/).|  
|ASP.NET Formularauthentifizierung|Die Formularauthentifizierung ermöglicht es Ihnen, Benutzer mit eigenem Code zu authentifizieren und anschließend ein Authentifizierungstoken in einem Cookie oder in der Seiten-URL beizubehalten. Der Benutzername und das Kennwort der Benutzer werden mit einem von Ihnen erstellten Anmeldeformular authentifiziert. Nicht authentifizierte Anforderungen werden zu einer Anmeldeseite umgeleitet, auf der der Benutzer Anmeldeinformationen eingibt und das Formular übermittelt. Wenn die Anwendung die Anforderung authentifiziert, stellt das System ein Ticket aus, das einen Schlüssel zum Wiederherstellen der Identität für nachfolgende Anforderungen enthält. Weitere Informationen finden Sie unter [Formularauthentifizierungsanbieter](https://docs.microsoft.com/previous-versions/aspnet/9wff0kyh(v=vs.100)). **Sicherheitshinweis:**  Standardmäßig ist das Cookie, das das Formularauthentifizierungsticket enthält, nicht gesichert, wenn Sie die Formularauthentifizierung in einer ASP.NET Webanwendung verwenden. Legen Sie ggf. fest, dass das Authentifizierungsticket und die anfänglichen Anmeldeinformationen mit SSL geschützt werden müssen. <br /><br /> Ein Beispiel für die Verwendung der Formularauthentifizierung mit WCF Data Services finden Sie im Blogbeitrag [OData and Authentication – Part 7 – Forms Authentication](https://devblogs.microsoft.com/odata/odata-and-authentication-part-7-forms-authentication/).|  
|Anspruchbasierte Authentifizierung|Bei der anspruchsbasierten Authentifizierung verwendet der Datendienst einen vertrauenswürdigen Identitätsanbieterdienst eines Drittanbieters, um den Benutzer zu authentifizieren. Der Identitätsanbieter nimmt eine positive Authentifizierung des Benutzers vor, der Zugriff auf Datendienstressourcen anfordert, und stellt ein Token aus, das Zugriff auf die angeforderten Ressourcen gewährt. Dieses Token wird dann an den Datendienst übergeben, und der Datendienst gewährt dem Benutzer basierend auf der Vertrauensstellung mit dem Identitätsdienst, von dem das Zugriffstoken ausgestellt wurde, Zugriff.<br /><br /> Der Vorteil der anspruchbasierten Authentifizierung besteht darin, dass mit dieser Methode verschiedene Clienttypen vertrauensdomänenübergreifend authentifiziert werden können. Durch die Verwendung eines Drittanbieter-Identitätsanbieters kann der Datendienst die Anforderungen für die Verwaltung und Authentifizierung von Benutzern abladen. OAuth 2.0 ist ein anspruchbasiertes Authentifizierungsprotokoll, das von der Microsoft Azure AppFabric-Zugriffssteuerung für die Partnerautorisierung als Dienst unterstützt wird. Dieses Protokoll unterstützt REST-basierte Dienste. Ein Beispiel für die Verwendung von OAuth 2.0 mit WCF Data Services finden Sie im Blogbeitrag [OData and Authentication – Part 8 – OAuth WRAP](https://devblogs.microsoft.com/odata/odata-and-authentication-part-8-oauth-wrap/).|  
  
<a name="clientAuthentication"></a>
### <a name="authentication-in-the-client-library"></a>Authentifizierung in der Clientbibliothek  
 Standardmäßig stellt die WCF Data Services-Clientbibliothek keine Anmeldeinformationen bereit, wenn eine Anforderung an einen OData-Dienst gestellt wird. Wenn der Datendienst für die Authentifizierung eines Benutzers Anmeldeinformationen erfordert, können diese Anmeldeinformationen wie im folgenden Beispiel in einem <xref:System.Net.NetworkCredential>-Objekt bereitgestellt werden, auf das von der <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A>-Eigenschaft des <xref:System.Data.Services.Client.DataServiceContext> zugegriffen wird:  
  
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
  
 Weitere Informationen finden Sie unter [Gewusst wie: Angeben von Clientanmeldeinformationen für eine Datendienstanforderung](specify-client-creds-for-a-data-service-request-wcf.md).  
  
 Wenn der Datendienst Anmeldeinformationen erfordert, die nicht mithilfe eines <xref:System.Net.NetworkCredential>-Objekts angegeben werden können (z. B. ein anspruchbasiertes Token oder Cookie), müssen Sie manuell Header in der HTTP-Anforderung festlegen (normalerweise die Header `Authorization` und `Cookie`). Weitere Informationen zu dieser Art von Authentifizierungsszenario finden Sie im Blogbeitrag [OData and Authentication – Part 3 – ClientSide Hooks](https://devblogs.microsoft.com/odata/odata-and-authentication-part-3-clientside-hooks/). Ein Beispiel für das Festlegen von HTTP-Headern in einer Anforderungsnachricht finden Sie unter [Gewusst wie: Festlegen von Headern in der Clientanforderung](how-to-set-headers-in-the-client-request-wcf-data-services.md).  
  
## <a name="impersonation"></a>Identitätswechsel  
 Im Allgemeinen greift der Datendienst anhand der Anmeldeinformationen des Arbeitsprozesses, der den Datendienst hostet, auf erforderliche Ressourcen zu (z. B. Dateien auf dem Server oder eine Datenbank). Bei Verwendung von Identitätswechsel können ASP.NET Anwendungen mit der Windows-Identität (Benutzerkonto) des Benutzers ausgeführt werden, der die Anforderung stellt. Ein Identitätswechsel wird für gewöhnlich in Anwendungen verwendet, bei denen die Benutzerauthentifizierung über IIS erfolgt und die Anmeldeinformationen dieses Prinzipals für den Zugriff auf die benötigten Ressourcen verwendet werden. Weitere Informationen finden Sie unter [ASP.NET Identitätswechsel](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100)).  
  
## <a name="configuring-data-service-authorization"></a>Konfigurieren der Datendienstautorisierung  
 Durch die Autorisierung wird einem Prinzipal oder Prozess, der mittels einer vorherigen erfolgreichen Authentifizierung identifiziert wurde, Zugriff auf Anwendungsressourcen gewährt. Im Allgemeinen sollten Benutzern des Datendiensts nur die Rechte gewährt werden, die zur Ausführung der von Clientanwendungen benötigten Vorgänge erforderlich sind.  
  
### <a name="restrict-access-to-data-service-resources"></a>Einschränken des Zugriffs auf Datendienstressourcen  
 Standardmäßig können Sie mit WCF Data Services jedem Benutzer, der auf den Datendienst zugreifen kann, allgemeinen Lese- und Schreibzugriff für Datendienstressourcen (Entitätssatz und Dienstvorgänge) gewähren. Für jede vom Datendienst verfügbar gemachte Entitätenmenge und alle Dienstvorgänge können separat Regeln zum Definieren des Lese- und Schreibzugriffs eingerichtet werden. Es wird empfohlen, sowohl den Lese- als auch den Schreibzugriff auf die Ressourcen zu beschränken, die von der Clientanwendung benötigt werden. Weitere Informationen finden Sie unter [Mindestressourcenzugriffsanforderungen](configuring-the-data-service-wcf-data-services.md#accessRequirements).  
  
### <a name="implement-role-based-interceptors"></a>Implementieren rollenbasierter Interceptors  
 Interceptors ermöglichen es Ihnen, Anforderungen für Datendienstressourcen abzufangen, bevor sie vom Datendienst verarbeitet werden. Weitere Informationen finden Sie unter [Abfangjäger](interceptors-wcf-data-services.md). Mithilfe von Interceptors können Sie Autorisierungsentscheidungen auf Grundlage des authentifizierten Benutzers treffen, von dem die Anforderung stammt. Ein Beispiel für das Einschränken des Zugriffs auf Datendienstressourcen basierend auf einer authentifizierten Benutzeridentität finden Sie unter [Gewusst wie: Abfangen von Datendienstnachrichten](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
### <a name="restrict-access-to-the-persisted-data-store-and-local-resources"></a>Einschränken des Zugriffs auf den persistenten Datenspeicher und lokale Ressourcen  
 Den für den Zugriff auf den persistenten Datenspeicher verwendeten Konten sollten nur die Rechte für eine Datenbank oder das Dateisystem gewährt werden, die zum Erfüllen der Anforderungen des Datendiensts erforderlich sind. Bei Verwendung der anonymen Authentifizierung ist dies das Konto, unter dem die Hostanwendung ausgeführt wird. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md). Wenn Identitätswechsel verwendet werden, muss authentifizierten Benutzern Zugriff auf diese Ressourcen gewährt werden (dazu wird normalerweise eine Windows-Gruppe verwendet).  
  
## <a name="other-security-considerations"></a>Sonstige Sicherheitsüberlegungen  
  
### <a name="secure-the-data-in-the-payload"></a>Sichern der Daten in der Nutzlast  
OData basiert auf dem HTTP-Protokoll. Abhängig von der vom Datendienst implementierten Authentifizierung kann der Header in einer HTTP-Nachricht wertvolle Benutzeranmeldeinformationen enthalten. Der Nachrichtentext kann ebenfalls wichtige Kundendaten enthalten, die geschützt werden müssen. In beiden Fällen wird empfohlen, den Austausch dieser Informationen mit SSL zu schützen.  
  
### <a name="ignored-message-headers-and-cookies"></a>Ignorierte Nachrichtenheader und Cookies  
 Mit Ausnahme der Header, die Inhaltstypen und Ressourcenpfade deklarieren, werden HTTP-Anforderungsheader ignoriert und nie vom Datendienst festgelegt.  
  
 Cookies können als Teil eines Authentifizierungsschemas verwendet werden, z. B. bei ASP.NET Formularauthentifizierung. Alle HTTP-Cookies, die für eine eingehende Anforderung gesetzt werden, werden jedoch von WCF DataServices ignoriert. Der Host eines Datendienstes kann das Cookie verarbeiten, aber die WCF Data Services-Laufzeit analysiert oder gibt niemals Cookies zurück. Die WCF Data Services-Clientbibliothek verarbeitet auch keine in der Antwort gesendeten Cookies.  
  
### <a name="custom-hosting-requirements"></a>Benutzerdefinierte Hostanforderungen  
 Standardmäßig wird WCF Data Services als ASP.NET Anwendung erstellt, die in IIS gehostet wird. Dies ermöglicht es dem Datendienst, die sicheren Verhalten dieser Plattform zu nutzen. Sie können WCF-Datendienste definieren, die von einem benutzerdefinierten Host gehostet werden. Weitere Informationen finden Sie unter [Hosten des Datendienstes](hosting-the-data-service-wcf-data-services.md). Die Komponenten und die Plattform, von denen ein Datendienst gehostet wird, müssen Angriffe auf den Datendienst durch die folgenden Sicherheitsverhalten verhindern:  
  
- Begrenzen Sie die Länge des in einer Datendienstanforderung akzeptierten URI für alle möglichen Vorgänge.  
  
- Begrenzen Sie die Größe ein- und ausgehender HTTP-Nachrichten.  
  
- Begrenzen Sie die Gesamtanzahl von Anforderungen, die gleichzeitig ausstehen können.  
  
- Beschränken Sie die Größe von HTTP-Headern und deren Werten, und stellen Sie WCF Data Services Zugriff auf Headerdaten bereit.  
  
- Richten Sie eine Erkennung und Verteidigungsmaßnahmen für bekannte Angriffe wie TCP-SYN und Nachrichtenreplay ein.  
  
### <a name="values-are-not-further-encoded"></a>Keine weitere Codierung von Werten  
 Eigenschaftswerte, die an den Datendienst gesendet werden, werden von der WCF Data Services-Laufzeit nicht weiter codiert. Wenn z. B. eine string-Eigenschaft einer Entität formatierten HTML-Inhalt enthält, werden die Tags vom Datendienst nicht HTML-codiert. Eigenschaftenwerte in der Antwort werden vom Datendienst ebenfalls nicht weiter codiert. Von der Clientbibliothek wird auch keine zusätzliche Codierung ausgeführt.  
  
### <a name="considerations-for-client-applications"></a>Überlegungen für Clientanwendungen  
 Die folgenden Sicherheitsüberlegungen gelten für Anwendungen, die den WCF Data Services-Client für den Zugriff auf OData-Dienste verwenden:  
  
- Die Clientbibliothek geht davon aus, dass die für den Zugriff auf den Datendienst verwendeten Protokolle eine geeignete Sicherheitsebene bereitstellen.  
  
- Die Clientbibliothek verwendet alle Standardwerte für Timeouts und Analyseoptionen der Transportstapel der zugrunde liegenden Plattform.  
  
- Die Clientbibliothek liest keine Einstellungen aus Anwendungskonfigurationsdateien.  
  
- Die Clientbibliothek implementiert keine domänenübergreifenden Zugriffsmechanismen. Sie verwendet stattdessen die vom zugrunde liegenden HTTP-Stapel bereitgestellten Mechanismen.  
  
- Die Clientbibliothek verfügt nicht über Benutzeroberflächenelemente und versucht nie, die empfangenen oder gesendeten Daten anzuzeigen oder zu rendern.  
  
- Benutzereingaben und akzeptierte Daten von nicht vertrauenswürdigen Diensten sollten immer von Clientanwendungen überprüft werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
