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
ms.openlocfilehash: 56ece9c2c81f05047e85ab681e7cfe0da65f35b9
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032438"
---
# <a name="securing-wcf-data-services"></a>Sichern von WCF Data Services
In diesem Thema werden spezielle Sicherheitsüberlegungen hinsichtlich der Entwicklung, Bereitstellung und Ausführung von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] und Anwendungen beschrieben, die auf Dienste zugreifen, die das [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] unterstützen. Neben diesen Hinweisen sollten Sie auch die Empfehlungen zum Erstellen sicherer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Anwendungen befolgen.  
  
 Beim Planen der Sicherheit eines [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-basierten [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Diensts müssen Sie sowohl die Authentifizierung (den Prozess zur Erkennung und Überprüfung der Identität eines Prinzipals) als auch die Autorisierung (den Prozess, durch den bestimmt wird, ob ein authentifizierter Prinzipal auf die angeforderten Ressourcen zugreifen kann) berücksichtigen. Sie sollten auch erwägen, die Nachricht mit SSL zu verschlüsseln.  
  
## <a name="authenticating-client-requests"></a>Authentifizieren von Clientanforderungen  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] implementiert keine eigene Authentifizierung, sondern beruht auf der Authentifizierung des Datendiensthosts. Der Dienst geht also davon aus, dass jede von ihm empfangene Anforderung bereits vom Netzwerkhost authentifiziert wurde und der Host den Prinzipal für die Anforderung anhand der von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] bereitgestellten Schnittstellen korrekt identifiziert hat. Diese Authentifizierungsoptionen und-Methoden finden Sie im [OData und authentifizierungsfolgen](https://go.microsoft.com/fwlink/?LinkId=200381).  
  
### <a name="authentication-options-for-a-wcf-data-service"></a>Authentifizierungsoptionen für WCF Data Services  
 Die folgende Tabelle enthält einige der Authentifizierungsmechanismen, die für das Authentifizieren von Anforderungen an einen WCF Data Service verfügbar sind.  
  
|Authentifizierungsoptionen|Beschreibung|  
|----------------------------|-----------------|  
|Anonyme Authentifizierung|Wenn die anonyme HTTP-Authentifizierung aktiviert ist, kann jeder Prinzipal eine Verbindung mit dem Datendienst herstellen. Anmeldeinformationen sind für den anonymen Zugriff nicht erforderlich. Verwenden Sie diese Option nur, wenn alle Benutzer Zugriff auf den Datendienst haben sollen.|  
|Standard- und Digestauthentifizierung|Für die Authentifizierung sind aus Benutzername und Kennwort bestehende Anmeldeinformationen erforderlich. Unterstützt die Authentifizierung von Nicht-Windows-Clients. **Sicherheitshinweis:** Anmeldeinformationen für Standardauthentifizierung (Benutzername und Kennwort) werden in Klartext gesendet und können abgefangen werden. Bei der Hashwertauthentifizierung wird ein auf den angegebenen Anmeldeinformationen basierender Hash gesendet. Sie ist daher sicherer als die Standardauthentifizierung. Beide Authentifizierungstypen sind für "Man-in-the-Middle"-Angriffe anfällig. Bei der Verwendung dieser Authentifizierungsmethoden sollte die Kommunikation zwischen Client und Datendienst ggf. mit SSL (Secure Sockets Layer) verschlüsselt werden. <br /><br /> Microsoft Internetinformationsdienste (IIS) stellt eine Implementierung der Standard- und Digestauthentifizierung für HTTP-Anforderungen in einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung bereit. Diese Windows-Authentifizierungsanbieterimplementierung ermöglicht es einer .NET Framework-Clientanwendung, Anmeldeinformationen im HTTP-Header der Anforderung an den Datendienst bereitzustellen, um die Authentifizierung eines Windows-Benutzers problemlos auszuhandeln. Weitere Informationen finden Sie unter [technische Referenz für die Digest-Authentifizierung](https://go.microsoft.com/fwlink/?LinkId=200408).<br /><br /> Wenn für den Datendienst keine Windows-Anmeldeinformationen, sondern eine Standardauthentifizierung anhand eines benutzerdefinierten Authentifizierungsdiensts verwendet werden soll, müssen Sie ein benutzerdefiniertes [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-HTTP-Modul für die Authentifizierung implementieren.<br /><br /> Ein Beispiel zur Verwendung eines benutzerdefinierten standardauthentifizierungsschemas mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], finden Sie im Beitrag [benutzerdefinierte Standardauthentifizierung](https://go.microsoft.com/fwlink/?LinkID=200388) in die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] und authentifizierungsfolgen.|  
|Windows-Authentifizierung|Windows-basierte Anmeldeinformationen werden mit NTLM oder Kerberos ausgetauscht. Dieser Mechanismus ist sicherer als die Standard- oder Digestauthentifizierung, erfordert jedoch, dass es sich beim Client um eine Windows-basierte Anwendung handelt. IIS stellt auch eine Implementierung der Windows-Authentifizierung für HTTP-Anforderungen in einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung bereit. Weitere Informationen finden Sie unter [ASP.NET Forms Authentication Overview](https://msdn.microsoft.com/library/099c1587-6934-476e-ac95-28f534bc9708).<br /><br /> Ein Beispiel zur Verwendung von Windows-Authentifizierung mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], finden Sie im Beitrag [Windows-Authentifizierung](https://go.microsoft.com/fwlink/?LinkID=200384) in die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] und authentifizierungsfolgen.|  
|[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Formularauthentifizierung|Die Formularauthentifizierung ermöglicht es Ihnen, Benutzer mit eigenem Code zu authentifizieren und anschließend ein Authentifizierungstoken in einem Cookie oder in der Seiten-URL beizubehalten. Der Benutzername und das Kennwort der Benutzer werden mit einem von Ihnen erstellten Anmeldeformular authentifiziert. Nicht authentifizierte Anforderungen werden zu einer Anmeldeseite umgeleitet, auf der der Benutzer Anmeldeinformationen eingibt und das Formular übermittelt. Wenn die Anwendung die Anforderung authentifiziert, stellt das System ein Ticket aus, das einen Schlüssel zum Wiederherstellen der Identität für nachfolgende Anforderungen enthält. Weitere Informationen finden Sie unter [Formularauthentifizierungsanbieter](https://msdn.microsoft.com/library/77e21ba2-bad1-4967-a8ec-74942dea7e47). **Sicherheitshinweis:** standardmäßig das Cookie, das Formularauthentifizierungsticket enthält, nicht gesichert, bei der Verwendung der Formularauthentifizierung in einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web-Anwendung. Legen Sie ggf. fest, dass das Authentifizierungsticket und die anfänglichen Anmeldeinformationen mit SSL geschützt werden müssen. <br /><br /> Für ein Beispiel zur Verwendung der Authentifizierung mit forms [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], finden Sie im Beitrag [Formularauthentifizierung](https://go.microsoft.com/fwlink/?LinkID=200389) in die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] und authentifizierungsfolgen.|  
|Anspruchbasierte Authentifizierung|Bei der anspruchsbasierten Authentifizierung stützt sich der auf eine vertrauenswürdige "Drittanbieter-Identitätsanbieter-Anbieterdienst für die Benutzerauthentifizierung. Der Identitätsanbieter nimmt eine positive Authentifizierung des Benutzers vor, der Zugriff auf Datendienstressourcen anfordert, und stellt ein Token aus, das Zugriff auf die angeforderten Ressourcen gewährt. Dieses Token wird dann an den Datendienst übergeben, und der Datendienst gewährt dem Benutzer basierend auf der Vertrauensstellung mit dem Identitätsdienst, von dem das Zugriffstoken ausgestellt wurde, Zugriff.<br /><br /> Der Vorteil der anspruchbasierten Authentifizierung besteht darin, dass mit dieser Methode verschiedene Clienttypen vertrauensdomänenübergreifend authentifiziert werden können. Durch die Verwendung eines Drittanbieter-Identitätsanbieters kann der Datendienst die Anforderungen für die Verwaltung und Authentifizierung von Benutzern abladen. OAuth 2.0 ist ein anspruchbasiertes Authentifizierungsprotokoll, das von der Microsoft Azure AppFabric-Zugriffssteuerung für die Partnerautorisierung als Dienst unterstützt wird. Dieses Protokoll unterstützt REST-basierte Dienste. Ein Beispiel zur Verwendung von OAuth 2.0 mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], finden Sie im Beitrag [OData und OAuth](https://go.microsoft.com/fwlink/?LinkId=200514) in die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] und authentifizierungsfolgen.|  
  
<a name="clientAuthentication"></a>   
### <a name="authentication-in-the-client-library"></a>Authentifizierung in der Clientbibliothek  
 Die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek stellt standardmäßig keine Anmeldeinformationen bereit, wenn eine Anforderung an einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Dienst gesendet wird. Wenn der Datendienst für die Authentifizierung eines Benutzers Anmeldeinformationen erfordert, können diese Anmeldeinformationen wie im folgenden Beispiel in einem <xref:System.Net.NetworkCredential>-Objekt bereitgestellt werden, auf das von der <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A>-Eigenschaft des <xref:System.Data.Services.Client.DataServiceContext> zugegriffen wird:  
  
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
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Angeben von Clientanmeldeinformationen für eine Service Request](../../../../docs/framework/data/wcf/specify-client-creds-for-a-data-service-request-wcf.md).  
  
 Wenn der Datendienst Anmeldeinformationen erfordert, die nicht mithilfe eines <xref:System.Net.NetworkCredential>-Objekts angegeben werden können (z. B. ein anspruchbasiertes Token oder Cookie), müssen Sie manuell Header in der HTTP-Anforderung festlegen (normalerweise die Header `Authorization` und `Cookie`). Weitere Informationen zu diesem authentifizierungsszenario finden Sie im Beitrag [OData und Authentifizierung: clientseitige Hooks](https://go.microsoft.com/fwlink/?LinkID=200385). Ein Beispiel zum Festlegen von HTTP-Header in einer Anforderungsnachricht finden Sie unter [Vorgehensweise: Festlegen von Headern in der Clientanforderung](../../../../docs/framework/data/wcf/how-to-set-headers-in-the-client-request-wcf-data-services.md).  
  
## <a name="impersonation"></a>Identitätswechsel  
 Im Allgemeinen greift der Datendienst anhand der Anmeldeinformationen des Arbeitsprozesses, der den Datendienst hostet, auf erforderliche Ressourcen zu (z. B. Dateien auf dem Server oder eine Datenbank). Mithilfe eines Identitätswechsels können [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendungen unter der Windows-Identität (Benutzerkonto) des Benutzers ausgeführt werden, der die Anforderung sendet. Ein Identitätswechsel wird für gewöhnlich in Anwendungen verwendet, bei denen die Benutzerauthentifizierung über IIS erfolgt und die Anmeldeinformationen dieses Prinzipals für den Zugriff auf die benötigten Ressourcen verwendet werden. Weitere Informationen finden Sie unter [ASP.NET-Identitätswechsel](https://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d).  
  
## <a name="configuring-data-service-authorization"></a>Konfigurieren der Datendienstautorisierung  
 Durch die Autorisierung wird einem Prinzipal oder Prozess, der mittels einer vorherigen erfolgreichen Authentifizierung identifiziert wurde, Zugriff auf Anwendungsressourcen gewährt. Im Allgemeinen sollten Benutzern des Datendiensts nur die Rechte gewährt werden, die zur Ausführung der von Clientanwendungen benötigten Vorgänge erforderlich sind.  
  
### <a name="restrict-access-to-data-service-resources"></a>Einschränken des Zugriffs auf Datendienstressourcen  
 Standardmäßig können Sie in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] jedem Benutzer, der auf den Datendienst zugreifen kann, allgemeinen Lese- und Schreibzugriff auf Datendienstressourcen gewähren (Entitätenmengen und Dienstvorgänge). Für jede vom Datendienst verfügbar gemachte Entitätenmenge und alle Dienstvorgänge können separat Regeln zum Definieren des Lese- und Schreibzugriffs eingerichtet werden. Es wird empfohlen, sowohl den Lese- als auch den Schreibzugriff auf die Ressourcen zu beschränken, die von der Clientanwendung benötigt werden. Weitere Informationen finden Sie unter [minimale Ressourcenzugriffsanforderungen](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md#accessRequirements).  
  
### <a name="implement-role-based-interceptors"></a>Implementieren rollenbasierter Interceptors  
 Interceptors ermöglichen es Ihnen, Anforderungen für Datendienstressourcen abzufangen, bevor sie vom Datendienst verarbeitet werden. Weitere Informationen finden Sie unter [Interceptors](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md). Mithilfe von Interceptors können Sie Autorisierungsentscheidungen auf Grundlage des authentifizierten Benutzers treffen, von dem die Anforderung stammt. Ein Beispiel zum Einschränken des Zugriffs auf datendienstressourcen basierend auf einer authentifizierten Benutzeridentität, finden Sie unter [wie: Abfangen von Datendienstnachrichten](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
### <a name="restrict-access-to-the-persisted-data-store-and-local-resources"></a>Einschränken des Zugriffs auf den persistenten Datenspeicher und lokale Ressourcen  
 Den für den Zugriff auf den persistenten Datenspeicher verwendeten Konten sollten nur die Rechte für eine Datenbank oder das Dateisystem gewährt werden, die zum Erfüllen der Anforderungen des Datendiensts erforderlich sind. Bei Verwendung der anonymen Authentifizierung ist dies das Konto, unter dem die Hostanwendung ausgeführt wird. Weitere Informationen finden Sie unter [Vorgehensweise: Entwickeln eines WCF-Datendiensts, der auf IIS ausgeführt wird](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md). Wenn Identitätswechsel verwendet werden, muss authentifizierten Benutzern Zugriff auf diese Ressourcen gewährt werden (dazu wird normalerweise eine Windows-Gruppe verwendet).  
  
## <a name="other-security-considerations"></a>Sonstige Sicherheitsüberlegungen  
  
### <a name="secure-the-data-in-the-payload"></a>Sichern der Daten in der Nutzlast  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] beruht auf dem HTTP-Protokoll. Abhängig von der vom Datendienst implementierten Authentifizierung kann der Header in einer HTTP-Nachricht wertvolle Benutzeranmeldeinformationen enthalten. Der Nachrichtentext kann ebenfalls wichtige Kundendaten enthalten, die geschützt werden müssen. In beiden Fällen wird empfohlen, den Austausch dieser Informationen mit SSL zu schützen.  
  
### <a name="ignored-message-headers-and-cookies"></a>Ignorierte Nachrichtenheader und Cookies  
 Mit Ausnahme der Header, die Inhaltstypen und Ressourcenpfade deklarieren, werden HTTP-Anforderungsheader ignoriert und nie vom Datendienst festgelegt.  
  
 Cookies können als Teil eines Authentifizierungsschemas verwendet werden, z. B. mit der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Formularauthentifizierung. Alle für eine eingehende Anforderung festgelegten HTTP-Cookies werden jedoch von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ignoriert. Der Host eines Datendiensts kann das Cookie verarbeiten, Cookies werden aber nie von der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Runtime analysiert oder zurückgegeben. In der Antwort gesendete Cookies werden auch nicht von der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek verarbeitet.  
  
### <a name="custom-hosting-requirements"></a>Benutzerdefinierte Hostanforderungen  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] wird standardmäßig als eine in IIS gehostete [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung erstellt. Dies ermöglicht es dem Datendienst, die sicheren Verhalten dieser Plattform zu nutzen. Sie können [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] definieren, die von einem benutzerdefinierten Host gehostet werden. Weitere Informationen finden Sie unter [Hosting des Datendiensts](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md). Die Komponenten und die Plattform, von denen ein Datendienst gehostet wird, müssen Angriffe auf den Datendienst durch die folgenden Sicherheitsverhalten verhindern:  
  
-   Begrenzen Sie die Länge des in einer Datendienstanforderung akzeptierten URI für alle möglichen Vorgänge.  
  
-   Begrenzen Sie die Größe ein- und ausgehender HTTP-Nachrichten.  
  
-   Begrenzen Sie die Gesamtanzahl von Anforderungen, die gleichzeitig ausstehen können.  
  
-   Begrenzen Sie die Größe von HTTP-Headern und den zugehörigen Werten, und gewähren Sie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Zugriff auf Headerdaten.  
  
-   Richten Sie eine Erkennung und Verteidigungsmaßnahmen für bekannte Angriffe wie TCP-SYN und Nachrichtenreplay ein.  
  
### <a name="values-are-not-further-encoded"></a>Keine weitere Codierung von Werten  
 An den Datendienst gesendete Eigenschaftenwerte werden von der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Runtime nicht weiter codiert. Wenn z. B. eine string-Eigenschaft einer Entität formatierten HTML-Inhalt enthält, werden die Tags vom Datendienst nicht HTML-codiert. Eigenschaftenwerte in der Antwort werden vom Datendienst ebenfalls nicht weiter codiert. Von der Clientbibliothek wird auch keine zusätzliche Codierung ausgeführt.  
  
### <a name="considerations-for-client-applications"></a>Überlegungen für Clientanwendungen  
 Die folgenden Sicherheitsüberlegungen gelten für Anwendungen, die mithilfe des [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clients auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Dienste zugreifen:  
  
-   Die Clientbibliothek geht davon aus, dass die für den Zugriff auf den Datendienst verwendeten Protokolle eine geeignete Sicherheitsebene bereitstellen.  
  
-   Die Clientbibliothek verwendet alle Standardwerte für Timeouts und Analyseoptionen der Transportstapel der zugrunde liegenden Plattform.  
  
-   Die Clientbibliothek liest keine Einstellungen aus Anwendungskonfigurationsdateien.  
  
-   Die Clientbibliothek implementiert keine domänenübergreifenden Zugriffsmechanismen. Sie verwendet stattdessen die vom zugrunde liegenden HTTP-Stapel bereitgestellten Mechanismen.  
  
-   Die Clientbibliothek verfügt nicht über Benutzeroberflächenelemente und versucht nie, die empfangenen oder gesendeten Daten anzuzeigen oder zu rendern.  
  
-   Benutzereingaben und akzeptierte Daten von nicht vertrauenswürdigen Diensten sollten immer von Clientanwendungen überprüft werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
