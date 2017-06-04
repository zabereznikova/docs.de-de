---
title: "Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements | Microsoft Docs"
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
  - "WCF, Benutzername und Kennwort"
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements
Wenn ein Benutzername und ein Kennwort für die Authentifizierung verwendet werden, verwendet [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] standardmäßig Windows zum Überprüfen des Benutzernamens und des Kennworts.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ermöglich jedoch benutzerdefinierte Benutzernamen\- und Kennwortauthentifizierungsschemas, die auch *Validierungssteuerelemente* genannt werden.Zum Verwenden eines benutzerdefinierten Benutzernamen\- und Kennwort\-Validierungssteuerelements erstellen und konfigurieren Sie eine Klasse, die sich von <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> ableitet.  
  
 Eine Beispielanwendung finden Sie unter [Benutzernamen\- und Kennwort\-Validierungssteuerelement](../../../../docs/framework/wcf/samples/user-name-password-validator.md).  
  
### So erstellen Sie ein benutzerdefiniertes Benutzernamen\- und Kennwort\-Validierungssteuerelement  
  
1.  Erstellen Sie eine von der <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>\-Klasse abgeleitete Klasse.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  Implementieren Sie ein benutzerdefiniertes Authentifizierungsschema, indem Sie die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>\-Methode außer Kraft setzen.  
  
     Verwenden Sie nicht den Code des folgenden Beispiels, der die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>\-Methode in einer Produktionsumgebung außer Kraft setzt.Ersetzen Sie den Code mit dem benutzerdefinierten Benutzernamen\- und Kennwort\-Validierungsschema. Möglicherweise müssen der Benutzername und das zugehörige Kennwort aus einer Datenbank abgerufen werden.  
  
     Um Authentifizierungsfehler an den Client zurückzugeben, lösen Sie in der <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>\-Methode eine <xref:System.ServiceModel.FaultException> aus.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### So konfigurieren Sie einen Dienst für das Verwenden eines benutzerdefinierten Benutzernamen\- und Kennwort\-Validierungssteuerelements  
  
1.  Konfigurieren Sie eine Bindung, die Nachrichtensicherheit über jedes beliebige Transportprotokoll oder Sicherheit auf Transportebene über HTTP\(S\) verwendet.  
  
     Bei Verwendung von Nachrichtensicherheit fügen Sie eine der vom System bereitgestellten Bindungen hinzu, beispielsweise [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), oder ein [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md), das Nachrichtensicherheit und den Anmeldeinformationstyp `UserName` unterstützt.  
  
     Wenn Sie Sicherheit auf Transportebene über HTTP\(S\) verwenden, fügen Sie entweder das [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oder das [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) hinzu oder ein [\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) oder ein [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) das mit HTTP\(S\) und dem Authentifizierungsschema `Basic` arbeitet.  
  
    > [!NOTE]
    >  Wenn Sie [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] oder höher verwenden, können Sie ein benutzerdefiniertes Benutzernamen\- und Kennwort\-Validierungssteuerelement mit Nachrichten\- und Transportsicherheit nutzen.In Verbindung mit [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] kann ein benutzerdefiniertes Benutzername\- und Kennwort\-Validierungssteuerelement nur mit Nachrichtensicherheit verwendet werden.  
  
    > [!TIP]
    >  Weitere Informationen zur Verwendung von \<netTcpBinding\> in diesem Kontext finden Sie unter [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
  
    1.  Fügen Sie in der Konfigurationsdatei unterhalb des [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)\-Elements ein [\<Bindungen\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)\-Element ein.  
  
    2.  Fügen Sie dem Bindungsabschnitt ein [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)\-Element oder [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)\-Element hinzu.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Bindungselements finden Sie unter [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
    3.  Legen Sie das `mode`\-Attribut für das [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) oder [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)`Message``Transport` auf `or`, `TransportWithMessageCredential`,   fest.  
  
    4.  Legen Sie das `clientCredentialType`\-Attribut des [\<message\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) oder des [\<transport\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) fest.  
  
         Bei Verwendung von Nachrichtensicherheit legen Sie das `clientCredentialType`\-Attribute des [\<message\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) auf `UserName`fest.  
  
         Wenn Sicherheit auf Transportebene über HTTP\(S\) verwendet wird, legen Sie das `clientCredentialType`\-Attribut des [\<transport\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)[\<transport\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)`Basic` oder  auf  fest.  
  
        > [!NOTE]
        >  Wenn ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst in Internet Information Services \(IIS\) unter Verwendung von Sicherheit auf Transportebene gehostet wird und die <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A>\-Eigenschaft auf <xref:System.ServiceModel.Security.UserNamePasswordValidationMode> festgelegt ist, dann verwendet das benutzerdefinierte Authentifizierungsschema eine Teilmenge der Windows\-Authentifizierung.Das liegt daran, dass IIS in diesem Szenario die Windows\-Authentifizierung ausführt, bevor [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] den benutzerdefinierten Authentifizierer aufruft  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Bindungselements finden Sie unter [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
     Das folgende Beispiel zeigt den Konfigurationscode für die Bindung.  
  
    ```  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2.  Konfigurieren Sie ein Verhalten, das angibt, dass ein benutzerdefiniertes Benutzername\- und Kennwort\-Validierungssteuerelement verwendet wird, um Benutzernamen\/Kennwort\-Paare für eingehende <xref:System.IdentityModel.Tokens.UserNameSecurityToken>\-Sicherheitstoken zu überprüfen.  
  
    1.  Fügen Sie ein [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)[\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\-Elements hinzu.  
  
    2.  Fügen Sie dem [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\-Element ein [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)\-Element hinzu.  
  
    3.  Fügen Sie ein [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)`name-Element hinzu, und legen Sie das` \-Attribut auf einen passenden Wert fest.  
  
    4.  Fügen Sie dem [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)\-Element ein [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)\-Element hinzu.  
  
    5.  Fügen Sie ein [\<userNameAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) zum [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) hinzu.  
  
    6.  Legen Sie den `userNamePasswordValidationMode` auf `Custom` fest.  
  
        > [!IMPORTANT]
        >  Wenn der `userNamePasswordValidationMode`\-Wert nicht festgelegt wird, verwendet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Windows\-Authentifizierung anstatt des benutzerdefinierten Benutzernamen\- und Kennwort\-Validierungssteuerelements.  
  
    7.  Legen Sie den `customUserNamePasswordValidatorType` auf den Typ fest, der das benutzerdefinierte Benutzernamen\- und Kennwort\-Validierungssteuerelement darstellt.  
  
     Im folgenden Beispiel sehen Sie das `<serviceCredentials>`\-Fragment bis zu diesem Punkt:  
  
    ```  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein benutzerdefiniertes Benutzernamen\- und Kennwort\-Validierungssteuerelement erstellt wird.Verwenden Sie nicht den Code, der die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>\-Methode in einer Produktionsumgebung außer Kraft setzt.Ersetzen Sie den Code mit dem benutzerdefinierten Benutzernamen\- und Kennwort\-Validierungsschema. Möglicherweise müssen der Benutzername und das zugehörige Kennwort aus einer Datenbank abgerufen werden.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## Siehe auch  
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>   
 [Gewusst wie: Verwenden des ASP.NET\-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)   
 [Authentifizierung](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)