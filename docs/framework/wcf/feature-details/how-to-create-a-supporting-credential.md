---
title: 'Vorgehensweise: Erstellen unterstützender Anmeldeinformationen'
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: 3ae2b59abf59b0256741ef4e908305d9f4350b4a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093708"
---
# <a name="how-to-create-a-supporting-credential"></a>Vorgehensweise: Erstellen unterstützender Anmeldeinformationen
Sie können über ein benutzerdefiniertes Sicherheitsschema verfügen, für das mehrere Anmeldeinformationen erforderlich sind. Beispielsweise kann ein Dienst vom Client nicht nur den Benutzernamen und das Kennwort fordern, sondern auch Anmeldeinformationen, die belegen, dass der Client älter als 18 Jahre ist. Anmeldeinformationen sind ein *unterstützende Anmeldeinformationen*. In diesem Thema wird erläutert, wie Sie solche Anmeldeinformationen in einem Windows Communication Foundation (WCF)-Client zu implementieren.  
  
> [!NOTE]
>  Die Spezifikation für unterstützende Anmeldeinformationen ist Teil der WS-SecurityPolicy-Spezifikation. Weitere Informationen finden Sie unter [Sicherheitsspezifikationen für Webdienste](https://go.microsoft.com/fwlink/?LinkId=88537).  
  
## <a name="supporting-tokens"></a>Unterstützende Token  
 Kurz gesagt, bei Verwendung von nachrichtensicherheit eine *primären Anmeldeinformationen* wird immer zum Sichern der Nachricht (z. B. ein x. 509-Zertifikat oder ein Kerberos-Ticket) verwendet.  
  
 Gemäß der Spezifikation, verwendet eine Bindung *Token* auf die Sicherung des Nachrichtenaustauschs. Ein *token* ist eine Darstellung von Sicherheitsanmeldeinformationen.  
  
 Die Sicherheitsbindung verwendet zum Erstellen einer Signatur ein in ihrer Richtlinie identifiziertes primäres Token. Diese Signatur wird als bezeichnet die *Nachrichtensignatur*.  
  
 Es können zusätzliche Token angegeben werden, um die von dem der Nachrichtensignatur zugeordneten Token bereitgestellten Ansprüche zu erweitern.  
  
## <a name="endorsing-signing-and-encrypting"></a>Unterzeichnen, Signieren und Verschlüsseln  
 Ergebnis unterstützender Anmeldeinformationen einem *unterstützendes Token* innerhalb der Nachricht übertragen. Die WS-SecurityPolicy-Spezifikation definiert vier Methoden zum Anhängen eines unterstützenden Tokens an die Nachricht, wie in der folgenden Tabelle beschrieben.  
  
|Zweck|Beschreibung|  
|-------------|-----------------|  
|Signiert|Das unterstützende Token ist im Sicherheitsheader enthalten und wird durch die Nachrichtensignatur signiert.|  
|Unterzeichnend|Ein *unterzeichnendes Token* die Nachrichtensignatur signiert.|  
|Signiert und unterzeichnend|Signierte, unterzeichnende Token signieren das gesamte aus der Nachrichtensignatur erstellte `ds:Signature`-Element und werden selbst durch die Nachrichtensignatur signiert; d. h., beide Token (das für die Nachrichtensignatur verwendete Token und das signierte unterzeichnende Token) signieren einander.|  
|Signiert und verschlüsselnd|Signierte, verschlüsselte unterstützende Token sind signierte unterstützende Token, die beim Anzeigen im `wsse:SecurityHeader` auch verschlüsselt werden.|  
  
## <a name="programming-supporting-credentials"></a>Programmieren von unterstützenden Anmeldeinformationen  
 Zum Erstellen eines Diensts, die unterstützende Token verwendet, müssen Sie erstellen, eine [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md). (Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)  
  
 Der erste Schritt beim Erstellen einer benutzerdefinierten Bindung ist das Erstellen eines Sicherheitsbindungselements, das einer der folgenden drei Typen sein kann:  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Alle Klassen erben vom <xref:System.ServiceModel.Channels.SecurityBindingElement>, das vier relevante Eigenschaften umfasst:  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a>Bereiche  
 Für unterstützende Anmeldeinformationen existieren vier Bereiche:  
  
-   *Endpunkt unterstützende Token* unterstützen alle Vorgänge eines Endpunkts. Die Anmeldeinformationen, die das unterstützende Token darstellt, können beim Aufrufen eines beliebigen Endpunktvorgangs verwendet werden.  
  
-   *Vorgang unterstützende Token* unterstützen nur einen bestimmten endpunktvorgang.  
  
 Wie durch die Eigenschaftennamen angegeben, können unterstützende Anmeldeinformationen erforderlich oder optional sein. Die unterstützenden Anmeldeinformationen werden verwendet, wenn sie vorhanden, aber nicht erforderlich sind; die Authentifizierung schlägt jedoch nicht fehl, wenn sie nicht vorhanden sind.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a>So erstellen Sie eine benutzerdefinierte Bindung, die unterstützende Anmeldeinformationen enthält  
  
1.  Erstellen Sie ein Sicherheitsbindungselement. Im nachfolgenden Beispiel wird ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> mit dem `UserNameForCertificate`-Authentifizierungsmodus erstellt. Verwenden Sie die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>-Methode.  
  
2.  Fügen Sie den unterstützenden Parameter der von der entsprechenden Eigenschaft (`Endorsing`, `Signed`, `SignedEncrypted` oder `SignedEndorsed`) zurückgegebenen Auflistung von Typen hinzu. Die Typen im <xref:System.ServiceModel.Security.Tokens>-Namespace umfassen häufig verwendete Typen wie die <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel wird eine Instanz des <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> erstellt und eine Instanz der <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters>-Klasse der von der unterzeichenden Eigenschaft zurückgegebenen Auflistung hinzugefügt.  
  
### <a name="code"></a>Code  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
