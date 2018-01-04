---
title: "SAML-Token und SAML-Ansprüche"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2b35ba4da503663a2bb92597ed193c408e7c99b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="saml-tokens-and-claims"></a>SAML-Token und SAML-Ansprüche
Security Assertions Markup Language (SAML) *Token* sind XML-Darstellungen von Ansprüchen. Standardmäßig werden von SAML-Token [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet in verbundsicherheitsszenarien werden *ausgestellte Token*.  
  
 SAML-Token enthalten Anweisungen, die Sets mit Ansprüchen sind, die von einer Entität über eine andere Entität gemacht wurden. In Verbundsicherheitsszenarien werden Anweisungen beispielsweise von einem Sicherheitstokendienst über einen Benutzer im System getroffen. Der Sicherheitstokendienst signiert das SAML-Token, um die Richtigkeit der Anweisungen im Token zu bestätigen. Darüber hinaus ist das SAML-Token kryptografischen Schlüsselmaterialien zugewiesen, wobei der Benutzer des SAML-Tokens beweisen muss, dass er um diese Materialien weiß. Dieser Beleg reicht aus, um die vertrauende Seite zu überzeugen, dass das SAML-Token tatsächlich für diesen Benutzer ausgestellt wurde. Ein typisches Szenario sieht folgendermaßen aus:  
  
1.  Ein Client fordert einen SAML-Token von einem Sicherheitstokendienst an, wobei er sich bei diesem Dienst mit den Windows-Anmeldeinformationen authentifiziert.  
  
2.  Der Sicherheitstokendienst stellt dem Client einen SAML-Token aus. Das SAML-Token wird mit einem dem Sicherheitstokendienst zugewiesenen Zertifikat signiert und enthält einen Prüfschlüssel, der für den Zieldienst verschlüsselt wurde.  
  
3.  Der Client empfängt auch eine Kopie der *Prüfschlüssel*. Der Client stellt dann das SAML-Token an den Anwendungsdienst (der *vertrauende*) und signiert die Nachricht mit diesem Prüfschlüssel.  
  
4.  Die Signatur über dem SAML-Token zeigt der vertrauenden Seite, dass der Sicherheitstokendienst das Token ausgestellt hat. Die mit dem Prüfschlüssel erstellte Nachrichtensignatur zeigt der vertrauenden Seite, dass das Token für den Client ausgestellt wurde.  
  
## <a name="from-claims-to-samlattributes"></a>Von Ansprüchen zu SamlAttributes  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden Anweisungen in SAML-Token als <xref:System.IdentityModel.Tokens.SamlAttribute>-Objekte modelliert, die direkt aus <xref:System.IdentityModel.Claims.Claim>-Objekten gefüllt werden können, vorausgesetzt das <xref:System.IdentityModel.Claims.Claim>-Objekt hat die<xref:System.IdentityModel.Claims.Claim.Right%2A>-Eigenschaft des Typs <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> und die <xref:System.IdentityModel.Claims.Claim.Resource%2A>-Eigenschaft des Typs <xref:System.String>. Zum Beispiel:  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
>  Wenn SAML-Token in Nachrichten serialisiert werden, z. B. wenn sie von einem Sicherheitstokendienst ausgestellt werden oder von Clients im Rahmen der Authentifizierung an Dienste gegeben werden, muss das Kontingent für die maximale Nachrichtengröße groß genug sein, um das SAML-Token und die anderen Teile der Nachricht aufnehmen zu können. Normalerweise ist das Kontingent für Nachrichten in Standardgröße ausreichend. Wenn jedoch ein SAML-Token sehr groß ist, da es mehrere Hundert Ansprüche enthält, müssen Sie u. U. das Kontingent vergrößern, um das serialisierte Token aufnehmen zu können. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Sicherheitsüberlegungen zu Daten](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).  
  
## <a name="from-samlattributes-to-claims"></a>Von SamlAttributes zu Ansprüchen  
 Wenn SAML-Token in Nachrichten empfangen werden, werden die unterschiedlichen Anweisungen im SAML-Token in <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Objekte umgewandelt, die in den <xref:System.IdentityModel.Policy.AuthorizationContext> gesetzt werden. Die Ansprüche aus jeder SAML-Anweisung werden von der <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A>-Eigenschaft des <xref:System.IdentityModel.Policy.AuthorizationContext> zurückgegeben und können überprüft werden, um zu bestimmen, ob der Benutzer authentifiziert und autorisiert werden soll  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Policy.AuthorizationContext>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 <xref:System.IdentityModel.Claims.ClaimSet>  
 [Verbund](../../../../docs/framework/wcf/feature-details/federation.md)  
 [Vorgehensweise: Erstellen eines Verbundclients](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [Ansprüche und Token](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)  
 [Erstellen von Ansprüchen und Ressourcenwerte](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
