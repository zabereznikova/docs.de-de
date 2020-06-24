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
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="ec9df-103">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="ec9df-103">How to: Use the ASP.NET Membership Provider</span></span>

<span data-ttu-id="ec9df-104">Der ASP.net-Mitgliedschafts Anbieter ist ein Feature, mit dem ASP.NET-Entwickler Websites erstellen können, die es Benutzern ermöglichen, eindeutige Kombinationen aus Benutzername und Kennwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec9df-104">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="ec9df-105">Jeder Benutzer kann damit ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden.</span><span class="sxs-lookup"><span data-stu-id="ec9df-105">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="ec9df-106">Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="ec9df-106">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="ec9df-107">Stattdessen kann jeder Benutzer, der seine Anmelde Informationen (die Kombination aus Benutzername und Kennwort) bereitstellt, die Website und seine Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec9df-107">Instead, any user that supplies their credentials (the user name/password combination) can use the site and its services.</span></span>

<span data-ttu-id="ec9df-108">Eine Beispielanwendung finden Sie unter [Mitgliedschaft und Rollen Anbieter](../samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ec9df-108">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="ec9df-109">Weitere Informationen zur Verwendung der ASP.NET-Rollen Anbieter Funktion finden Sie unter Gewusst [wie: Verwenden des ASP.NET-Rollen Anbieters mit einem-Dienst](how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="ec9df-109">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>

<span data-ttu-id="ec9df-110">Die Mitgliedschaftsfunktion setzt die Verwendung einer SQL Server-Datenbank zum Speichern der Benutzerdaten voraus.</span><span class="sxs-lookup"><span data-stu-id="ec9df-110">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="ec9df-111">Die Funktion schließt auch Methoden zum Anzeigen einer Frage für Benutzer ein, die ihr Kennwort vergessen haben.</span><span class="sxs-lookup"><span data-stu-id="ec9df-111">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>

<span data-ttu-id="ec9df-112">Windows Communication Foundation (WCF)-Entwickler können diese Features aus Sicherheitsgründen nutzen.</span><span class="sxs-lookup"><span data-stu-id="ec9df-112">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="ec9df-113">Wenn Benutzer in eine WCF-Anwendung integriert sind, müssen Sie der WCF-Client Anwendung eine Kombination aus Benutzername und Kennwort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ec9df-113">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="ec9df-114">Verwenden Sie zum Übertragen der Daten an den WCF-Dienst eine Bindung, die Benutzername/Kennwort-Anmelde Informationen unterstützt, wie z. b. <xref:System.ServiceModel.WSHttpBinding> (in der Konfiguration, [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ), und legen Sie den Client Anmelde Informationstyp auf fest `UserName` .</span><span class="sxs-lookup"><span data-stu-id="ec9df-114">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="ec9df-115">Auf dem-Dienst authentifiziert die WCF-Sicherheit den Benutzer auf der Grundlage des Benutzernamens und des Kennworts und weist außerdem die von der ASP.NET-Rolle angegebene Rolle zu.</span><span class="sxs-lookup"><span data-stu-id="ec9df-115">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>

> [!NOTE]
> <span data-ttu-id="ec9df-116">WCF stellt keine Methoden bereit, um die Datenbank mit Kombinationen aus Benutzername und Kennwort oder anderen Benutzerinformationen aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="ec9df-116">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>

### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="ec9df-117">So konfigurieren Sie den Mitgliedschaftsanbieter</span><span class="sxs-lookup"><span data-stu-id="ec9df-117">To configure the membership provider</span></span>

1. <span data-ttu-id="ec9df-118">Erstellen Sie in der Web.config-Datei unter dem <`system.web`>-Element ein <`membership`> Element.</span><span class="sxs-lookup"><span data-stu-id="ec9df-118">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>

2. <span data-ttu-id="ec9df-119">Erstellen Sie unter dem `<membership>`-Element ein `<providers>`-Element.</span><span class="sxs-lookup"><span data-stu-id="ec9df-119">Under the `<membership>` element, create a `<providers>` element.</span></span>

3. <span data-ttu-id="ec9df-120">Fügen Sie als untergeordnetes Element des <`providers`>-Elements ein-Element hinzu, `<clear />` um die Auflistung der Anbieter zu leeren.</span><span class="sxs-lookup"><span data-stu-id="ec9df-120">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>

4. <span data-ttu-id="ec9df-121">Erstellen Sie unter dem- `<clear />` Element ein <`add`>-Element mit den folgenden Attributen, die auf die entsprechenden Werte festgelegt sind: `name` , `type` , `connectionStringName` , `applicationName` , `enablePasswordRetrieval` , `enablePasswordReset` , `requiresQuestionAndAnswer` , `requiresUniqueEmail` und `passwordFormat` .</span><span class="sxs-lookup"><span data-stu-id="ec9df-121">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="ec9df-122">Das `name`-Attribut wird später als Wert in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec9df-122">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="ec9df-123">Im folgenden Beispiel wird das Attribut auf den Wert `SqlMembershipProvider` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ec9df-123">The following example sets it to `SqlMembershipProvider`.</span></span>

    <span data-ttu-id="ec9df-124">Im folgenden Beispiel wird der Konfigurationsabschnitt angegeben.</span><span class="sxs-lookup"><span data-stu-id="ec9df-124">The following example shows the configuration section.</span></span>

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

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="ec9df-125">So konfigurieren Sie Dienstsicherheit, die eine Kombination aus Benutzername und Kennwort akzeptiert</span><span class="sxs-lookup"><span data-stu-id="ec9df-125">To configure service security to accept the user name/password combination</span></span>

1. <span data-ttu-id="ec9df-126">Fügen Sie in der Konfigurationsdatei unter dem- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Element ein- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec9df-126">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

2. <span data-ttu-id="ec9df-127">Fügen Sie [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) dem Bindungs Abschnitt ein hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec9df-127">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="ec9df-128">Weitere Informationen zum Erstellen eines WCF-Bindungs Elements finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung in der Konfiguration](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ec9df-128">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

3. <span data-ttu-id="ec9df-129">Legen Sie das `mode`-Attribut des `<security>`-Elements auf `Message` fest.</span><span class="sxs-lookup"><span data-stu-id="ec9df-129">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>

4. <span data-ttu-id="ec9df-130">Legen Sie das- `clientCredentialType` Attribut des <`message`>-Elements auf fest `UserName` .</span><span class="sxs-lookup"><span data-stu-id="ec9df-130">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="ec9df-131">Dies gibt an, dass ein Benutzername-Kennwort-Paar als Anmeldeinformationen für den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ec9df-131">This specifies that a user name/password pair will be used as the client's credential.</span></span>

    <span data-ttu-id="ec9df-132">Das folgende Beispiel zeigt den Konfigurationscode für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="ec9df-132">The following example shows the configuration code for the binding.</span></span>

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

### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="ec9df-133">So konfigurieren Sie einen Dienst für die Verwendung des Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="ec9df-133">To configure a service to use the membership provider</span></span>

1. <span data-ttu-id="ec9df-134">Fügen Sie ein-Element als untergeordnetes Element des- `<system.serviceModel>` Elements hinzu. [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ec9df-134">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element</span></span>

2. <span data-ttu-id="ec9df-135">Fügen Sie ein- [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) Element zum <`behaviors`>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec9df-135">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>

3. <span data-ttu-id="ec9df-136">Fügen Sie hinzu [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) , und legen Sie das- `name` Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="ec9df-136">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>

4. <span data-ttu-id="ec9df-137">Fügen Sie ein- [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) Element zum <`behavior`>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec9df-137">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>

5. <span data-ttu-id="ec9df-138">Fügen Sie [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) dem- `<serviceCredentials>` Element einen hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec9df-138">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>

6. <span data-ttu-id="ec9df-139">Legen Sie das `userNamePasswordValidationMode`-Attribut auf `MembershipProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="ec9df-139">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ec9df-140">Wenn der `userNamePasswordValidationMode` Wert nicht festgelegt ist, verwendet WCF anstelle des ASP.net-Mitgliedschafts Anbieters die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ec9df-140">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>

7. <span data-ttu-id="ec9df-141">Legen Sie das `membershipProviderName`-Attribut auf den Namen des Anbieters fest (wird beim Hinzufügen des Anbieters im ersten Verfahren in diesem Thema angegeben).</span><span class="sxs-lookup"><span data-stu-id="ec9df-141">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="ec9df-142">Im folgenden Beispiel sehen Sie das `<serviceCredentials>`-Fragment bis zu diesem Punkt:</span><span class="sxs-lookup"><span data-stu-id="ec9df-142">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

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

## <a name="example"></a><span data-ttu-id="ec9df-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec9df-143">Example</span></span>

<span data-ttu-id="ec9df-144">Das folgende Codebeispiel zeigt die Konfiguration für einen Dienst, der die ASP-Mitgliedschaftsfunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec9df-144">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ec9df-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec9df-145">See also</span></span>

- [<span data-ttu-id="ec9df-146">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="ec9df-146">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="ec9df-147">Mitgliedschafts- und Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="ec9df-147">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
