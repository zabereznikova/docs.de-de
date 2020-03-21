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
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="04186-102">Gewusst wie: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="04186-102">How to: Use the ASP.NET Membership Provider</span></span>

<span data-ttu-id="04186-103">Der ASP.NET-Mitgliedschaftsanbieter ist ein Feature, mit dem ASP.NET Entwickler Websites erstellen können, mit denen Benutzer eindeutige Benutzernamen- und Kennwortkombinationen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="04186-103">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="04186-104">Jeder Benutzer kann damit ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden.</span><span class="sxs-lookup"><span data-stu-id="04186-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="04186-105">Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="04186-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="04186-106">Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen bereitstellt (die Kombination "Benutzername/Kennwort"," und "Benutzername/Kennwort") die Website und ihre Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="04186-106">Instead, any user that supplies their credentials (the user name/password combination) can use the site and its services.</span></span>

<span data-ttu-id="04186-107">Eine Beispielanwendung finden Sie unter [Mitgliedschaft und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="04186-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="04186-108">Informationen zur Verwendung der ASP.NET Rollenanbieterfunktion finden Sie unter [Gewusst wie: Verwenden des ASP.NET Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="04186-108">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>

<span data-ttu-id="04186-109">Die Mitgliedschaftsfunktion setzt die Verwendung einer SQL Server-Datenbank zum Speichern der Benutzerdaten voraus.</span><span class="sxs-lookup"><span data-stu-id="04186-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="04186-110">Die Funktion schließt auch Methoden zum Anzeigen einer Frage für Benutzer ein, die ihr Kennwort vergessen haben.</span><span class="sxs-lookup"><span data-stu-id="04186-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>

<span data-ttu-id="04186-111">Windows Communication Foundation (WCF)-Entwickler können diese Funktionen aus Sicherheitsgründen nutzen.</span><span class="sxs-lookup"><span data-stu-id="04186-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="04186-112">Wenn benutzerin eine WCF-Anwendung integriert ist, müssen sie der WCF-Clientanwendung eine Kombination aus Benutzername und Kennwort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="04186-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="04186-113">Um die Daten an den WCF-Dienst zu übertragen, verwenden Sie eine <xref:System.ServiceModel.WSHttpBinding> Bindung, die Benutzernamen/Kennwortanmeldeinformationen unterstützt, z. `UserName`B. die (in der Konfiguration, die [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) und legen Sie den Clientanmeldeinformationstyp auf fest.</span><span class="sxs-lookup"><span data-stu-id="04186-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="04186-114">Im Dienst authentifiziert WCF-Sicherheit den Benutzer basierend auf dem Benutzernamen und kennwort und weist auch die Rolle zu, die durch die rolle ASP.NET angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="04186-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>

> [!NOTE]
> <span data-ttu-id="04186-115">WCF stellt keine Methoden zum Auffüllen der Datenbank mit Kombinationen aus Benutzername/Kennwort oder anderen Benutzerinformationen bereit.</span><span class="sxs-lookup"><span data-stu-id="04186-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>

### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="04186-116">So konfigurieren Sie den Mitgliedschaftsanbieter</span><span class="sxs-lookup"><span data-stu-id="04186-116">To configure the membership provider</span></span>

1. <span data-ttu-id="04186-117">Erstellen Sie in der Datei Web.config unter dem <`system.web`>-Element ein <`membership`>-Element.</span><span class="sxs-lookup"><span data-stu-id="04186-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>

2. <span data-ttu-id="04186-118">Erstellen Sie unter dem `<membership>`-Element ein `<providers>`-Element.</span><span class="sxs-lookup"><span data-stu-id="04186-118">Under the `<membership>` element, create a `<providers>` element.</span></span>

3. <span data-ttu-id="04186-119">Fügen Sie als `providers` untergeordnetes Element `<clear />` zum <>-Element ein Element hinzu, um die Auflistung der Anbieter zu leeren.</span><span class="sxs-lookup"><span data-stu-id="04186-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>

4. <span data-ttu-id="04186-120">Erstellen `<clear />` Sie unter dem `add` Element ein <>-Element mit `name` `type`den `connectionStringName` `applicationName`folgenden `enablePasswordRetrieval` `enablePasswordReset`Attributen, die auf die entsprechenden Werte festgelegt sind: , , , , , `requiresQuestionAndAnswer`, `requiresUniqueEmail`, , und `passwordFormat`.</span><span class="sxs-lookup"><span data-stu-id="04186-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="04186-121">Das `name`-Attribut wird später als Wert in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="04186-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="04186-122">Im folgenden Beispiel wird das Attribut auf den Wert `SqlMembershipProvider` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="04186-122">The following example sets it to `SqlMembershipProvider`.</span></span>

    <span data-ttu-id="04186-123">Im folgenden Beispiel wird der Konfigurationsabschnitt angegeben.</span><span class="sxs-lookup"><span data-stu-id="04186-123">The following example shows the configuration section.</span></span>

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

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="04186-124">So konfigurieren Sie Dienstsicherheit, die eine Kombination aus Benutzername und Kennwort akzeptiert</span><span class="sxs-lookup"><span data-stu-id="04186-124">To configure service security to accept the user name/password combination</span></span>

1. <span data-ttu-id="04186-125">Fügen Sie in der Konfigurationsdatei unter dem [ \<System.serviceModel>-Element](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) eine [ \<Bindung>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="04186-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>

2. <span data-ttu-id="04186-126">Fügen Sie dem Bindungsabschnitt eine [ \<wsHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="04186-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="04186-127">Weitere Informationen zum Erstellen eines WCF-Bindungselements finden Sie unter [Gewusst wie: Angeben einer Dienstbindung in Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="04186-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>

3. <span data-ttu-id="04186-128">Legen Sie das `mode`-Attribut des `<security>`-Elements auf `Message` fest.</span><span class="sxs-lookup"><span data-stu-id="04186-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>

4. <span data-ttu-id="04186-129">Legen `clientCredentialType` Sie das `message` Attribut des `UserName`<>-Elements auf fest.</span><span class="sxs-lookup"><span data-stu-id="04186-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="04186-130">Dies gibt an, dass ein Benutzername-Kennwort-Paar als Anmeldeinformationen für den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="04186-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>

    <span data-ttu-id="04186-131">Das folgende Beispiel zeigt den Konfigurationscode für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="04186-131">The following example shows the configuration code for the binding.</span></span>

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

### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="04186-132">So konfigurieren Sie einen Dienst für die Verwendung des Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="04186-132">To configure a service to use the membership provider</span></span>

1. <span data-ttu-id="04186-133">Fügen Sie dem `<system.serviceModel>` Element als untergeordnetes Element ein [ \<Verhalten>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="04186-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>

2. <span data-ttu-id="04186-134">Fügen Sie dem <`behaviors`>-Element einen [ \<serviceBehaviors->](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="04186-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>

3. <span data-ttu-id="04186-135">Fügen [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Sie ein Verhalten `name`>hinzu, und legen Sie das Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="04186-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>

4. <span data-ttu-id="04186-136">Fügen Sie dem <`behavior`>-Element einen [ \<serviceCredentials->](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="04186-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>

5. <span data-ttu-id="04186-137">Fügen Sie dem `<serviceCredentials>` Element eine [ \<userNameAuthentication->](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="04186-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>

6. <span data-ttu-id="04186-138">Legen Sie das `userNamePasswordValidationMode`-Attribut auf `MembershipProvider` fest.</span><span class="sxs-lookup"><span data-stu-id="04186-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04186-139">Wenn `userNamePasswordValidationMode` der Wert nicht festgelegt ist, verwendet WCF die Windows-Authentifizierung anstelle des ASP.NET Mitgliedschaftsanbieters.</span><span class="sxs-lookup"><span data-stu-id="04186-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>

7. <span data-ttu-id="04186-140">Legen Sie das `membershipProviderName`-Attribut auf den Namen des Anbieters fest (wird beim Hinzufügen des Anbieters im ersten Verfahren in diesem Thema angegeben).</span><span class="sxs-lookup"><span data-stu-id="04186-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="04186-141">Im folgenden Beispiel sehen Sie das `<serviceCredentials>`-Fragment bis zu diesem Punkt:</span><span class="sxs-lookup"><span data-stu-id="04186-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

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

## <a name="example"></a><span data-ttu-id="04186-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04186-142">Example</span></span>

<span data-ttu-id="04186-143">Das folgende Codebeispiel zeigt die Konfiguration für einen Dienst, der die ASP-Mitgliedschaftsfunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="04186-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="04186-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04186-144">See also</span></span>

- [<span data-ttu-id="04186-145">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="04186-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="04186-146">Mitgliedschafts- und Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="04186-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
