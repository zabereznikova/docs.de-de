---
title: 'Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters'
description: Erfahren Sie, wie der ASP.net-Mitgliedschafts Anbieter Websites unterstützt, mit denen Benutzer einen Benutzernamen und ein Kennwort für den Zugriff ohne Windows-Domänen Konto erstellen können
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 6d527993dcf1fc5d5cd39bf22c3e772baf60e62f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246726"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters

Der ASP.net-Mitgliedschafts Anbieter ist ein Feature, mit dem ASP.NET-Entwickler Websites erstellen können, die es Benutzern ermöglichen, eindeutige Kombinationen aus Benutzername und Kennwort zu erstellen. Jeder Benutzer kann damit ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden. Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen. Stattdessen kann jeder Benutzer, der seine Anmelde Informationen (die Kombination aus Benutzername und Kennwort) bereitstellt, die Website und seine Dienste verwenden.

Eine Beispielanwendung finden Sie unter [Mitgliedschaft und Rollen Anbieter](../samples/membership-and-role-provider.md). Weitere Informationen zur Verwendung der ASP.NET-Rollen Anbieter Funktion finden Sie unter Gewusst [wie: Verwenden des ASP.NET-Rollen Anbieters mit einem-Dienst](how-to-use-the-aspnet-role-provider-with-a-service.md).

Die Mitgliedschaftsfunktion setzt die Verwendung einer SQL Server-Datenbank zum Speichern der Benutzerdaten voraus. Die Funktion schließt auch Methoden zum Anzeigen einer Frage für Benutzer ein, die ihr Kennwort vergessen haben.

Windows Communication Foundation (WCF)-Entwickler können diese Features aus Sicherheitsgründen nutzen. Wenn Benutzer in eine WCF-Anwendung integriert sind, müssen Sie der WCF-Client Anwendung eine Kombination aus Benutzername und Kennwort bereitstellen. Verwenden Sie zum Übertragen der Daten an den WCF-Dienst eine Bindung, die Benutzername/Kennwort-Anmelde Informationen unterstützt, wie z. b. <xref:System.ServiceModel.WSHttpBinding> (in der Konfiguration, [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ), und legen Sie den Client Anmelde Informationstyp auf fest `UserName` . Auf dem-Dienst authentifiziert die WCF-Sicherheit den Benutzer auf der Grundlage des Benutzernamens und des Kennworts und weist außerdem die von der ASP.NET-Rolle angegebene Rolle zu.

> [!NOTE]
> WCF stellt keine Methoden bereit, um die Datenbank mit Kombinationen aus Benutzername und Kennwort oder anderen Benutzerinformationen aufzufüllen.

### <a name="to-configure-the-membership-provider"></a>So konfigurieren Sie den Mitgliedschaftsanbieter

1. Erstellen Sie in der Web.config-Datei unter dem <`system.web`>-Element ein <`membership`> Element.

2. Erstellen Sie unter dem `<membership>`-Element ein `<providers>`-Element.

3. Fügen Sie als untergeordnetes Element des <`providers`>-Elements ein-Element hinzu, `<clear />` um die Auflistung der Anbieter zu leeren.

4. Erstellen Sie unter dem- `<clear />` Element ein <`add`>-Element mit den folgenden Attributen, die auf die entsprechenden Werte festgelegt sind: `name` , `type` , `connectionStringName` , `applicationName` , `enablePasswordRetrieval` , `enablePasswordReset` , `requiresQuestionAndAnswer` , `requiresUniqueEmail` und `passwordFormat` . Das `name`-Attribut wird später als Wert in der Konfigurationsdatei verwendet. Im folgenden Beispiel wird das Attribut auf den Wert `SqlMembershipProvider` festgelegt.

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

1. Fügen Sie in der Konfigurationsdatei unter dem- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Element ein- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Element hinzu.

2. Fügen Sie [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) dem Bindungs Abschnitt ein hinzu. Weitere Informationen zum Erstellen eines WCF-Bindungs Elements finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung in der Konfiguration](../how-to-specify-a-service-binding-in-configuration.md).

3. Legen Sie das `mode`-Attribut des `<security>`-Elements auf `Message` fest.

4. Legen Sie das- `clientCredentialType` Attribut des <`message`>-Elements auf fest `UserName` . Dies gibt an, dass ein Benutzername-Kennwort-Paar als Anmeldeinformationen für den Client verwendet wird.

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

1. Fügen Sie ein-Element als untergeordnetes Element des- `<system.serviceModel>` Elements hinzu. [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)

2. Fügen Sie ein- [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) Element zum <`behaviors`>-Element hinzu.

3. Fügen Sie hinzu [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) , und legen Sie das- `name` Attribut auf einen geeigneten Wert fest.

4. Fügen Sie ein- [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) Element zum <`behavior`>-Element hinzu.

5. Fügen Sie [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) dem- `<serviceCredentials>` Element einen hinzu.

6. Legen Sie das `userNamePasswordValidationMode`-Attribut auf `MembershipProvider` fest.

    > [!IMPORTANT]
    > Wenn der `userNamePasswordValidationMode` Wert nicht festgelegt ist, verwendet WCF anstelle des ASP.net-Mitgliedschafts Anbieters die Windows-Authentifizierung.

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

- [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Mitgliedschafts- und Rollenanbieter](../samples/membership-and-role-provider.md)
