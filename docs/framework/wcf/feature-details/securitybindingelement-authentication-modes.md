---
title: "SecurityBindingElement-Authentifizierungsmodi | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 12300bf4-c730-4405-9f65-d286f68b5a43
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# SecurityBindingElement-Authentifizierungsmodi
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] stellt verschiedene Modi bereit, mit denen sich Clients und Dienste gegenseitig authentifizieren.Sie können Sicherheitsbindungselemente für diese Authentifizierungsmodi erstellen. Dazu verwenden Sie statische Methoden für die <xref:System.ServiceModel.Channels.SecurityBindingElement>\-Klasse oder führen eine entsprechende Konfiguration durch.In diesem Thema werden die 18 Authentifizierungsmodi kurz beschrieben.  
  
 Ein Beispiel für die Verwendung des Elements für einen der Authentifizierungsmodi finden Sie unter [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## Programmgesteuerte Konfiguration  
 Im folgenden Verfahren wird beschrieben, wie der Authentifizierungsmodus in einer Konfigurationsdatei festgelegt wird.  
  
#### So legen Sie den Authentifizierungsmodus in der Konfiguration fest  
  
1.  Fügen Sie dem [\<Bindungen\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)[\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)\-Element hinzu.  
  
2.  Fügen Sie dem `<customBinding>`\-Element ein [\<Bindung\>](../../../../docs/framework/misc/binding.md)\-Element als untergeordnetes Element hinzu.  
  
3.  Fügen Sie dem `<security>`\-Element ein `<binding>`\-Element hinzu.  
  
4.  Legen Sie das `authenticationMode`\-Attribut auf einen der unten beschriebenen Werte fest.Im folgenden Codebeispiel wird der Modus auf `AnonymousForCertificate` festgelegt.  
  
    ```  
    <bindings>  
      <customBinding>  
        <binding name="SecureCustomBinding">  
         <security authenticationMode ="AnonymousForCertificate" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
#### So legen Sie den Modus programmgesteuert fest  
  
1.  Beim Rückgabetyp kann es sich um einen der folgenden handeln: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> oder <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2.  Rufen Sie die entsprechende statische Methode der <xref:System.ServiceModel.Channels.SecurityBindingElement>\-Klasse auf.Im folgenden Codebeispiel wird die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>\-Methode aufgerufen.  
  
     [!code-csharp[c_CustomBindingsAuthMode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#3)]
     [!code-vb[c_CustomBindingsAuthMode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#3)]  
  
3.  Verwenden Sie das Bindungselement, um die benutzerdefinierte Bindung zu erstellen.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## Modusbeschreibungen  
  
### AnonymousForCertificate  
 In diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird über ein X.509\-Zertifikat authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>\-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.Legen Sie das `authenticationMode`\-Attribut des \<`security`\>\-Elements alternativ auf `AnonymousForCertificate` fest.  
  
### AnonymousForSslNegotiated  
 In diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird über ein X.509\-Zertifikat authentifiziert, das zur Laufzeit verhandelt wird.Das Sicherheitsbindungselement ist ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, das von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A>\-Methode zurückgegeben wird, wenn für den ersten Parameter der Wert `false` übergeben wird.Legen Sie das `authenticationMode`\-Attribut alternativ auf `AnonymousForSslNegotiated` fest.  
  
### CertificateOverTransport  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509\-Zertifikat, das an der SOAP\-Schicht als ausstellendes unterstützendes Token angezeigt wird, d. h. ein Token, das die Nachricht signiert.Der Dienst wird über ein X.509\-Zertifikat an der Transportschicht authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateCertificateOverTransportBindingElement%2A>\-Methode zurückgegebenes <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>.Legen Sie das `authenticationMode`\-Attribut alternativ auf `CertificateOverTransport` fest.  
  
### IssuedToken  
 Bei diesem Authentifizierungsmodus wird der Client nicht am Dienst selbst authentifiziert. Er wird stattdessen an einem Sicherheitstokendienst authentifiziert und empfängt ein SAML\-Token, das er dem Server als Beleg für den freigegebenen Schlüssel präsentiert.Der Dienst wird nicht am Client authentifiziert. Stattdessen verschlüsselt der Sicherheitstokendienst den freigegebenen Schlüssel als Teil des ausgestellten Tokens, sodass nur der Dienst den Schlüssel entschlüsseln kann.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>\-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.Legen Sie das `authenticationMode`\-Attribut alternativ auf `IssuedToken` fest.  
  
### IssuedTokenForCertificate  
 Bei diesem Authentifizierungsmodus wird der Client nicht am Dienst selbst authentifiziert. Er wird stattdessen an einem Sicherheitstokendienst authentifiziert und empfängt ein SAML\-Token, das er dem Server als Beleg für den freigegebenen Schlüssel präsentiert.Das ausgegebene Token wird an der SOAP\-Schicht als unterstützendes Token bzw. Bearer\-Token angezeigt, d. h. als ein Token, das die Nachricht signiert.Der Dienst authentifiziert sich dem Client gegenüber mit einem X.509\-Zertifikat.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>\-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.Legen Sie das `authenticationMode`\-Attribut alternativ auf `IssuedTokenForCertificate` fest.  
  
### IssuedTokenForSslNegotiated  
 Bei diesem Authentifizierungsmodus wird der Client nicht am Dienst selbst authentifiziert. Er wird stattdessen an einem Sicherheitstokendienst authentifiziert und empfängt ein SAML\-Token, das er dem Server als Beleg für den freigegebenen Schlüssel präsentiert.Das ausgegebene Token wird an der SOAP\-Schicht als unterstützendes Token bzw. Bearer\-Token angezeigt, d. h. als ein Token, das die Nachricht signiert.Der Dienst wird mit einem X.509\-Zertifikat authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>\-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.Legen Sie das `authenticationMode`\-Attribut alternativ auf `IssuedTokenForSslnegotiated` fest.  
  
### IssuedTokenOverTransport  
 Bei diesem Authentifizierungsmodus wird der Client nicht am Dienst selbst authentifiziert. Er wird stattdessen an einem Sicherheitstokendienst authentifiziert und empfängt ein SAML\-Token, das er dem Server als Beleg für den freigegebenen Schlüssel präsentiert.Das ausgegebene Token wird an der SOAP\-Schicht als unterstützendes Token bzw. Bearer\-Token angezeigt, d. h. als ein Token, das die Nachricht signiert.Der Dienst wird über ein X.509\-Zertifikat auf der Transportschicht authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>\-Methode zurückgegebenes `TransportSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `IssuedTokenOverTransport` fest.  
  
### Kerberos  
 In diesem Authentifizierungsmodus wird der Client über ein Kerberos\-Ticket am Dienst authentifiziert.Dieses Ticket bietet auch eine Serverauthentifizierung.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A>\-Methode zurückgegebenes `SymmetricSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `Kerberos` fest.  
  
> [!NOTE]
>  Um diesen Authentifizierungsmodus zu verwenden, muss dem Dienstkonto ein Dienstprinzipalname zugeordnet sein.Führen Sie den Dienst zu diesem Zweck unter dem Konto NETZWERKDIENST oder dem Konto LOKALES SYSTEM aus.Verwenden Sie andernfalls das Tool SetSpn.exe, um einen Dienstprinzipalnamen für das Dienstkonto zu erstellen.Der Client muss auf jeden Fall den korrekten Dienstprinzipalnamen im [\<servicePrincipalName\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md)\-Element oder den <xref:System.ServiceModel.EndpointAddress>\-Konstruktor verwenden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
> [!NOTE]
>  Wenn der `Kerberos`\-Authentifizierungsmodus verwendet wird, werden die <xref:System.Security.Principal.TokenImpersonationLevel>\-Ebene und die <xref:System.Security.Principal.TokenImpersonationLevel>\-Ebene des Identitätswechsels nicht unterstützt.  
  
### KerberosOverTransport.  
 In diesem Authentifizierungsmodus wird der Client über ein Kerberos\-Ticket am Dienst authentifiziert.Das Kerberos\-Token wird an der SOAP\-Schicht als unterstützendes Token angezeigt, d. h. ein Token, das die Nachricht signiert.Der Dienst wird über ein X.509\-Zertifikat an der Transportschicht authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosOverTransportBindingElement%2A>\-Methode zurückgegebenes `TransportSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `KerberosOverTransport` fest.  
  
> [!NOTE]
>  Um diesen Authentifizierungsmodus zu verwenden, muss dem Dienstkonto ein Dienstprinzipalname zugeordnet sein.Führen Sie den Dienst zu diesem Zweck unter dem Konto NETZWERKDIENST oder dem Konto LOKALES SYSTEM aus.Verwenden Sie andernfalls das Tool SetSpn.exe, um einen Dienstprinzipalnamen für das Dienstkonto zu erstellen.Der Client muss auf jeden Fall den korrekten Dienstprinzipalnamen im [\<servicePrincipalName\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md)\-Element oder den <xref:System.ServiceModel.EndpointAddress>\-Konstruktor verwenden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
### MutualCertificate  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509\-Zertifikat, das an der SOAP\-Schicht als ausstellendes unterstützendes Token angezeigt wird, d. h. ein Token, das die Nachricht signiert.Der Dienst wird auch mit einem X.509\-Zertifikat authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>\-Methode zurückgegebenes `SymmetricSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `MutualCertificate` fest.  
  
### MutualCertificateDuplex  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509\-Zertifikat, das an der SOAP\-Schicht als ausstellendes unterstützendes Token angezeigt wird, d. h. ein Token, das die Nachricht signiert.Der Dienst wird auch über ein X.509\-Zertifikat authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateDuplexBindingElement%2A>\-Methode zurückgegebenes `AsymmetricSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `MutualCertificateDuplex` fest.  
  
### MutalSslNegotiation  
 In diesem Authentifizierungsmodus werden sowohl der Client als auch der Dienst über X.509\-Zertifikate authentifiziert.Das Sicherheitsbindungselement ist ein `SymmetricSecurityBindingElement`, das von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A>\-Methode zurückgegeben wird, wenn für den ersten Parameter der Wert `true` übergeben wird.Legen Sie das `authenticationMode`\-Attribut alternativ auf `MutualSslNegotiated` fest.  
  
### SecureConversation  
 Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>\-Methode zurückgegebenes `SymmetricSecurityBindingElement`.Diese Methode verwendet ein <xref:System.ServiceModel.Channels.SecurityBindingElement> als Parameter, der während der Initialisierung zum Erstellen der sicheren Sitzung verwendet wird.Legen Sie das `authenticationMode`\-Attribut alternativ auf `SecureConversation` fest.  
  
 Falls keine Bootstrapbindung angegeben ist, wird der `SspiNegotiated`\-Authentifizierungsmodus verwendet.  
  
### SspiNegotiation  
 In diesem Authentifizierungsmodus wird ein Aushandlungsprotokoll für die Client\- und Serverauthentifizierung verwendet.Falls möglich, wird Kerberos verwendet, andernfalls NTLM.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%2A>\-Methode zurückgegebenes `SymmetricSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `SspiNegotiated` fest.  
  
### SspiNegotiatedOverTransport  
 In diesem Authentifizierungsmodus wird ein Aushandlungsprotokoll für die Client\- und Serverauthentifizierung verwendet.Falls möglich, wird Kerberos verwendet, andernfalls NTLM.Das resultierende Token wird an der SOAP\-Schicht als unterstützendes Token angezeigt, d. h. ein Token, das die Nachricht signiert.Der Dienst wird zusätzlich über ein X.509\-Zertifikat an der Transportschicht authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationOverTransportBindingElement%2A>\-Methode zurückgegebenes `TransportSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `SspiNegotiatedOverTransport` fest.  
  
### UserNameForCertificate  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das an der SOAP\-Schicht als signiertes unterstützendes Token angezeigt wird. Dieses Token wird von der Nachrichtensignatur signiert.Der Dienst authentifiziert sich über ein X.509\-Zertifikat am Client.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>\-Methode zurückgegebenes `SymmetricSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `UserNameForCertificate` fest.  
  
 Für den `UserNameForCertificate`\-Authentifizierungsmodus müssen sowohl der Client als auch der Dienst WS\-Sicherheit 1.1 verwenden.  
  
### UserNameForSslNegotiated  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das an der SOAP\-Schicht als signiertes unterstützendes Token angezeigt wird. Dieses Token wird von der Nachrichtensignatur signiert.Der Dienst wird über ein X.509\-Zertifikat authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForSslBindingElement%2A>\-Methode zurückgegebenes `SymmetricSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `UserNameForSslNegotiated` fest.  
  
### UserNameOverTransport  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das an der SOAP\-Schicht als signiertes unterstützendes Token angezeigt wird. Dieses Token wird von der Nachrichtensignatur signiert.Der Dienst wird über ein X.509\-Zertifikat an der Transportschicht authentifiziert.Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameOverTransportBindingElement%2A>\-Methode zurückgegebenes `TransportSecurityBindingElement`.Legen Sie das `authenticationMode`\-Attribut alternativ auf `UserNameOverTransport` fest.  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>   
 [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)