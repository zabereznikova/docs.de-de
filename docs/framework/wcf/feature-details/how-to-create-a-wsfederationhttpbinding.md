---
title: "Vorgehensweise: Erstellen einer WSFederationHttpBinding | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Verbund"
  - "WCF, Verbund"
ms.assetid: e54897d7-aa6c-46ec-a278-b2430c8c2e10
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Vorgehensweise: Erstellen einer WSFederationHttpBinding
In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] stellt die <xref:System.ServiceModel.WSFederationHttpBinding>\-Klasse \([\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) in der Konfiguration\) einen Mechanismus bereit, um einen Verbunddienst verfügbar zu machen.  Hierbei handelt es sich um einen Dienst, der eine Clientauthentifizierung mithilfe eines von einem Sicherheitstokendienst ausgestellten Sicherheitstokens erfordert.  In diesem Thema wird erläutert, wie <xref:System.ServiceModel.WSFederationHttpBinding> sowohl im Code als auch in der Konfiguration eingerichtet werden kann.  Nach dem Erstellen der Bindung können Sie einen Endpunkt einrichten, von dem diese Bindung verwendet wird.  
  
 Die folgenden grundlegenden Schritte sind erforderlich:  
  
1.  Wählen Sie einen Sicherheitsmodus aus.  Von <xref:System.ServiceModel.WSFederationHttpBinding> wird `Message` unterstützt, wodurch sogar über mehrere Hops hinweg eine End\-to\-End\-Sicherheit auf Nachrichtenebene erzielt wird. Zudem wird `TransportWithMessageCredential` unterstützt, um bei einer direkten HTTPS\-Verbindung zwischen Client und Dienst eine höhere Leistung zu erzielen.  
  
    > [!NOTE]
    >  Von <xref:System.ServiceModel.WSFederationHttpBinding> wird als Sicherheitsmodus auch `None` unterstützt.  Dieser Modus ist nicht sicher und wird nur zu Debuggingzwecken bereitgestellt.  Wird ein Dienstendpunkt mit einer <xref:System.ServiceModel.WSFederationHttpBinding> bereitgestellt, deren Sicherheitsmodus auf `None` festgelegt ist, ergibt sich für die Clientbindung \(die vom [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generiert wird\) eine <xref:System.ServiceModel.WsHttpBinding> mit dem Sicherheitsmodus `None`.  
  
     Im Gegensatz zu anderen vom System bereitgestellten Bindungen muss bei Verwendung von `WSFederationHttpBinding` kein Typ für die Clientanmeldeinformationen ausgewählt werden, da für die Anmeldeinformationen immer ein ausgestelltes Token verwendet wird.  Der Grund: Für die Clientanmeldeinformationen wird immer ein ausgestelltes Token verwendet.  Von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird ein Token von einem angegebenen Aussteller abgerufen und dem Dienst zur Authentifizierung des Clients vorgelegt.  
  
2.  Legen Sie auf Verbundclients die <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A>\-Eigenschaft auf die URL des Sicherheitstokendiensts fest.  Legen Sie <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A> auf die Bindung fest, die für die Kommunikation mit dem Sicherheitstokendienst verwendet werden soll.  
  
3.  Dies ist optional.  Legen Sie die <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A>\-Eigenschaft auf den Uniform Resource Identifier \(URI\) eines Tokentyps fest.  Geben Sie bei Verbunddiensten den Tokentyp an, der vom Dienst erwartet wird.  Geben Sie bei Verbundclients den Tokentyp an, der durch den Client vom Sicherheitstokendienst angefordert wird.  
  
     Ist kein Tokentyp angegeben, werden von den Clients WS\-Trust Request Security\-Tokens \(RSTs\) ohne Tokentyp\-URI generiert, und von den Diensten wird standardmäßig eine Clientauthentifizierung mithilfe eines SAML 1.1\-Tokens \(Security Assertions Markup Language\) erwartet.  
  
     Der URI für ein SAML 1.1\-Token lautet "http:\/\/docs.oasis\-open.org\/wss\/oasis\-wss SAML \#SAMLV1.1".  
  
4.  Dies ist optional.  Legen Sie bei Verbunddiensten die <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>\-Eigenschaft auf die Metadaten\-URL eines Sicherheitstokendiensts fest.  Der Metadatenendpunkt ermöglicht den Clients des Diensts das Auswählen eines geeigneten Bindungs\-\/Endpunktpaars, sofern der Dienst zum Veröffentlichen von Metadaten konfiguriert ist.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Veröffentlichen von Metadaten finden Sie unter [Veröffentlichen von Metadaten](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
 Auch andere Eigenschaften können festgelegt werden. Dazu zählen unter anderem der Schlüsseltyp, der im ausgestellten Token als Prüfschlüssel verwendet wird, die zwischen Client und Dienst verwendete Algorithmussuite, die Einstellung, ob die Dienstanmeldeinformationen ausgehandelt oder explizit angegeben werden, bestimmte Ansprüche, die vom Dienst im ausgestellten Token erwartet werden, sowie sämtliche zusätzliche XML\-Elemente, die der vom Client an den Sicherheitstokendienst gesendeten Anforderung hinzugefügt werden müssen.  
  
> [!NOTE]
>  Die `NegotiateServiceCredential`\-Eigenschaft ist nur relevant, wenn `SecurityMode` auf `Message` festgelegt ist.  Ist `SecurityMode` auf `TransportWithMessageCredential` festgelegt, wird die `NegotiateServiceCredential`\-Eigenschaft ignoriert.  
  
### So konfigurieren Sie WSFederationHttpBinding im Code  
  
1.  Erstellen Sie eine Instanz von <xref:System.ServiceModel.WSFederationHttpBinding>.  
  
2.  Legen Sie die <xref:System.ServiceModel.WSFederationHttpSecurity.Mode%2A>\-Eigenschaft gemäß Ihren Anforderungen auf <xref:System.ServiceModel.WSFederationHttpSecurityMode> oder <xref:System.ServiceModel.WSFederationHttpSecurityMode> fest.  Ist anstelle von <xref:System.ServiceModel.Security.SecurityAlgorithmSuite.Basic256%2A> eine andere Algorithmussuite erforderlich, legen Sie die <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.AlgorithmSuite%2A>\-Eigenschaft auf ein Werttoken von <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> fest.  
  
3.  Legen Sie die <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A>\-Eigenschaft auf einen geeigneten Wert fest.  
  
4.  Legen Sie die <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A>\-Eigenschaft gemäß Ihren Anforderungen auf <xref:System.IdentityModel.Tokens.SecurityKeyType> `SymmetricKey` oder .`AsymmetricKey` fest.  
  
5.  Legen Sie die <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A>\-Eigenschaft auf einen geeigneten Wert fest.  Ist kein Wert festgelegt, wird für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standardmäßig "http:\/\/docs.oasis\-open.org\/wss\/oasis\-wss\-saml\-token\-profile\-1.1\#SAMLV1.1" verwendet. Diese Einstellung steht für SAML 1.1\-Tokens.  
  
6.  Ist erforderlich für den Client, wenn kein lokaler Aussteller angegeben ist. Optional für den Dienst.  Erstellen Sie eine <xref:System.ServiceModel.EndpointAddress> mit der Adresse und den Identitätsinformationen des Sicherheitstokendiensts, und weisen Sie die <xref:System.ServiceModel.EndpointAddress>\-Instanz der <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A>\-Eigenschaft zu.  
  
7.  Erforderlich für den Client, wenn kein lokaler Aussteller angegeben ist. Wird nicht für den Dienst verwendet.  Erstellen Sie eine <xref:System.ServiceModel.Channels.Binding> für `SecurityTokenService`, und weisen Sie die <xref:System.ServiceModel.Channels.Binding>\-Instanz der <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A>\-Eigenschaft zu.  
  
8.  Wird nicht für den Client verwendet. Optional für den Dienst.  Erstellen Sie eine <xref:System.ServiceModel.EndpointAddress>\-Instanz für die Metadaten des Sicherheitstokendiensts, und weisen Sie sie der `IssuerMetadataAddress`\-Eigenschaft zu.  
  
9. Optional für Client und Dienst.  Erstellen Sie mindestens eine <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>\-Instanz, und fügen Sie sie der von der <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>\-Eigenschaft zurückgegebenen Auflistung hinzu.  
  
10. Optional für Client und Dienst.  Erstellen Sie mindestens eine <xref:System.Xml.XmlElement>\-Instanz, und fügen Sie sie der von der <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>\-Eigenschaft zurückgegebenen Auflistung hinzu.  
  
### So erstellen Sie einen Verbundendpunkt in der Konfiguration  
  
1.  Erstellen Sie ein [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) als untergeordnetes Element des [\<Bindungen\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)\-Elements in der Anwendungskonfigurationsdatei.  
  
2.  Erstellen Sie ein [\<Bindung\>](../../../../docs/framework/misc/binding.md)\-Element als untergeordnetes Element von [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md), und legen Sie das `name`\-Attribut auf einen geeigneten Wert fest.  
  
3.  Erstellen Sie ein `<security>`\-Element als untergeordnetes Element des [\<Bindung\>](../../../../docs/framework/misc/binding.md)\-Elements.  
  
4.  Legen Sie das `mode`\-Attribut des `<security>``Message-Elements gemäß Ihren Anforderungen auf` `TransportWithMessageCredential oder`  fest.  
  
5.  Erstellen Sie ein `<message>``<security>-Element als untergeordnetes Element des` \-Elements.  
  
6.  Dies ist optional.  Legen Sie das `algorithmSuite`\-Attribut des `<message>`\-Elements auf einen geeigneten Wert fest.  Die Standardeinstellung ist `Basic256`.  
  
7.  Dies ist optional.  Ist ein asymmetrischer Prüfschlüssel erforderlich, legen Sie das `issuedKeyType`\-Attribut des `<message>``AsymmetricKey-Elements auf`  fest.  Die Standardeinstellung ist `SymmetricKey`.  
  
8.  Dies ist optional.  Legen Sie das `issuedTokenType`\-Attribut des `<message>`\-Elements fest.  
  
9. Ist erforderlich für den Client, wenn kein lokaler Aussteller angegeben ist. Optional für den Dienst.  Erstellen Sie ein `<issuer>`\-Element als untergeordnetes Element des `<message>`\-Elements.  
  
10. Legen Sie das `address`\-Attribut auf das `<issuer>`\-Element fest, und geben Sie die Adresse an, unter der vom Sicherheitstokendienst Tokenanforderungen angenommen werden.  
  
11. Dies ist optional.  Fügen Sie ein untergeordnetes `<identity>`\-Element hinzu, und geben Sie die Identität des Sicherheitstokendiensts an.  
  
12. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
13. Erforderlich für den Client, wenn kein lokaler Aussteller angegeben ist. Wird nicht für den Dienst verwendet.  Erstellen Sie im Bindungsbereich ein [\<Bindung\>](../../../../docs/framework/misc/binding.md)\-Element, das für die Kommunikation mit dem Sicherheitstokendienst verwendet werden kann.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen einer Bindung finden Sie unter [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
14. Geben Sie die im vorangegangenen Schritt erstellte Bindung an, indem Sie das `binding`\-Attribut und das `bindingConfiguration`\-Attribut des `<issuer>`\-Elements festlegen.  
  
15. Wird nicht für den Client verwendet. Optional für den Dienst.  Erstellen Sie ein `<issuerMetadata>`\-Element als untergeordnetes Element des \<`message`\>\-Elements.  Geben Sie anschließend in einem `address`\-Attribut des `<issuerMetadata>`\-Elements die Adresse an, unter der die Metadaten des Sicherheitstokendiensts veröffentlicht werden.  Optional können Sie ein untergeordnetes `<identity>`\-Element hinzufügen und die Identität des Sicherheitstokendiensts angeben.  
  
16. Optional für Client und Dienst.  Fügen Sie ein `<claimTypeRequirements>`\-Element als untergeordnetes Element des `<message>`\-Elements hinzu.  Geben Sie erforderliche und optionale Ansprüche an, auf denen der Dienst beruht, indem Sie dem `<claimTypeRequirements>`\-Element [\<add\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)\-Elemente hinzufügen und den Anspruchstyp mithilfe des `claimType`\-Attributs angeben.  Geben Sie an, ob ein bestimmter Anspruch erforderlich oder optional ist, indem Sie das `isOptional`\-Attribut festlegen.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt einen Code zum imperativen Einrichten einer `WSFederationHttpBinding`.  
  
 [!code-csharp[c_FederationBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federationbinding/cs/source.cs#2)]
 <!-- TODO: review snippet reference [!code-vb[c_FederationBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federationbinding/vb/source.vb#2)]  -->  
  
## Siehe auch  
 [Verbund](../../../../docs/framework/wcf/feature-details/federation.md)   
 [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md)   
 [Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)