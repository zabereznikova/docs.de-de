---
title: 'Vorgehensweise: Erstellen eines Dienstes, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb38d8310d22b8128c76ed77f06a49c9576db33d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="9b53b-102">Vorgehensweise: Erstellen eines Dienstes, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="9b53b-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="9b53b-103">In diesem Thema wird gezeigt, wie Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement implementieren und wie Sie Anmeldeinformationen für Clients oder Dienste konfigurieren, um die standardmäßige Zertifikatüberprüfungslogik durch das benutzerdefinierte Zertifikats-Validierungssteuerelement zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9b53b-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="9b53b-104">Wenn das X.509-Zertifikat verwendet wird, um einen Client oder Dienst zu authentifizieren, nutzt [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] standardmäßig den Windows-Zertifikatspeicher und die Kryptografie-API, um das Zertifikat zu überprüfen und sicherzustellen, dass es vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="9b53b-104">If the X.509 certificate is used to authenticate a client or service, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="9b53b-105">Es kann vorkommen, dass die integrierten Funktionen zur Zertifikatsvalidierung nicht ausreichen und geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9b53b-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9b53b-106"> bietet eine einfache Möglichkeit zum Ändern der Validierungslogik, indem es Benutzern erlaubt wird, ein benutzerdefiniertes Zertifikats-Validierungssteuerelement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b53b-106"> provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="9b53b-107">Wenn Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement angeben, verwendet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht die integrierte Validierungslogik für Zertifikate, sondern nutzt stattdessen das benutzerdefinierte Validierungssteuerelement.</span><span class="sxs-lookup"><span data-stu-id="9b53b-107">If a custom certificate validator is specified, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9b53b-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="9b53b-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="9b53b-109">So erstellen Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="9b53b-109">To create a custom certificate validator</span></span>  
  
1.  <span data-ttu-id="9b53b-110">Definieren Sie eine neue Klasse, die von <xref:System.IdentityModel.Selectors.X509CertificateValidator> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="9b53b-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2.  <span data-ttu-id="9b53b-111">Implementieren Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="9b53b-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="9b53b-112">Das Zertifikat, das überprüft werden muss, wird als Argument an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="9b53b-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="9b53b-113">Wenn das übergebene Zertifikat gemäß der Validierungslogik nicht gültig ist, löst diese Methode eine <xref:System.IdentityModel.Tokens.SecurityTokenValidationException> aus.</span><span class="sxs-lookup"><span data-stu-id="9b53b-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="9b53b-114">Wenn das Zertifikat gültig ist, gibt die Methode einen Wert an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="9b53b-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b53b-115">Um dem Client Authentifizierungsfehler zurückzugeben, lösen Sie in der <xref:System.ServiceModel.FaultException>-Methode eine <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> aus.</span><span class="sxs-lookup"><span data-stu-id="9b53b-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="9b53b-116">So geben Sie bei der Dienstkonfiguration ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an</span><span class="sxs-lookup"><span data-stu-id="9b53b-116">To specify a custom certificate validator in service configuration</span></span>  
  
1.  <span data-ttu-id="9b53b-117">Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element und ein [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf die [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9b53b-117">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="9b53b-118">Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) und legen Sie die `name` -Attribut auf einen geeigneten Wert.</span><span class="sxs-lookup"><span data-stu-id="9b53b-118">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="9b53b-119">Hinzufügen einer [ \<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) auf die `<behavior>` Element.</span><span class="sxs-lookup"><span data-stu-id="9b53b-119">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4.  <span data-ttu-id="9b53b-120">Fügen Sie dem `<clientCertificate>`-Element ein `<serviceCredentials>`-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="9b53b-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5.  <span data-ttu-id="9b53b-121">Hinzufügen einer [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) auf die `<clientCertificate>` Element.</span><span class="sxs-lookup"><span data-stu-id="9b53b-121">Add an [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6.  <span data-ttu-id="9b53b-122">Legen Sie das `customCertificateValidatorType`-Attribut auf den Validierungssteuerelementtyp fest.</span><span class="sxs-lookup"><span data-stu-id="9b53b-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="9b53b-123">Im folgenden Beispiel wird das Attribut auf den Namespace und den Namen des Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9b53b-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7.  <span data-ttu-id="9b53b-124">Legen Sie das `certificateValidationMode`-Attribut auf `Custom` fest.</span><span class="sxs-lookup"><span data-stu-id="9b53b-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="9b53b-125">So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie die Konfiguration auf dem Client verwenden</span><span class="sxs-lookup"><span data-stu-id="9b53b-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1.  <span data-ttu-id="9b53b-126">Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element und ein [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf die [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9b53b-126">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="9b53b-127">Hinzufügen einer [ \<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9b53b-127">Add an [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3.  <span data-ttu-id="9b53b-128">Fügen Sie ein `<behavior>`-Element hinzu, und legen Sie das `name`-Attribut auf einen passenden Wert fest.</span><span class="sxs-lookup"><span data-stu-id="9b53b-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="9b53b-129">Hinzufügen einer [ \<ClientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9b53b-129">Add a [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5.  <span data-ttu-id="9b53b-130">Hinzufügen einer [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="9b53b-130">Add a [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6.  <span data-ttu-id="9b53b-131">Hinzufügen einer [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b53b-131">Add an [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7.  <span data-ttu-id="9b53b-132">Legen Sie das `customCertificateValidatorType`-Attribut auf den Validierungssteuerelementtyp fest.</span><span class="sxs-lookup"><span data-stu-id="9b53b-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8.  <span data-ttu-id="9b53b-133">Legen Sie das `certificateValidationMode`-Attribut auf `Custom` fest.</span><span class="sxs-lookup"><span data-stu-id="9b53b-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="9b53b-134">Im folgenden Beispiel wird das Attribut auf den Namespace und den Namen des Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9b53b-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="9b53b-135">So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie Code auf der Dienstseite verwenden</span><span class="sxs-lookup"><span data-stu-id="9b53b-135">To specify a custom certificate validator using code on the service</span></span>  
  
1.  <span data-ttu-id="9b53b-136">Geben Sie das benutzerdefinierte Zertifikats-Validierungssteuerelement über die <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="9b53b-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="9b53b-137">Sie können auf die Dienstanmeldeinformationen mit der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9b53b-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2.  <span data-ttu-id="9b53b-138">Legen Sie die <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> fest.</span><span class="sxs-lookup"><span data-stu-id="9b53b-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="9b53b-139">So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie Code auf der Clientseite verwenden</span><span class="sxs-lookup"><span data-stu-id="9b53b-139">To specify a custom certificate validator using code on the client</span></span>  
  
1.  <span data-ttu-id="9b53b-140">Geben Sie das benutzerdefinierte Zertifikats-Validierungssteuerelement über die <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="9b53b-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="9b53b-141">Sie können auf die Clientanmeldeinformationen mit der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9b53b-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="9b53b-142">(Die Client-Klasse, die von generierten [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) immer leitet sich von der <xref:System.ServiceModel.ClientBase%601> Klasse.)</span><span class="sxs-lookup"><span data-stu-id="9b53b-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2.  <span data-ttu-id="9b53b-143">Legen Sie die <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> fest.</span><span class="sxs-lookup"><span data-stu-id="9b53b-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b53b-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b53b-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9b53b-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b53b-145">Description</span></span>  
 <span data-ttu-id="9b53b-146">Das folgende Beispiel zeigt eine Implementierung eines benutzerdefinierten Zertifikats-Validierungssteuerelements und seine Verwendung für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="9b53b-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9b53b-147">Code</span><span class="sxs-lookup"><span data-stu-id="9b53b-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9b53b-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b53b-148">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>
