---
title: 'Gewusst wie: Verwenden des ASP.NET-Mitgliedschaftsanbieters'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 5b15d56c7150a8478bc32651538903778e3b877d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184796"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Gewusst wie: Verwenden des ASP.NET-Mitgliedschaftsanbieters

Der ASP.NET-Mitgliedschaftsanbieter ist ein Feature, mit dem ASP.NET Entwickler Websites erstellen können, mit denen Benutzer eindeutige Benutzernamen- und Kennwortkombinationen erstellen können. Jeder Benutzer kann damit ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden. Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen. Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen bereitstellt (die Kombination "Benutzername/Kennwort"," und "Benutzername/Kennwort") die Website und ihre Dienste verwenden.

Eine Beispielanwendung finden Sie unter [Mitgliedschaft und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Informationen zur Verwendung der ASP.NET Rollenanbieterfunktion finden Sie unter [Gewusst wie: Verwenden des ASP.NET Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).

Die Mitgliedschaftsfunktion setzt die Verwendung einer SQL Server-Datenbank zum Speichern der Benutzerdaten voraus. Die Funktion schließt auch Methoden zum Anzeigen einer Frage für Benutzer ein, die ihr Kennwort vergessen haben.

Windows Communication Foundation (WCF)-Entwickler können diese Funktionen aus Sicherheitsgründen nutzen. Wenn benutzerin eine WCF-Anwendung integriert ist, müssen sie der WCF-Clientanwendung eine Kombination aus Benutzername und Kennwort bereitstellen. Um die Daten an den WCF-Dienst zu übertragen, verwenden Sie eine <xref:System.ServiceModel.WSHttpBinding> Bindung, die Benutzernamen/Kennwortanmeldeinformationen unterstützt, z. `UserName`B. die (in der Konfiguration, die [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) und legen Sie den Clientanmeldeinformationstyp auf fest. Im Dienst authentifiziert WCF-Sicherheit den Benutzer basierend auf dem Benutzernamen und kennwort und weist auch die Rolle zu, die durch die rolle ASP.NET angegeben wird.

> [!NOTE]
> WCF stellt keine Methoden zum Auffüllen der Datenbank mit Kombinationen aus Benutzername/Kennwort oder anderen Benutzerinformationen bereit.

### <a name="to-configure-the-membership-provider"></a>So konfigurieren Sie den Mitgliedschaftsanbieter

1. Erstellen Sie in der Datei Web.config unter dem <`system.web`>-Element ein <`membership`>-Element.

2. Erstellen Sie unter dem `<membership>`-Element ein `<providers>`-Element.

3. Fügen Sie als `providers` untergeordnetes Element `<clear />` zum <>-Element ein Element hinzu, um die Auflistung der Anbieter zu leeren.

4. Erstellen `<clear />` Sie unter dem `add` Element ein <>-Element mit `name` `type`den `connectionStringName` `applicationName`folgenden `enablePasswordRetrieval` `enablePasswordReset`Attributen, die auf die entsprechenden Werte festgelegt sind: , , , , , `requiresQuestionAndAnswer`, `requiresUniqueEmail`, , und `passwordFormat`. Das `name`-Attribut wird später als Wert in der Konfigurationsdatei verwendet. Im folgenden Beispiel wird das Attribut auf den Wert `SqlMembershipProvider` festgelegt.

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

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a>So konfigurieren Sie Dienstsicherheit, die eine Kombination aus Benutzername und Kennwort akzeptiert

1. Fügen Sie in der Konfigurationsdatei unter dem [ \<System.serviceModel>-Element](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) eine [ \<Bindung>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element hinzu.

2. Fügen Sie dem Bindungsabschnitt eine [ \<wsHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) hinzu. Weitere Informationen zum Erstellen eines WCF-Bindungselements finden Sie unter [Gewusst wie: Angeben einer Dienstbindung in Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).

3. Legen Sie das `mode`-Attribut des `<security>`-Elements auf `Message` fest.

4. Legen `clientCredentialType` Sie das `message` Attribut des `UserName`<>-Elements auf fest. Dies gibt an, dass ein Benutzername-Kennwort-Paar als Anmeldeinformationen für den Client verwendet wird.

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

### <a name="to-configure-a-service-to-use-the-membership-provider"></a>So konfigurieren Sie einen Dienst für die Verwendung des Mitgliedschaftsanbieters

1. Fügen Sie dem `<system.serviceModel>` Element als untergeordnetes Element ein [ \<Verhalten>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element hinzu.

2. Fügen Sie dem <`behaviors`>-Element einen [ \<serviceBehaviors->](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) hinzu.

3. Fügen [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Sie ein Verhalten `name`>hinzu, und legen Sie das Attribut auf einen geeigneten Wert fest.

4. Fügen Sie dem <`behavior`>-Element einen [ \<serviceCredentials->](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) hinzu.

5. Fügen Sie dem `<serviceCredentials>` Element eine [ \<userNameAuthentication->](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) hinzu.

6. Legen Sie das `userNamePasswordValidationMode`-Attribut auf `MembershipProvider` fest.

    > [!IMPORTANT]
    > Wenn `userNamePasswordValidationMode` der Wert nicht festgelegt ist, verwendet WCF die Windows-Authentifizierung anstelle des ASP.NET Mitgliedschaftsanbieters.

7. Legen Sie das `membershipProviderName`-Attribut auf den Namen des Anbieters fest (wird beim Hinzufügen des Anbieters im ersten Verfahren in diesem Thema angegeben). Im folgenden Beispiel sehen Sie das `<serviceCredentials>`-Fragment bis zu diesem Punkt:

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

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt die Konfiguration für einen Dienst, der die ASP-Mitgliedschaftsfunktion verwendet.

```xml
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

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Mitgliedschafts- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
