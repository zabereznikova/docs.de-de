---
title: 'Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4ea4f4d7021f02d239b9e2e93a85b5baaf5a0317
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="7adbf-102">Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements</span><span class="sxs-lookup"><span data-stu-id="7adbf-102">How to: Use a Custom User Name and Password Validator</span></span>
<span data-ttu-id="7adbf-103">Wenn ein Benutzername und ein Kennwort für die Authentifizierung verwendet werden, verwendet [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] standardmäßig Windows zum Überprüfen des Benutzernamens und des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="7adbf-103">By default, when a user name and password is used for authentication, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses Windows to validate the user name and password.</span></span> <span data-ttu-id="7adbf-104">Allerdings [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ermöglicht benutzerdefinierten Benutzernamen- und Kennwort-Authentifizierungsschemas, auch bekannt als *Validierungssteuerelemente*.</span><span class="sxs-lookup"><span data-stu-id="7adbf-104">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="7adbf-105">Zum Verwenden eines benutzerdefinierten Benutzernamen- und Kennwort-Validierungssteuerelements erstellen und konfigurieren Sie eine Klasse, die sich von <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> ableitet.</span><span class="sxs-lookup"><span data-stu-id="7adbf-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>  
  
 <span data-ttu-id="7adbf-106">Eine beispielanwendung finden Sie unter [Benutzer und Kennwort-Validierungssteuerelement](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span><span class="sxs-lookup"><span data-stu-id="7adbf-106">For a sample application, see [User Name Password Validator](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span></span>  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="7adbf-107">So erstellen Sie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="7adbf-107">To create a custom user name and password validator</span></span>  
  
1.  <span data-ttu-id="7adbf-108">Erstellen Sie eine von der <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>-Klasse abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="7adbf-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  <span data-ttu-id="7adbf-109">Implementieren Sie ein benutzerdefiniertes Authentifizierungsschema, indem Sie die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="7adbf-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     <span data-ttu-id="7adbf-110">Verwenden Sie nicht den Code des folgenden Beispiels, der die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode in einer Produktionsumgebung außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="7adbf-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="7adbf-111">Ersetzen Sie den Code mit dem benutzerdefinierten Benutzernamen- und Kennwort-Validierungsschema. Möglicherweise müssen der Benutzername und das zugehörige Kennwort aus einer Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7adbf-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
     <span data-ttu-id="7adbf-112">Um dem Client Authentifizierungsfehler zurückzugeben, lösen Sie in der <xref:System.ServiceModel.FaultException>-Methode eine <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> aus.</span><span class="sxs-lookup"><span data-stu-id="7adbf-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="7adbf-113">So konfigurieren Sie einen Dienst für das Verwenden eines benutzerdefinierten Benutzernamen- und Kennwort-Validierungssteuerelements</span><span class="sxs-lookup"><span data-stu-id="7adbf-113">To configure a service to use a custom user name and password validator</span></span>  
  
1.  <span data-ttu-id="7adbf-114">Konfigurieren Sie eine Bindung, die Nachrichtensicherheit über jedes beliebige Transportprotokoll oder Sicherheit auf Transportebene über HTTP(S) verwendet.</span><span class="sxs-lookup"><span data-stu-id="7adbf-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>  
  
     <span data-ttu-id="7adbf-115">Bei Verwendung von nachrichtensicherheit fügen Sie eine der vom System bereitgestellte Bindungen, wie z. B. eine [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), oder ein [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) die Sicherheit unterstützt für Nachrichten und die `UserName` Anmeldeinformationstyp.</span><span class="sxs-lookup"><span data-stu-id="7adbf-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>  
  
     <span data-ttu-id="7adbf-116">Wenn Sie Sicherheit auf Transportebene über HTTP(s) verwenden, fügen Sie entweder die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oder [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \< NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) oder ein [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , HTTP (S) verwendet und die `Basic` -Authentifizierungsschema.</span><span class="sxs-lookup"><span data-stu-id="7adbf-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7adbf-117">Wenn Sie [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] oder höher verwenden, können Sie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement mit Nachrichten- und Transportsicherheit nutzen.</span><span class="sxs-lookup"><span data-stu-id="7adbf-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="7adbf-118">In Verbindung mit [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] kann ein benutzerdefiniertes Benutzername- und Kennwort-Validierungssteuerelement nur mit Nachrichtensicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7adbf-118">With [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], a custom username and password validator can only be used with message security.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="7adbf-119">Weitere Informationen zur Verwendung von \<NetTcpBinding > in diesem Kontext finden Sie unter [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7adbf-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span></span>  
  
    1.  <span data-ttu-id="7adbf-120">In der Konfigurationsdatei unter der [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element, Hinzufügen einer [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element.</span><span class="sxs-lookup"><span data-stu-id="7adbf-120">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
    2.  <span data-ttu-id="7adbf-121">Hinzufügen einer [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oder [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Element im Abschnitt über Bindungen.</span><span class="sxs-lookup"><span data-stu-id="7adbf-121">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="7adbf-122">Weitere Informationen zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding-Element, finden Sie unter [wie: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7adbf-122">For more information about creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
    3.  <span data-ttu-id="7adbf-123">Legen Sie die `mode` Attribut des der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) oder [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) auf `Message`, `Transport`, `or``TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="7adbf-123">Set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, `or``TransportWithMessageCredential`.</span></span>  
  
    4.  <span data-ttu-id="7adbf-124">Legen Sie die `clientCredentialType` Attribut von der [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) oder [ \<Transport >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7adbf-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>  
  
         <span data-ttu-id="7adbf-125">Legen Sie bei Verwendung von nachrichtensicherheit die `clientCredentialType` Attribut des der [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) auf `UserName`.</span><span class="sxs-lookup"><span data-stu-id="7adbf-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>  
  
         <span data-ttu-id="7adbf-126">Wenn Sicherheit auf Transportebene über HTTP(s) verwenden, legen Sie die `clientCredentialType` Attribut des der [ \<Transport >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) oder [ \<Transport >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) auf `Basic`.</span><span class="sxs-lookup"><span data-stu-id="7adbf-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="7adbf-127">Wenn ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst in Internet Information Services (IIS) unter Verwendung von Sicherheit auf Transportebene gehostet wird und die <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> festgelegt ist, dann verwendet das benutzerdefinierte Authentifizierungsschema eine Teilmenge der Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="7adbf-127">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="7adbf-128">Das liegt daran, dass IIS in diesem Szenario die Windows-Authentifizierung ausführt, bevor [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] den benutzerdefinierten Authentifizierer aufruft</span><span class="sxs-lookup"><span data-stu-id="7adbf-128">That is because in this scenario, IIS performs Windows authentication prior to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoking the custom authenticator.</span></span>  
  
     <span data-ttu-id="7adbf-129">Weitere Informationen zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding-Element, finden Sie unter [wie: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7adbf-129">For more information about creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
     <span data-ttu-id="7adbf-130">Das folgende Beispiel zeigt den Konfigurationscode für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="7adbf-130">The following example shows the configuration code for the binding.</span></span>  
  
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
  
2.  <span data-ttu-id="7adbf-131">Konfigurieren Sie ein Verhalten, das angibt, dass ein benutzerdefiniertes Benutzername- und Kennwort-Validierungssteuerelement verwendet wird, um Benutzernamen/Kennwort-Paare für eingehende <xref:System.IdentityModel.Tokens.UserNameSecurityToken>-Sicherheitstoken zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7adbf-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>  
  
    1.  <span data-ttu-id="7adbf-132">Als untergeordnetes Element der [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element, Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element.</span><span class="sxs-lookup"><span data-stu-id="7adbf-132">As a child to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    2.  <span data-ttu-id="7adbf-133">Hinzufügen einer [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf die [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element.</span><span class="sxs-lookup"><span data-stu-id="7adbf-133">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    3.  <span data-ttu-id="7adbf-134">Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) Element, und legen die `name` -Attribut auf einen geeigneten Wert.</span><span class="sxs-lookup"><span data-stu-id="7adbf-134">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
    4.  <span data-ttu-id="7adbf-135">Hinzufügen einer [ \<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) auf die [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) Element.</span><span class="sxs-lookup"><span data-stu-id="7adbf-135">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
    5.  <span data-ttu-id="7adbf-136">Hinzufügen einer [ \<UserNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) auf die [ \<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="7adbf-136">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
    6.  <span data-ttu-id="7adbf-137">Legen Sie `userNamePasswordValidationMode` auf `Custom` fest</span><span class="sxs-lookup"><span data-stu-id="7adbf-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="7adbf-138">Wenn der `userNamePasswordValidationMode`-Wert nicht festgelegt wird, verwendet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Windows-Authentifizierung anstatt des benutzerdefinierten Benutzernamen- und Kennwort-Validierungssteuerelements.</span><span class="sxs-lookup"><span data-stu-id="7adbf-138">If the `userNamePasswordValidationMode` value is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses Windows authentication instead of the custom user name and password validator.</span></span>  
  
    7.  <span data-ttu-id="7adbf-139">Legen Sie den `customUserNamePasswordValidatorType` auf den Typ fest, der das benutzerdefinierte Benutzernamen- und Kennwort-Validierungssteuerelement darstellt.</span><span class="sxs-lookup"><span data-stu-id="7adbf-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>  
  
     <span data-ttu-id="7adbf-140">Im folgenden Beispiel sehen Sie das `<serviceCredentials>`-Fragment bis zu diesem Punkt:</span><span class="sxs-lookup"><span data-stu-id="7adbf-140">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a><span data-ttu-id="7adbf-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7adbf-141">Example</span></span>  
 <span data-ttu-id="7adbf-142">Im folgenden Codebeispiel wird veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7adbf-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="7adbf-143">Verwenden Sie nicht den Code, der die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode in einer Produktionsumgebung außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="7adbf-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="7adbf-144">Ersetzen Sie den Code mit dem benutzerdefinierten Benutzernamen- und Kennwort-Validierungsschema. Möglicherweise müssen der Benutzername und das zugehörige Kennwort aus einer Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7adbf-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7adbf-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7adbf-145">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>  
 [<span data-ttu-id="7adbf-146">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="7adbf-146">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 [<span data-ttu-id="7adbf-147">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7adbf-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
