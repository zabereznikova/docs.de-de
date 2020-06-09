---
title: 'Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 5ada34ca2d0d757ea333fed60aef179d6578356c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601178"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="d33c4-102">Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements</span><span class="sxs-lookup"><span data-stu-id="d33c4-102">How to: Use a Custom User Name and Password Validator</span></span>

<span data-ttu-id="d33c4-103">Wenn ein Benutzername und ein Kennwort für die Authentifizierung verwendet werden, werden von Windows Communication Foundation (WCF) standardmäßig Windows verwendet, um den Benutzernamen und das Kennwort zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d33c4-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="d33c4-104">WCF ermöglicht jedoch benutzerdefinierte Authentifizierungs Schemas für Benutzernamen und Kennwort, die auch als *Validierungs Steuerelemente*bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d33c4-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="d33c4-105">Zum Verwenden eines benutzerdefinierten Benutzernamen- und Kennwort-Validierungssteuerelements erstellen und konfigurieren Sie eine Klasse, die sich von <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> ableitet.</span><span class="sxs-lookup"><span data-stu-id="d33c4-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>

<span data-ttu-id="d33c4-106">Eine Beispielanwendung finden Sie unter [Benutzer Name Kennwort-Validierungs](../samples/user-name-password-validator.md)Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d33c4-106">For a sample application, see [User Name Password Validator](../samples/user-name-password-validator.md).</span></span>

### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="d33c4-107">So erstellen Sie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="d33c4-107">To create a custom user name and password validator</span></span>

1. <span data-ttu-id="d33c4-108">Erstellen Sie eine von der <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>-Klasse abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="d33c4-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <span data-ttu-id="d33c4-109">Implementieren Sie ein benutzerdefiniertes Authentifizierungsschema, indem Sie die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="d33c4-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    <span data-ttu-id="d33c4-110">Verwenden Sie nicht den Code des folgenden Beispiels, der die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode in einer Produktionsumgebung außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="d33c4-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="d33c4-111">Ersetzen Sie den Code mit dem benutzerdefinierten Benutzernamen- und Kennwort-Validierungsschema. Möglicherweise müssen der Benutzername und das zugehörige Kennwort aus einer Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d33c4-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

    <span data-ttu-id="d33c4-112">Um dem Client Authentifizierungsfehler zurückzugeben, lösen Sie in der <xref:System.ServiceModel.FaultException>-Methode eine <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> aus.</span><span class="sxs-lookup"><span data-stu-id="d33c4-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="d33c4-113">So konfigurieren Sie einen Dienst für das Verwenden eines benutzerdefinierten Benutzernamen- und Kennwort-Validierungssteuerelements</span><span class="sxs-lookup"><span data-stu-id="d33c4-113">To configure a service to use a custom user name and password validator</span></span>

1. <span data-ttu-id="d33c4-114">Konfigurieren Sie eine Bindung, die Nachrichtensicherheit über jedes beliebige Transportprotokoll oder Sicherheit auf Transportebene über HTTP(S) verwendet.</span><span class="sxs-lookup"><span data-stu-id="d33c4-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>

    <span data-ttu-id="d33c4-115">Wenn Sie die Nachrichten Sicherheit verwenden, fügen Sie eine der vom System bereitgestellten Bindungen hinzu, z. b. ein [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) oder ein, [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) das Nachrichten Sicherheit und den Anmelde `UserName` Informationstyp unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d33c4-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>

    <span data-ttu-id="d33c4-116">Wenn Sie Sicherheit auf Transport Ebene über HTTP (s) verwenden, fügen Sie entweder das [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) oder [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) , ein [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) oder ein hinzu, [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) das HTTP (s) und das `Basic` Authentifizierungsschema verwendet.</span><span class="sxs-lookup"><span data-stu-id="d33c4-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d33c4-117">Wenn Sie .NET Framework 3,5 oder höhere Versionen verwenden, können Sie ein benutzerdefiniertes Benutzernamen-und Kennwort-Validierungs Steuerelement mit Nachrichten-und Transportsicherheit verwenden.</span><span class="sxs-lookup"><span data-stu-id="d33c4-117">When using .NET Framework 3.5 or later versions, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="d33c4-118">Mit WinFX kann ein benutzerdefinierter Benutzername und ein Kennwort-Validierungs Steuerelement nur mit Nachrichten Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d33c4-118">With WinFX, a custom username and password validator can only be used with message security.</span></span>

    > [!TIP]
    > <span data-ttu-id="d33c4-119">Weitere Informationen zur Verwendung von \<netTcpBinding> in diesem Kontext finden Sie unter [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d33c4-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).</span></span>

    1. <span data-ttu-id="d33c4-120">Fügen Sie in der Konfigurationsdatei unter dem- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Element ein- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="d33c4-120">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

    2. <span data-ttu-id="d33c4-121">Fügen Sie [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) dem Bindungs Abschnitt ein-Element oder ein- [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="d33c4-121">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="d33c4-122">Weitere Informationen zum Erstellen eines WCF-Bindungs Elements finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung in der Konfiguration](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d33c4-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    3. <span data-ttu-id="d33c4-123">Legen Sie das- `mode` Attribut von [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) oder [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) auf `Message` , oder fest `Transport` `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="d33c4-123">Set the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

    4. <span data-ttu-id="d33c4-124">Legen Sie das- `clientCredentialType` Attribut von [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) oder fest [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d33c4-124">Set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>

        <span data-ttu-id="d33c4-125">Wenn Sie die Nachrichten Sicherheit verwenden, legen Sie das- `clientCredentialType` Attribut von [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) auf fest `UserName` .</span><span class="sxs-lookup"><span data-stu-id="d33c4-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>

        <span data-ttu-id="d33c4-126">Wenn Sie Sicherheit auf Transport Ebene über HTTP (S) verwenden, legen `clientCredentialType` Sie das-Attribut von [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) oder [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) auf fest `Basic` .</span><span class="sxs-lookup"><span data-stu-id="d33c4-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d33c4-127">Wenn ein WCF-Dienst mit Sicherheit auf Transport Ebene in Internetinformationsdienste (IIS) gehostet wird und die- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> Eigenschaft auf festgelegt ist, wird für <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> das benutzerdefinierte Authentifizierungsschema eine Teilmenge der Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d33c4-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="d33c4-128">Der Grund hierfür ist, dass IIS in diesem Szenario die Windows-Authentifizierung ausführt, bevor WCF den benutzerdefinierten Authentifikator aufruft.</span><span class="sxs-lookup"><span data-stu-id="d33c4-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>

    <span data-ttu-id="d33c4-129">Weitere Informationen zum Erstellen eines WCF-Bindungs Elements finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung in der Konfiguration](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d33c4-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    <span data-ttu-id="d33c4-130">Das folgende Beispiel zeigt den Konfigurations Code für die Bindung:</span><span class="sxs-lookup"><span data-stu-id="d33c4-130">The following example shows the configuration code for the binding:</span></span>

    ```xml
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

2. <span data-ttu-id="d33c4-131">Konfigurieren Sie ein Verhalten, das angibt, dass ein benutzerdefiniertes Benutzername- und Kennwort-Validierungssteuerelement verwendet wird, um Benutzernamen/Kennwort-Paare für eingehende <xref:System.IdentityModel.Tokens.UserNameSecurityToken>-Sicherheitstoken zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d33c4-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>

    1. <span data-ttu-id="d33c4-132">Fügen Sie ein-Element als untergeordnetes Element des- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Elements hinzu [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="d33c4-132">As a child to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    2. <span data-ttu-id="d33c4-133">Fügen Sie [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) dem- [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) Element einen hinzu.</span><span class="sxs-lookup"><span data-stu-id="d33c4-133">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    3. <span data-ttu-id="d33c4-134">Fügen Sie ein [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) -Element hinzu, und legen Sie das- `name` Attribut auf einen geeigneten Wert fest</span><span class="sxs-lookup"><span data-stu-id="d33c4-134">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>

    4. <span data-ttu-id="d33c4-135">Fügen Sie [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) dem- [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) Element einen hinzu.</span><span class="sxs-lookup"><span data-stu-id="d33c4-135">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    5. <span data-ttu-id="d33c4-136">Fügen Sie ein hinzu [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="d33c4-136">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

    6. <span data-ttu-id="d33c4-137">Legen Sie `userNamePasswordValidationMode` auf `Custom` fest.</span><span class="sxs-lookup"><span data-stu-id="d33c4-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="d33c4-138">Wenn der `userNamePasswordValidationMode` Wert nicht festgelegt ist, verwendet WCF anstelle des benutzerdefinierten Benutzernamens und des Kennwort-Validierungs Steuer Elements die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d33c4-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>

    7. <span data-ttu-id="d33c4-139">Legen Sie den `customUserNamePasswordValidatorType` auf den Typ fest, der das benutzerdefinierte Benutzernamen- und Kennwort-Validierungssteuerelement darstellt.</span><span class="sxs-lookup"><span data-stu-id="d33c4-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>

    <span data-ttu-id="d33c4-140">Das folgende Beispiel zeigt das `<serviceCredentials>` Fragment bis zu diesem Punkt:</span><span class="sxs-lookup"><span data-stu-id="d33c4-140">The following example shows the `<serviceCredentials>` fragment to this point:</span></span>

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a><span data-ttu-id="d33c4-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d33c4-141">Example</span></span>

<span data-ttu-id="d33c4-142">Im folgenden Codebeispiel wird veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d33c4-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="d33c4-143">Verwenden Sie nicht den Code, der die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode in einer Produktionsumgebung außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="d33c4-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="d33c4-144">Ersetzen Sie den Code mit dem benutzerdefinierten Benutzernamen- und Kennwort-Validierungsschema. Möglicherweise müssen der Benutzername und das zugehörige Kennwort aus einer Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d33c4-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a><span data-ttu-id="d33c4-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d33c4-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="d33c4-146">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="d33c4-146">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="d33c4-147">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d33c4-147">Authentication</span></span>](authentication-in-wcf.md)
