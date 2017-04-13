---
title: "Gewusst wie: Verwenden des ASP.NET-Mitgliedschaftsanbieters | Microsoft Docs"
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
  - "WCF und ASP.NET"
  - "WCF, Autorisierung"
  - "WCF, Sicherheit"
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Gewusst wie: Verwenden des ASP.NET-Mitgliedschaftsanbieters
Der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Mitgliedschaftsanbieter ist eine Funktion für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Entwickler zum Erstellen von Websites, mit denen die Benutzer eindeutige Kombinationen aus Benutzername und Kennwort erstellen können.Jeder Benutzer kann damit ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden.Dies steht im Gegensatz zur Windows\-Sicherheit, bei der die Benutzer über Konten in einer Windows\-Domäne verfügen müssen.Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen \(Kombination aus Benutzername und Kennwort\) angibt, die Site und ihre Dienste nutzen.  
  
 Eine Beispielanwendung finden Sie unter [Mitgliedschafts\- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).Informationen zum Verwenden der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Rollenanbieterfunktion finden Sie unter [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 Die Mitgliedschaftsfunktion setzt die Verwendung einer SQL Server\-Datenbank zum Speichern der Benutzerdaten voraus.Die Funktion schließt auch Methoden zum Anzeigen einer Frage für Benutzer ein, die ihr Kennwort vergessen haben.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Entwickler können diese Funktionen für Sicherheitszwecke nutzen.Wenn sie in eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung integriert sind, müssen die Benutzer der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientanwendung eine Kombination aus Benutzername und Kennwort bereitstellen.Damit die Daten an den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst übertragen werden, müssen Sie eine Bindung verwenden, die die Benutzernamen\-\/Kennwortanmeldeinformationen unterstützt, z. B. <xref:System.ServiceModel.WSHttpBinding> \(in der Konfiguration [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)\), und den Clientanmeldetyp auf `UserName` festlegen.Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sicherheit des Diensts authentifiziert den Benutzer basierend auf Benutzername und Kennwort und weist die von der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Rolle angegebene Rolle zu.  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt keine Methoden bereit, um die Datenbank mit Benutzername\-Kennwort\-Kombinationen oder anderen Benutzerdaten zu füllen.  
  
### So konfigurieren Sie den Mitgliedschaftsanbieter  
  
1.  Erstellen Sie unter dem \<`system.web`\>\-Element der Datei Web.config ein \<`membership`\>\-Element.  
  
2.  Erstellen Sie unter dem `<membership>`\-Element ein `<providers>`\-Element.  
  
3.  Fügen Sie der Datei Web.config das folgende `<clear />`\-Element als untergeordnetes Element des \<`providers`\>\-Elements hinzu, um die Liste der Anbieter zu löschen.  
  
4.  Erstellen Sie unterhalb des `<clear />`\-Elements ein \<`add`\>\-Element, und legen Sie die folgenden Attributwerte fest: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail` und `passwordFormat`.Das `name`\-Attribut wird später als Wert in der Konfigurationsdatei verwendet.Im folgenden Beispiel wird es auf `SqlMembershipProvider` festgelegt.  
  
     Im folgenden Beispiel wird der Konfigurationsabschnitt angegeben.  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### So konfigurieren Sie Dienstsicherheit, die eine Kombination aus Benutzername und Kennwort akzeptiert  
  
1.  Fügen Sie in der Konfigurationsdatei unterhalb des [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)\-Elements ein [\<Bindungen\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)\-Element ein.  
  
2.  Fügen Sie dem Bindungsabschnitt ein [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) hinzu.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Bindungselements finden Sie unter [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3.  Legen Sie das `mode`\-Attribut des `<security>`\-Elements auf `Message` fest.  
  
4.  Legen Sie das `clientCredentialType`\-Attribut des \<`message`\>\-Elements auf `UserName` fest.Dies gibt an, dass ein Benutzername\-Kennwort\-Paar als Anmeldeinformationen für den Client verwendet wird.  
  
     Das folgende Beispiel zeigt den Konfigurationscode für die Bindung.  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### So konfigurieren Sie einen Dienst für die Verwendung des Mitgliedschaftsanbieters  
  
1.  Fügen Sie ein [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\-Element als untergeordnetes Element des `<system.serviceModel>`\-Elements hinzu.  
  
2.  Fügen Sie dem \<`behaviors`\>\-Element ein [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)\-Element hinzu.  
  
3.  Fügen Sie ein [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)\-Element hinzu, und legen Sie das `name`\-Attribut auf einen entsprechenden Wert fest.  
  
4.  Fügen Sie dem \<`behavior`\>\-Element ein [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)\-Element hinzu.  
  
5.  Fügen Sie dem `<serviceCredentials>`\-Element ein [\<userNameAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)\-Element hinzu.  
  
6.  Legen Sie das `userNamePasswordValidationMode`\-Attribut auf `MembershipProvider` fest.  
  
    > [!IMPORTANT]
    >  Wenn der `userNamePasswordValidationMode`\-Wert nicht festgelegt ist, verwendet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Windows\-Authentifizierung statt des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Mitgliedschaftsanbieters.  
  
7.  Legen Sie das `membershipProviderName`\-Attribut auf den Namen des Anbieters fest \(wird beim Hinzufügen des Anbieters im ersten Verfahren in diesem Thema angegeben\).Im folgenden Beispiel sehen Sie das `<serviceCredentials>`\-Fragment bis zu diesem Punkt:  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
  
    ```  
  
## Beispiel  
 Das folgende Codebeispiel zeigt die Konfiguration für einen Dienst, der die ASP\-Mitgliedschaftsfunktion verwendet.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
  
```  
  
## Siehe auch  
 [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)   
 [Mitgliedschafts\- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)