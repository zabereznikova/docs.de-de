---
title: 'Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: 7c2eb820a7e087d99ebd2c463db6e10595f7c1da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119625"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a>Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet
In diesem Thema wird gezeigt, wie Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement implementieren und wie Sie Anmeldeinformationen für Clients oder Dienste konfigurieren, um die standardmäßige Zertifikatüberprüfungslogik durch das benutzerdefinierte Zertifikats-Validierungssteuerelement zu ersetzen.  
  
 Wenn das x. 509-Zertifikat verwendet wird, um einen Client oder Dienst zu authentifizieren, verwendet Windows Communication Foundation (WCF) wird standardmäßig die Windows-Zertifikatspeicher und die Kryptografie-API zum Überprüfen des Zertifikats und stellen Sie sicher, dass es vertrauenswürdig ist. Es kann vorkommen, dass die integrierten Funktionen zur Zertifikatsvalidierung nicht ausreichen und geändert werden müssen. WCF bietet eine einfache Möglichkeit zum Ändern der Validierungslogik, da Benutzer ein benutzerdefiniertes Zertifikats-Validierungssteuerelement hinzuzufügen. Wenn ein benutzerdefiniertes Zertifikats-Validierungssteuerelement angegeben wird, WCF nicht Validierungslogik integrierte Zertifikat, sondern verwendet stattdessen das benutzerdefinierte Validierungssteuerelement.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-create-a-custom-certificate-validator"></a>So erstellen Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement  
  
1.  Definieren Sie eine neue Klasse, die von <xref:System.IdentityModel.Selectors.X509CertificateValidator> abgeleitet ist.  
  
2.  Implementieren Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>-Methode. Das Zertifikat, das überprüft werden muss, wird als Argument an die Methode übergeben. Wenn das übergebene Zertifikat gemäß der Validierungslogik nicht gültig ist, löst diese Methode eine <xref:System.IdentityModel.Tokens.SecurityTokenValidationException> aus. Wenn das Zertifikat gültig ist, gibt die Methode einen Wert an den Aufrufer zurück.  
  
    > [!NOTE]
    >  Um dem Client Authentifizierungsfehler zurückzugeben, lösen Sie in der <xref:System.ServiceModel.FaultException>-Methode eine <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> aus.  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a>So geben Sie bei der Dienstkonfiguration ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an  
  
1.  Hinzufügen einer [ \<Verhaltensweisen >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element und ein [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf die [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element.  
  
2.  Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) und legen Sie die `name` -Attribut auf einen geeigneten Wert.  
  
3.  Hinzufügen einer [ \<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) auf die `<behavior>` Element.  
  
4.  Fügen Sie dem `<clientCertificate>`-Element ein `<serviceCredentials>`-Element hinzu.  
  
5.  Hinzufügen einer [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) auf die `<clientCertificate>` Element.  
  
6.  Legen Sie das `customCertificateValidatorType`-Attribut auf den Validierungssteuerelementtyp fest. Im folgenden Beispiel wird das Attribut auf den Namespace und den Namen des Typs festgelegt.  
  
7.  Legen Sie das `certificateValidationMode`-Attribut auf `Custom` fest.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a>So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie die Konfiguration auf dem Client verwenden  
  
1.  Hinzufügen einer [\<Verhaltensweisen >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element und ein [\<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf die [\<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element.  
  
2.  Hinzufügen einer [ \<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) Element.  
  
3.  Fügen Sie ein `<behavior>`name-Element hinzu, und legen Sie das`name`-Attribut auf einen passenden Wert fest.  
  
4.  Hinzufügen einer [ \<ClientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element.  
  
5.  Hinzufügen einer [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).  
  
6.  Hinzufügen einer [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) wie im folgenden Beispiel gezeigt.  
  
7.  Legen Sie das `customCertificateValidatorType`-Attribut auf den Validierungssteuerelementtyp fest.  
  
8.  Legen Sie das `certificateValidationMode`-Attribut auf `Custom` fest. Im folgenden Beispiel wird das Attribut auf den Namespace und den Namen des Typs festgelegt.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"   
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a>So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie Code auf der Dienstseite verwenden  
  
1.  Geben Sie das benutzerdefinierte Zertifikats-Validierungssteuerelement über die <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>-Eigenschaft an. Sie können auf die Dienstanmeldeinformationen mit der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft zugreifen.  
  
2.  Legen Sie die <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> -Eigenschaft auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>fest.  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a>So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie Code auf der Clientseite verwenden  
  
1.  Geben Sie das benutzerdefinierte Zertifikats-Validierungssteuerelement über die <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>-Eigenschaft an. Sie können auf die Clientanmeldeinformationen mit der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft zugreifen. (Die Client-Klasse, die vom [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) leitet sich immer von der <xref:System.ServiceModel.ClientBase%601> Klasse.)  
  
2.  Legen Sie die <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> -Eigenschaft auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>fest.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt eine Implementierung eines benutzerdefinierten Zertifikats-Validierungssteuerelements und seine Verwendung für den Dienst.  
  
### <a name="code"></a>Code  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
