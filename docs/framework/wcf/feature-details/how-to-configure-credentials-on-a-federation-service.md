---
title: 'Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 149ab165-0ef3-490a-83a9-4322a07bd98a
ms.openlocfilehash: 05f35bbb7dbb34cd4067c407578038cbb4eff70f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599142"
---
# <a name="how-to-configure-credentials-on-a-federation-service"></a>Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst
In Windows Communication Foundation (WCF) besteht das Erstellen eines Verbund Dienstanbieter aus den folgenden Haupt Prozeduren:  
  
1. Konfigurieren einer <xref:System.ServiceModel.WSFederationHttpBinding> oder einer ähnlichen benutzerdefinierten Bindung. Weitere Informationen zum Erstellen einer entsprechenden Bindung finden Sie unter Gewusst [wie: Erstellen einer WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md).  
  
2. Konfigurieren von <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>, die kontrollieren, wie dem Dienst präsentierte ausgestellte Token authentifiziert werden.  
  
 Dieses Thema enthält Details über den zweiten Schritt. Weitere Informationen über die Funktionsweise eines Verbund Dienstanbieter finden Sie unter [Federation](federation.md).  
  
### <a name="to-set-the-properties-of-issuedtokenservicecredential-in-code"></a>So legen Sie die Eigenschaften von IssuedTokenServiceCredential in Code fest  
  
1. Verwenden Sie die <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>-Eigenschaft der <xref:System.ServiceModel.Description.ServiceCredentials>-Klasse, um einen Verweis an eine <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>-Instanz zurückzugeben. Der Zugriff auf die Eigenschaft erfolgt über die <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft der <xref:System.ServiceModel.ServiceHostBase>-Klasse.  
  
2. Legen Sie die- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowUntrustedRsaIssuers%2A> Eigenschaft auf fest, `true` Wenn selbst ausgestellte Token wie CardSpace-Karten authentifiziert werden sollen. Der Standardwert lautet `false`.  
  
3. Füllen Sie die von der <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>-Eigenschaft zurückgegebene Sammlung mit Instanzen der <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Klasse auf. Jede Instanz stellt einen Aussteller dar, von dem der Dienst Token authentifiziert.  
  
    > [!NOTE]
    > Im Gegensatz zur clientseitigen Sammlung, die von der <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>-Eigenschaft zurückgegeben wird, handelt es sich bei der Sammlung bekannter Zertifikate nicht um eine schlüsselgebundene Sammlung. Der Dienst akzeptiert die Token, die die angegebenen Zertifikate unabhängig von der Adresse des Clients, der die Nachricht mit dem ausgestellten Token gesendet hat, ausstellen (mit gewissen Einschränkungen, die später in diesem Thema beschrieben werden).  
  
4. Legen Sie die <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A>-Eigenschaft auf einen der <xref:System.ServiceModel.Security.X509CertificateValidationMode>-Enumerationswerte fest. Dies kann nur in Code erfolgen. Der Standardwert lautet <xref:System.IdentityModel.Selectors.X509CertificateValidator.ChainTrust%2A>.  
  
5. Wenn die <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> gesetzt ist, weisen Sie eine Instanz der benutzerdefinierten <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse zur <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>-Eigenschaft zu.  
  
6. Wenn <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> auf `ChainTrust` oder `PeerOrChainTrust` eingestellt ist, legen Sie die <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.RevocationMode%2A>-Eigenschaft auf einen entsprechenden Wert aus der <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>-Enumeration fest. Beachten Sie, dass der Sperrmodus nicht im `PeerTrust`-Validierungsmodus oder im `Custom`-Validierungsmodus verwendet wird.  
  
7. Weisen Sie, sofern erforderlich, eine Instanz einer benutzerdefinierten <xref:System.IdentityModel.Tokens.SamlSerializer>-Klasse zur <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.SamlSerializer%2A>-Eigenschaft zu. Ein benutzerdefiniertes SAML-Serialisierungsprogramm (Security Assertions Markup Language) wird benötigt, z. B. zum Analysieren von benutzerdefinierten SAML-Assertionen.  
  
### <a name="to-set-the-properties-of-issuedtokenservicecredential-in-configuration"></a>So legen Sie die Eigenschaften von IssuedTokenServiceCredential in der Konfiguration fest  
  
1. Erstellen Sie ein- `<issuedTokenAuthentication>` Element als untergeordnetes Element eines <`serviceCredentials`>-Elements.  
  
2. Legen Sie das- `allowUntrustedRsaIssuers` Attribut des- `<issuedTokenAuthentication>` Elements auf fest `true` , wenn Sie ein selbst ausgestelltes Token authentifizieren, z. b. eine CardSpace-Karte.  
  
3. Erstellen Sie ein `<knownCertificates>`-Element als untergeordnetes Element des `<issuedTokenAuthentication>`-Elements.  
  
4. Erstellen Sie null oder mehr `<add>``<knownCertificates>``storeLocation``storeName`-Attribut und dem -Attribut an, wie das Zertifikat zu finden ist.  
  
5. Legen Sie bei Bedarf das- `samlSerializer` Attribut des <`issuedTokenAuthentication`>-Elements auf den Typnamen der benutzerdefinierten <xref:System.IdentityModel.Tokens.SamlSerializer> Klasse fest.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Eigenschaften von <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> in Code festgelegt.  
  
 [!code-csharp[C_FederatedService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federatedservice/cs/source.cs#2)]
 [!code-vb[C_FederatedService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federatedservice/vb/source.vb#2)]  
  
 Damit ein Verbunddienst einen Client authentifizieren kann, muss Folgendes für das ausgestellte Token zutreffen:  
  
- Wenn die digitale Signatur des ausgestellten Tokens einen RSA-Sicherheitsschlüsselbezeichner verwendet, muss die <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowUntrustedRsaIssuers%2A>-Eigenschaft `true` lauten.  
  
- Wenn die Signatur des ausgestellten Tokens eine Seriennummer eines X.509-Ausstellers, einen Subjektschlüsselbezeichner des X.509-Zertifikats oder einen Fingerabdruck-Sicherheitsbezeichner des X.509-Zertifikats verwendet, muss das ausgestellte Token von einem Zertifikat in der Sammlung signiert sein, die von der <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>-Eigenschaft der <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>-Klasse zurückgegeben wurde.  
  
- Wenn das ausgestellte Token mit einem X.509-Zertifikat signiert ist, muss das Zertifikat anhand der semantischen Informationen validiert werden, die vom Wert der <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A>-Eigenschaft angegeben werden, unabhängig davon, ob das Zertifikat als <xref:System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause> an die vertrauende Seite gesendet wurde oder von der <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>-Eigenschaft stammt. Weitere Informationen zur Überprüfung des X. 509-Zertifikats finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md).  
  
 Durch Festlegen von <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerTrust> würde beispielsweise jedes ausgestellte Token, dessen Signaturzertifikat im `TrustedPeople`-Zertifikatspeicher abgelegt ist, authentifiziert werden. Legen Sie in diesem Fall die <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.TrustedStoreLocation%2A>-Eigenschaft entweder auf <xref:System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser> oder auf <xref:System.Security.Cryptography.X509Certificates.StoreLocation.LocalMachine> fest. Sie können andere Modi auswählen, einschließlich <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>. Bei Auswahl von `Custom` müssen Sie eine Instanz der <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse zur <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CustomCertificateValidator%2A>-Eigenschaft zuweisen. Das benutzerdefinierte Validierungssteuerelement kann Zertifikate mit allen beliebigen Kriterien überprüfen. Weitere Informationen finden Sie unter Vorgehens [Weise: Erstellen eines Dienstanbieter, der ein benutzerdefiniertes zertifikatvalidator verwendet](../extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Verbund](federation.md)
- [Verbund und Vertrauenswürdigkeit](federation-and-trust.md)
- [Verbundbeispiel](../samples/federation-sample.md)
- [Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Vorgehensweise: Erstellen einer WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md)
- [Vorgehensweise: Erstellen eines Verbundclients](how-to-create-a-federated-client.md)
- [Verwenden von Zertifikaten](working-with-certificates.md)
- [SecurityBindingElement-Authentifizierungsmodi](securitybindingelement-authentication-modes.md)
