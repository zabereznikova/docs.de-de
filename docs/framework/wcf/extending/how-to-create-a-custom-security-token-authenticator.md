---
title: 'Gewusst wie: Erstellen eines benutzerdefinierten Sicherheitstoken-Authentifizierungsators'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: 10e245f7-d31e-42e7-82a2-d5780325d372
ms.openlocfilehash: 7bbe59958f59f76046c0a112463cfa64d09c14d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185592"
---
# <a name="how-to-create-a-custom-security-token-authenticator"></a>Gewusst wie: Erstellen eines benutzerdefinierten Sicherheitstoken-Authentifizierungsators
In diesem Thema wird beschrieben, wie Sie einen benutzerdefinierten Sicherheitstokenauthentifizierer erstellen und in einen benutzerdefinierten Sicherheitstoken-Manager integrieren. Ein Sicherheitstokenauthentifizierer überprüft den Inhalt eines Sicherheitstokens, das mit einer eingehenden Nachricht bereitgestellt wird. Bei erfolgreicher Validierung gibt der Authentifizierer eine Sammlung von <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Instanzen zurück, die nach der Auswertung einen Satz von Ansprüchen zurückgeben.  
  
 Um einen benutzerdefinierten Sicherheitstokenautheator in Windows Communication Foundation (WCF) zu verwenden, müssen Sie zunächst benutzerdefinierte Anmeldeinformationen und Implementierungen des Sicherheitstoken-Managers erstellen. Weitere Informationen zum Erstellen benutzerdefinierter Anmeldeinformationen und eines Sicherheitstoken-Managers finden Sie unter [Exemplarische Vorgehensweise: Erstellen benutzerdefinierter Client- und Dienstanmeldeinformationen](walkthrough-creating-custom-client-and-service-credentials.md).
  
## <a name="procedures"></a>Prozeduren  
  
#### <a name="to-create-a-custom-security-token-authenticator"></a>So erstellen Sie einen benutzerdefinierten Sicherheitstokenauthentifizierer  
  
1. Definieren Sie eine neue von der <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>-Klasse abgeleitete Klasse.  
  
2. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateTokenCore%2A> -Methode. Die Methode gibt `true` oder `false` zurück, je nachdem, ob der benutzerdefinierte Authentifizierer den eingehenden Tokentyp auswerten kann oder nicht.  
  
3. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.ValidateTokenCore%2A> -Methode. Diese Methode muss den Tokeninhalt entsprechend überprüfen. Wenn das Token den Validierungsschritt übergibt, gibt es eine Auflistung von <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Instanzen zurück. Im folgenden Beispiel wird eine benutzerdefinierte Autorisierungsrichtlinienimplementierung, die in der nächsten Prozedur erstellt wird, verwendet.  
  
     [!code-csharp[C_CustomTokenAuthenticator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#1)]
     [!code-vb[C_CustomTokenAuthenticator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#1)]  
  
 Der vorherige Code gibt eine Auflistung von Autorisierungsrichtlinien in der <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateToken%28System.IdentityModel.Tokens.SecurityToken%29>-Methode zurück. WCF stellt keine öffentliche Implementierung dieser Schnittstelle bereit. Die folgende Prozedur zeigt, wie Sie diese Schritte Ihren eigenen Anforderungen entsprechend ausführen.  
  
#### <a name="to-create-a-custom-authorization-policy"></a>So erstellen Sie eine benutzerdefinierte Autorisierungsrichtlinie  
  
1. Definieren Sie eine neue Klasse, die die <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Schnittstelle implementiert.  
  
2. Implementieren Sie die schreibgeschützte <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A>-Eigenschaft. Eine Möglichkeit, diese Eigenschaft zu implementieren, besteht darin, eine GUID (Globally Unique Identifier) im Klassenkonstruktor zu generieren und jedes Mal zurückzugeben, wenn der Wert für diese Eigenschaft angefordert wird.  
  
3. Implementieren Sie die schreibgeschützte <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A>-Eigenschaft. Diese Eigenschaft muss einen Aussteller der Sätze von Ansprüchen zurückgeben, die aus dem Token abgerufen werden. Dieser Aussteller sollte dem Aussteller des Tokens oder einer Autorität entsprechen, die für die Überprüfung der Tokeninhalte zuständig ist. Im folgenden Beispiel wird der Ausstelleranspruch, der von dem in der vorherigen Prozedur erstellten benutzerdefinierten Sicherheitstokenauthentifizierer an diese Klasse übergeben wird, verwendet. Der benutzerdefinierte Sicherheitstokenauthentifizierer nutzt den vom System bereitgestellten Satz von Ansprüchen (der von der <xref:System.IdentityModel.Claims.ClaimSet.System%2A>-Eigenschaft zurückgegeben wird), um den Aussteller des Benutzernamentokens darzustellen.  
  
4. Implementieren Sie die <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A>-Methode. Diese Methode füllt eine Instanz der <xref:System.IdentityModel.Policy.EvaluationContext>-Klasse (die als Argument weitergegeben wurde) mit Ansprüchen auf, die auf dem eingehenden Sicherheitstokeninhalt basieren. Die Methode gibt `true` zurück, wenn der Vorgang mit der Evaluierung vorgenommen wird. In Fällen, in denen die Implementierung vom Vorhandensein anderer Autorisierungsrichtlinien abhängt, die zusätzliche Informationen zum Evaluierungskontext bieten, kann diese Methode `false` zurückgeben, wenn die erforderlichen Informationen noch nicht im Evaluierungskontext vorhanden sind. In diesem Fall ruft WCF die Methode erneut auf, nachdem alle anderen Autorisierungsrichtlinien ausgewertet wurden, die für die eingehende Nachricht generiert wurden, wenn mindestens eine dieser Autorisierungsrichtlinien den Evaluierungskontext geändert hat.  
  
     [!code-csharp[c_CustomTokenAuthenticator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#3)]
     [!code-vb[c_CustomTokenAuthenticator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#3)]  

 [Exemplarische Vorgehensweise: Beim Erstellen benutzerdefinierter Client- und Dienstanmeldeinformationen](walkthrough-creating-custom-client-and-service-credentials.md) wird beschrieben, wie benutzerdefinierte Anmeldeinformationen und ein benutzerdefinierter Sicherheitstoken-Manager erstellt werden. Zur Verwendung des hier erstellten benutzerdefinierten Sicherheitstokenauthentifizierers wird eine Implementierung des Sicherheitstoken-Managers so geändert, dass der benutzerdefinierte Authentifizierer von der <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A>-Methode zurückgegeben wird. Die Methode gibt einen Authentifizierer zurück, wenn eine entsprechende Sicherheitstokenanforderung übergeben wird.  
  
#### <a name="to-integrate-a-custom-security-token-authenticator-with-a-custom-security-token-manager"></a>So integrieren Sie einen benutzerdefinierten Sicherheitstokenauthentifizierer mit einem benutzerdefinierten Sicherheitstoken-Manager  
  
1. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A>-Methode in der benutzerdefinierten Sicherheitstoken-Manager-Implementierung.  
  
2. Fügen Sie Logik zur Methode hinzu, um diese zu befähigen, Ihren benutzerdefinierten Sicherheitstokenauthentifizierer basierend auf dem <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>-Parameter zurückzugeben. Im folgenden Beispiel wird ein benutzerdefinierter Sicherheitstokenauthentifizierer zurückgegeben, wenn der Tokentyp der Tokenanforderungen ein Benutzername ist (der von der <xref:System.IdentityModel.Tokens.SecurityTokenTypes.UserName%2A>-Eigenschaft dargestellt wird) und die Nachrichtenrichtung, für die der Sicherheitstokenauthentifizierer angefordert wird, eingegeben wird (dargestellt durch das <xref:System.ServiceModel.Description.MessageDirection.Input>-Feld).  
  
     [!code-csharp[c_CustomTokenAuthenticator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#2)]
     [!code-vb[c_CustomTokenAuthenticator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#2)]  

## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.UserNameSecurityToken>
- [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](walkthrough-creating-custom-client-and-service-credentials.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](how-to-create-a-custom-security-token-provider.md)
