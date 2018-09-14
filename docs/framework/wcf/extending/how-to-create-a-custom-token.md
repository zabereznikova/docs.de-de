---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Tokens'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SecurityTokenParameters class
- security [WCF], creating custom tokens
- WSSecurityTokenSerializer class
- SecurityToken class
ms.assetid: 6d892973-1558-4115-a9e1-696777776125
ms.openlocfilehash: fd168bf2e5233d9119872b267aea466a7af07041
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45508368"
---
# <a name="how-to-create-a-custom-token"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Tokens
In diesem Thema wird beschrieben, wie Sie mit der <xref:System.IdentityModel.Tokens.SecurityToken>-Klasse ein benutzerdefiniertes Sicherheitstoken erstellen und in einen benutzerdefinierten Sicherheitstokenanbieter und -authentifizierer integrieren. Ein vollständiges Codebeispiel finden Sie unter den [benutzerdefinierte Token](../../../../docs/framework/wcf/samples/custom-token.md) Beispiel.  
  
 Ein *Sicherheitstoken* ist im Wesentlichen ein XML‑Element, das durch das Windows Communication Foundation (WCF)-Sicherheitsframework verwendet wird, um Ansprüche bezüglich des Absenders in der SOAP-Nachricht darzustellen. WCF-Sicherheit bietet verschiedene Token für vom System bereitgestellten Authentifizierungsmodi. Dazu gehören u.&#160;a. ein Sicherheitstoken für ein X.509-Zertifikat, dargestellt durch die <xref:System.IdentityModel.Tokens.X509SecurityToken>-Klasse, oder ein Sicherheitstoken für den Benutzernamen, dargestellt durch die <xref:System.IdentityModel.Tokens.UserNameSecurityToken>-Klasse.  
  
 Möglicherweise werden Authentifizierungsmodi oder Anmeldeinformationen nicht von den bereitgestellten Typen unterstützt. In diesem Fall müssen Sie ein benutzerdefiniertes Sicherheitstoken erstellen, um eine XML-Darstellung der benutzerdefinierten Anmeldeinformationen in der SOAP-Nachricht bereitzustellen.  
  
 Die folgenden Verfahren zeigen, wie Sie ein benutzerdefiniertes Sicherheitstoken zu erstellen und wie Sie es in der WCF-Sicherheit-Infrastruktur integrieren. In diesem Thema wird ein Kreditkartentoken erstellt, mit dem Informationen über die Kreditkarte des Kunden an den Server übermittelt werden.  
  
 Weitere Informationen über benutzerdefinierte Anmeldeinformationen und Sicherheitstoken-Manager finden Sie unter [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
 Weitere Klassen, die Sicherheitstoken darstellen, finden Sie im <xref:System.IdentityModel.Tokens>-Namespace.  
  
 Weitere Informationen zu Anmeldeinformationen, Sicherheitstoken-Manager sowie Anbieter- und authentifiziererklassen finden Sie unter [Sicherheitsarchitektur](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f).  
  
## <a name="procedures"></a>Verfahren  
 Clientanwendungen müssen über eine Möglichkeit zur Angabe von Kreditkarteninformationen für die Sicherheitsinfrastruktur verfügen. Diese Informationen werden von einer benutzerdefinierten Klasse für Clientanmeldeinformationen für die Anwendung verfügbar gemacht. Zunächst muss eine Klasse erstellt werden, um die Kreditkarteninformationen für die benutzerdefinierten Clientanmeldeinformationen darzustellen.  
  
#### <a name="to-create-a-class-that-represents-credit-card-information-inside-client-credentials"></a>So erstellen Sie eine Klasse, die Kreditkarteninformationen in Clientanmeldeinformationen darstellt  
  
1.  Definieren Sie eine neue Klasse, die die Kreditkarteninformationen für die Anwendung darstellt. Im folgenden Beispiel wird diese Klasse als `CreditCardInfo` bezeichnet.  
  
2.  Fügen Sie der Klasse entsprechende Eigenschaften hinzu, damit die erforderlichen Informationen für das benutzerdefinierte Token von der Anwendung festgelegt werden können. In diesem Beispiel verfügt die Klasse über drei Eigenschaften: `CardNumber`, `CardIssuer` und `ExpirationDate`.  
  
     [!code-csharp[c_CustomToken#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#4)]
     [!code-vb[c_CustomToken#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#4)]  
  
 Im Anschluss muss eine Klasse erstellt werden, die das benutzerdefinierte Sicherheitstoken darstellt. Diese Klasse wird von der Sicherheitstokenanbieter, vom Sicherheitstokenauthentifizierer sowie Serialisierungsprogrammklassen verwendet, um Informationen über das Sicherheitstoken in und aus der WCF-Sicherheitsinfrastruktur übergeben.  
  
#### <a name="to-create-a-custom-security-token-class"></a>So erstellen Sie eine benutzerdefinierte Sicherheitstokenklasse  
  
1.  Definieren Sie eine neue von der <xref:System.IdentityModel.Tokens.SecurityToken>-Klasse abgeleitete Klasse. In diesem Beispiel wird eine Klasse mit der Bezeichnung `CreditCardToken` erstellt.  
  
2.  Überschreiben Sie die <xref:System.IdentityModel.Tokens.SecurityToken.Id%2A>-Eigenschaft. Mit dieser Eigenschaft wird der lokale Bezeichner des Sicherheitstokens abgerufen, mit dem von anderen Elementen in der SOAP-Nachricht auf die XML-Darstellung des Sicherheitstokens verwiesen wird. Der Bezeichner des Tokens in diesem Beispiel kann als Konstruktorparameter übergeben werden. Alternativ wird immer dann ein neuer Parameter generiert, wenn eine Instanz des Sicherheitstokens erstellt wird.  
  
3.  Implementiert die <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A>-Eigenschaft. Diese Eigenschaft gibt eine Auflistung von Sicherheitsschlüsseln zurück, die die Instanz des Sicherheitstokens darstellt. Dieser Schlüssel können von WCF verwendet werden, um Teile der SOAP-Nachricht signieren oder verschlüsseln. Das Sicherheitstoken für die Kreditkarte kann in diesem Beispiel keine Sicherheitsschlüssel enthalten. Aus diesem Grund wird von der Implementierung stets eine leere Auflistung zurückgegeben.  
  
4.  Überschreiben Sie die <xref:System.IdentityModel.Tokens.SecurityToken.ValidFrom%2A>-Eigenschaft und die <xref:System.IdentityModel.Tokens.SecurityToken.ValidTo%2A>-Eigenschaft. Diese Eigenschaften werden von WCF verwendet, um die Gültigkeit der Instanz des Sicherheitstokens zu bestimmen. Das Sicherheitstoken für die Kreditkarte in diesem Beispiel weist nur ein Ablaufdatum auf. Die `ValidFrom`-Eigenschaft gibt daher einen <xref:System.DateTime>-Wert zurück, der das Datum und die Uhrzeit der Instanzerstellung enthält.  
  
     [!code-csharp[c_CustomToken#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#1)]
     [!code-vb[c_CustomToken#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#1)]  
  
 Wenn ein neuer Sicherheitstokentyp erstellt wird, ist eine Implementierung der <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters>-Klasse erforderlich. Mit dieser Implementierung wird in der Konfiguration des Sicherheitsbindungselements der neue Tokentyp dargestellt. Die Parameterklasse für das Sicherheitstoken dient als Vorlage zur Anpassung der Instanz des Sicherheitstokens, das beim Verarbeiten einer Nachricht verwendet wird. Die Vorlage stellt zusätzliche Eigenschaften bereit, mit der die Anwendung Kriterien angeben kann, die vom Sicherheitstoken für eine Verwendung oder Authentifizierung erfüllt werden müssen. Im folgende Beispiel werden keine zusätzlichen Eigenschaften, sodass nur der Sicherheit hinzugefügt, die Typ des Sicherheitstokens entspricht, wenn die WCF-Infrastruktur für eine Instanz des Sicherheitstokens sucht verwendet, oder um zu überprüfen.  
  
#### <a name="to-create-a-custom-security-token-parameters-class"></a>So erstellen Sie eine Parameterklasse für das benutzerdefinierte Sicherheitstoken  
  
1.  Definieren Sie eine neue von der <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters>-Klasse abgeleitete Klasse.  
  
2.  Implementieren Sie die <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.CloneCore%2A>-Methode. Kopieren Sie ggf. alle in der Klasse definierten internen Felder. In diesem Beispiel werden keine weiteren Felder definiert.  
  
3.  Implementieren Sie die schreibgeschützte <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.SupportsClientAuthentication%2A>-Eigenschaft. Diese Eigenschaft gibt `true` zurück, wenn der Typ des Sicherheitstokens, der von dieser Klasse dargestellt wird, zur Authentifizierung eines Clients gegenüber einem Dienst verwendet werden kann. Das Sicherheitstoken der Kreditkarte kann in diesem Beispiel zur Authentifizierung eines Clients gegenüber einem Dienst verwendet werden.  
  
4.  Implementieren Sie die schreibgeschützte <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.SupportsServerAuthentication%2A>-Eigenschaft. Diese Eigenschaft gibt `true` zurück, wenn der Typ des Sicherheitstokens, der von dieser Klasse dargestellt wird, zur Authentifizierung eines Diensts gegenüber einem Client verwendet werden kann. Das Sicherheitstoken der Kreditkarte kann in diesem Beispiel nicht zur Authentifizierung eines Diensts gegenüber einem Client verwendet werden.  
  
5.  Implementieren Sie die schreibgeschützte <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.SupportsClientWindowsIdentity%2A>-Eigenschaft. Diese Eigenschaft gibt `true` zurück, wenn der Typ des Sicherheitstokens, der von dieser Klasse dargestellt wird, einem Windows-Konto zugeordnet werden kann. In diesem Fall wird das Ergebnis der Authentifizierung durch eine Instanz der <xref:System.Security.Principal.WindowsIdentity>-Klasse dargestellt. Das Token in diesem Beispiel kann keinem Windows-Konto zugeordnet werden.  
  
6.  Implementieren Sie die <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.CreateKeyIdentifierClause%28System.IdentityModel.Tokens.SecurityToken%2CSystem.ServiceModel.Security.Tokens.SecurityTokenReferenceStyle%29>-Methode. Diese Methode wird von WCF-Framework zur Sicherheit aufgerufen, wenn dies erforderlich ist einen Verweis auf die Instanz des Sicherheitstokens durch Parameterklasse dieses Sicherheitstoken dargestellt wird. Sowohl die tatsächliche Instanz des Sicherheitstokens als auch der <xref:System.ServiceModel.Security.Tokens.SecurityTokenReferenceStyle>, der den angeforderten Verweistyp angibt, werden als Argumente an diese Methode übergeben. In diesem Beispiel werden vom Kreditkarten-Sicherheitstoken nur interne Verweise unterstützt. Mit der <xref:System.IdentityModel.Tokens.SecurityToken>-Klasse können interne Verweise erstellt werden, sodass für die Implementierung kein zusätzlicher Code erforderlich ist.  
  
7.  Implementieren Sie die <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.InitializeSecurityTokenRequirement%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>-Methode. Diese Methode wird aufgerufen, von WCF, um die Sicherheitstokenparameter-Klasse-Instanz in eine Instanz von konvertieren die <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> Klasse. Das Ergebnis wird von Sicherheitstokenanbietern zum Erstellen der entsprechenden Instanz des Sicherheitstokens verwendet.  
  
     [!code-csharp[c_CustomToken#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#2)]
     [!code-vb[c_CustomToken#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#2)]  
  
 Sicherheitstoken werden in SOAP-Nachrichten übertragen. Hierfür ist ein Übersetzungsmechanismus zwischen der Darstellung des Sicherheitstokens im Speicher und in der Übertragung erforderlich. WCF verwendet ein Sicherheitstoken-Serialisierungsprogramm für diese Aufgabe. Für jedes benutzerdefinierte Token muss ein benutzerdefiniertes Sicherheitstoken-Serialisierungsprogramm verfügbar sein, mit dem das benutzerdefinierte Sicherheitstoken aus der SOAP-Nachricht serialisiert bzw. deserialisiert werden kann.  
  
> [!NOTE]
>  Abgeleitete Schlüssel sind standardmäßig aktiviert. Wenn Sie ein benutzerdefiniertes Sicherheitstoken erstellen und verwenden Sie es als primäres Token verwendet, leitet WCF einen Schlüssel daraus. Dabei wird das Serialisierungsprogramm für benutzerdefnierte Sicherheitstoken aufgerufen, um die <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> für das benutzerdefinierte Sicherheitstoken zur Übertragung zu schreiben, während das `DerivedKeyToken` serialisiert wird. Auf der Empfangsseite erwartet das `DerivedKeyToken`-Serialisierungsprogramm beim Deserialisieren des Tokens aus der Übertragung ein `SecurityTokenReference`-Element als sich selbst untergeordnetes Element oberster Ebene. Wurde vom Serialisierungsprogramm für benutzerdefinierte Sicherheitstokens beim Serialisieren des eigenen Klauseltyps kein `SecurityTokenReference`-Element hinzugefügt, wird eine Ausnahme ausgelöst.  
  
#### <a name="to-create-a-custom-security-token-serializer"></a>So erstellen Sie ein benutzerdefiniertes Sicherheitstoken-Serialisierungsprogramm  
  
1.  Definieren Sie eine neue von der <xref:System.ServiceModel.Security.WSSecurityTokenSerializer>-Klasse abgeleitete Klasse.  
  
2.  Überschreiben Sie die <xref:System.ServiceModel.Security.WSSecurityTokenSerializer.CanReadTokenCore%28System.Xml.XmlReader%29>-Methode, die den XML-Stream mit dem <xref:System.Xml.XmlReader> liest. Diese Methode gibt `true` zurück, wenn das Sicherheitstoken für das aktuelle Element von der Implementierung des Serialisierungsprogramms deserialisiert werden kann. In diesem Beispiel überprüft die Methode, ob das aktuelle XML-Element des XML-Readers den richtigen Namen und den richtigen Namespace aufweist. Ist dies nicht der Fall, wird die Basisklassenimplementierung dieser Methode aufgerufen, um das XML-Element zu behandeln.  
  
3.  Überschreiben Sie die <xref:System.ServiceModel.Security.WSSecurityTokenSerializer.ReadTokenCore%28System.Xml.XmlReader%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%29>-Methode. Diese Methode wird zum Lesen des XML-Inhalts des Sicherheitstokens sowie zum Erstellen der entsprechenden Darstellung im Speicher verwendet. Wenn das XML-Element, das gerade vom übergebenen XML-Reader erfasst wird, von der Methode nicht erkannt wird, wird die Basisklassenimplementierung zur Verarbeitung der vom System bereitgestellten Tokentypen aufgerufen.  
  
4.  Überschreiben Sie die <xref:System.ServiceModel.Security.WSSecurityTokenSerializer.CanWriteTokenCore%28System.IdentityModel.Tokens.SecurityToken%29>-Methode. Diese Methode gibt `true` zurück, wenn die (als Argument übergebene) Darstellung des Tokens im Speicher in die XML-Darstellung konvertiert werden kann. Wenn dies nicht der Fall ist, wird die Basisklassenimplementierung aufgerufen.  
  
5.  Überschreiben Sie die <xref:System.ServiceModel.Security.WSSecurityTokenSerializer.WriteTokenCore%28System.Xml.XmlWriter%2CSystem.IdentityModel.Tokens.SecurityToken%29>-Methode. Diese Methode konvertiert die Darstellung eines Sicherheitstokens im Speicher in eine XML-Darstellung. Andernfalls wird die Basisklassenimplementierung aufgerufen.  
  
     [!code-csharp[c_CustomToken#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#3)]
     [!code-vb[c_CustomToken#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#3)]  
  
 Integrieren Sie das benutzerdefinierte Sicherheitstoken nach Abschluss dieser vier Verfahren in den Anbieter, Authentifizierer, Manager und Client sowie in die Anmeldeinformationen des Diensts für das Sicherheitstoken.  
  
#### <a name="to-integrate-the-custom-security-token-with-a-security-token-provider"></a>So integrieren Sie das benutzerdefinierte Sicherheitstoken in einen Sicherheitstokenanbieter  
  
1.  Der Sicherheitstokenanbieter erstellt das Token, ändert es gegebenenfalls und gibt eine Instanz des Tokens zurück. Um einen benutzerdefinierten Anbieter für das benutzerdefinierte Sicherheitstoken zu erstellen, erstellen Sie eine Klasse, die von der <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Klasse erbt. Im folgenden Beispiel wird die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>-Methode überschrieben, um eine Instanz von `CreditCardToken` zurückzugeben. Weitere Informationen zu benutzerdefinierten sicherheitstokenanbietern finden Sie unter [Vorgehensweise: Erstellen Sie einen benutzerdefinierten Sicherheitstokenanbieter](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomToken#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#6)]
     [!code-vb[c_CustomToken#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#6)]  
  
#### <a name="to-integrate-the-custom-security-token-with-a-security-token-authenticator"></a>So integrieren Sie das benutzerdefinierte Sicherheitstoken in einen Sicherheitstokenauthentifizierer  
  
1.  Der Sicherheitstokenauthentifizierer überprüft den Inhalt des Sicherheitstokens beim Extrahieren aus der Nachricht. Um einen benutzerdefinierten Authentifizierer für das benutzerdefinierte Sicherheitstoken zu erstellen, erstellen Sie eine Klasse, die von der <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>-Klasse erbt. Im folgenden Beispiel wird die <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.ValidateTokenCore%2A>-Methode überschrieben. Weitere Informationen zu benutzerdefinierten sicherheitstokenauthentifizierern finden Sie unter [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md).  
  
     [!code-csharp[c_CustomToken#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#7)]
     [!code-vb[c_CustomToken#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#7)]  
  
     [!code-csharp[c_CustomToken#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#12)]
     [!code-vb[c_CustomToken#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#12)]  
  
#### <a name="to-integrate-the-custom-security-token-with-a-security-token-manager"></a>So integrieren Sie das benutzerdefinierte Sicherheitstoken in einen Sicherheitstoken-Manager  
  
1.  Der Sicherheitstoken-Manager erstellt die entsprechenden Instanzen für den Anbieter, den Sicherheitsauthentifizierer und das Serialisierungsprogramm für das Token. Zum Erstellen eines Managers für das benutzerdefinierte Token erstellen Sie eine Klasse, die von der <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>-Klasse erbt. Die primären Methoden der Klasse erstellen den entsprechenden Anbieter und den entsprechenden Client oder die entsprechenden Anmeldeinformationen für den Dienst mit einer <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>. Weitere Informationen zu benutzerdefinierten Sicherheitstoken-Managern, finden Sie unter [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomToken#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#8)]
     [!code-vb[c_CustomToken#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#8)]  
  
     [!code-csharp[c_CustomToken#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#9)]
     [!code-vb[c_CustomToken#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#9)]  
  
#### <a name="to-integrate-the-custom-security-token-with-custom-client-and-service-credentials"></a>So integrieren Sie das benutzerdefinierte Sicherheitstoken in den benutzerdefinierten Client und die benutzerdefinierten Anmeldeinformationen des Diensts  
  
1.  Der benutzerdefinierte Client und die benutzerdefinierten Anmeldeinformationen für den Dienst müssen hinzugefügt werden, damit eine API für die Anwendung Informationen zum benutzerdefinierten Token angeben kann, die von der zuvor erstellten Infrastruktur für das benutzerdefinierte Sicherheitstoken zur Bereitstellung und Authentifizierung von Inhalten für das benutzerdefinierte Sicherheitstoken verwendet werden können. Die folgenden Beispiele veranschaulichen diese Vorgehensweise. Weitere Informationen zu benutzerdefinierten Client- und Dienstanmeldeinformationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomToken#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#10)]
     [!code-vb[c_CustomToken#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#10)]  
  
     [!code-csharp[c_customToken#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#11)]
     [!code-vb[c_customToken#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#11)]  
  
 Die benutzerdefinierte Sicherheitsrolle tokenparameter-Klasse, die erstellt wird zuvor für die WCF-Sicherheit-Framework mitzuteilen, dass ein benutzerdefiniertes Sicherheitstoken verwendet werden muss, bei der Kommunikation mit einem Dienst verwendet. Das folgende Verfahren veranschaulicht die Vorgehensweise.  
  
#### <a name="to-integrate-the-custom-security-token-with-the-binding"></a>So integrieren Sie das benutzerdefinierte Sicherheitstoken in die Bindung  
  
1.  Die Parameterklasse für das benutzerdefinierte Sicherheitstoken muss in einer der Tokenparameterauflistungen angegeben werden, die für die <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse verfügbar gemacht werden. Im folgenden Beispiel wird die Auflistung verwendet, die von `SignedEncrypted` zurückgegeben wird. Mit diesem Code wird jeder Nachricht, die vom Client an den Dienst gesendet wird, das benutzerdefinierte Kreditkartentoken hinzugefügt, und der Inhalt wird automatisch signiert und verschlüsselt.  
  
     [!code-csharp[c_CustomToken#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#13)]
     [!code-vb[c_CustomToken#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#13)]  
  
 In diesem Thema werden die verschiedenen Codeteile behandelt, die zur Implementierung und Verwendung benutzerdefinierter Token erforderlich sind. Um ein vollständiges Beispiel finden Sie unter zusammenarbeiten all diese Teile des Codes finden Sie unter [benutzerdefinierte Token](../../../../docs/framework/wcf/samples/custom-token.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Tokens.SecurityToken>  
 <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters>  
 <xref:System.ServiceModel.Security.WSSecurityTokenSerializer>  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
 [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 [Sicherheitsarchitektur](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
