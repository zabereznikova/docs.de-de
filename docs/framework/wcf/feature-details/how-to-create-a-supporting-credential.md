---
title: 'Vorgehensweise: Erstellen unterstützender Anmeldeinformationen'
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: 1e11da11de68b1d3e24115387ec61ad22ec031b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286304"
---
# <a name="how-to-create-a-supporting-credential"></a>Vorgehensweise: Erstellen unterstützender Anmeldeinformationen

Sie können über ein benutzerdefiniertes Sicherheitsschema verfügen, für das mehrere Anmeldeinformationen erforderlich sind. Beispielsweise kann ein Dienst vom Client nicht nur den Benutzernamen und das Kennwort fordern, sondern auch Anmeldeinformationen, die belegen, dass der Client älter als 18 Jahre ist. Die zweiten Anmelde Informationen sind *unterstützende* Anmelde Informationen. In diesem Thema wird erläutert, wie solche Anmelde Informationen in einem Windows Communication Foundation (WCF)-Client implementiert werden.  
  
> [!NOTE]
> Die Spezifikation für unterstützende Anmeldeinformationen ist Teil der WS-SecurityPolicy-Spezifikation. Weitere Informationen finden Sie unter [Webdienstesicherheit Spezifikationen](/previous-versions/dotnet/articles/ms951273(v=msdn.10)).  
  
## <a name="supporting-tokens"></a>Unterstützende Token  

 Kurz gesagt: Wenn Sie Nachrichten Sicherheit verwenden, wird immer eine *primäre* Anmelde Information verwendet, um die Nachricht zu sichern (z. b. ein X. 509-Zertifikat oder ein Kerberos-Ticket).  
  
 Gemäß der Definition durch die Spezifikation verwendet eine Sicherheitsbindung *Token* , um den Nachrichtenaustausch zu sichern. Ein *Token* ist eine Darstellung von Sicherheits Anmelde Informationen.  
  
 Die Sicherheitsbindung verwendet zum Erstellen einer Signatur ein in ihrer Richtlinie identifiziertes primäres Token. Diese Signatur wird als *Nachrichten Signatur* bezeichnet.  
  
 Es können zusätzliche Token angegeben werden, um die von dem der Nachrichtensignatur zugeordneten Token bereitgestellten Ansprüche zu erweitern.  
  
## <a name="endorsing-signing-and-encrypting"></a>Unterzeichnen, Signieren und Verschlüsseln  

 Eine unterstützende Anmelde Informationen führt dazu, dass ein *unterstützendes Token* innerhalb der Nachricht übertragen wird Die WS-SecurityPolicy-Spezifikation definiert vier Methoden zum Anhängen eines unterstützenden Tokens an die Nachricht, wie in der folgenden Tabelle beschrieben.  
  
|Zweck|BESCHREIBUNG|  
|-------------|-----------------|  
|Signiert|Das unterstützende Token ist im Sicherheitsheader enthalten und wird durch die Nachrichtensignatur signiert.|  
|Unterzeichnend|Ein unter zeichnendes *Token* signiert die Nachrichten Signatur.|  
|Signiert und unterzeichnend|Signierte, unterzeichnende Token signieren das gesamte aus der Nachrichtensignatur erstellte `ds:Signature`-Element und werden selbst durch die Nachrichtensignatur signiert; d. h., beide Token (das für die Nachrichtensignatur verwendete Token und das signierte unterzeichnende Token) signieren einander.|  
|Signiert und verschlüsselnd|Signierte, verschlüsselte unterstützende Token sind signierte unterstützende Token, die beim Anzeigen im `wsse:SecurityHeader` auch verschlüsselt werden.|  
  
## <a name="programming-supporting-credentials"></a>Programmieren von unterstützenden Anmeldeinformationen  

 Um einen Dienst zu erstellen, der unterstützende Token verwendet, müssen Sie einen erstellen [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) . (Weitere Informationen finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).)  
  
 Der erste Schritt beim Erstellen einer benutzerdefinierten Bindung ist das Erstellen eines Sicherheitsbindungselements, das einer der folgenden drei Typen sein kann:  
  
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Alle Klassen erben vom <xref:System.ServiceModel.Channels.SecurityBindingElement>, das vier relevante Eigenschaften umfasst:  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a>Bereiche  

 Für unterstützende Anmeldeinformationen existieren vier Bereiche:  
  
- *Endpunkt unterstützende Token* unterstützen alle Vorgänge eines Endpunkts. Die Anmeldeinformationen, die das unterstützende Token darstellt, können beim Aufrufen eines beliebigen Endpunktvorgangs verwendet werden.  
  
- Unter *stützende Token* unterstützen nur einen bestimmten Endpunkt Vorgang.  
  
 Wie durch die Eigenschaftennamen angegeben, können unterstützende Anmeldeinformationen erforderlich oder optional sein. Die unterstützenden Anmeldeinformationen werden verwendet, wenn sie vorhanden, aber nicht erforderlich sind; die Authentifizierung schlägt jedoch nicht fehl, wenn sie nicht vorhanden sind.  
  
## <a name="procedures"></a>Prozeduren  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a>So erstellen Sie eine benutzerdefinierte Bindung, die unterstützende Anmeldeinformationen enthält  
  
1. Erstellen Sie ein Sicherheitsbindungselement. Im nachfolgenden Beispiel wird ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> mit dem `UserNameForCertificate`-Authentifizierungsmodus erstellt. Verwenden Sie die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>-Methode.  
  
2. Fügen Sie den unterstützenden Parameter der von der entsprechenden Eigenschaft (`Endorsing`, `Signed`, `SignedEncrypted` oder `SignedEndorsed`) zurückgegebenen Auflistung von Typen hinzu. Die Typen im <xref:System.ServiceModel.Security.Tokens>-Namespace umfassen häufig verwendete Typen wie die <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>BESCHREIBUNG  

 Im folgenden Beispiel wird eine Instanz des <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> erstellt und eine Instanz der <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters>-Klasse der von der unterzeichenden Eigenschaft zurückgegebenen Auflistung hinzugefügt.  
  
### <a name="code"></a>Code  

 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
