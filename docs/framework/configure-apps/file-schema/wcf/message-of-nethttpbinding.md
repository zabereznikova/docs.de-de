---
title: <message> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 5bc953b4a1fad90aec5db507469368e7b21bb7e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105455"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="8de86-102">\<Message > von \<NetHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8de86-102">\<message> of \<netHttpBinding></span></span>
<span data-ttu-id="8de86-103">Definiert die Einstellungen für Sicherheit auf Nachrichtenebene, der die [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8de86-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="8de86-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8de86-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8de86-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8de86-105">\<bindings></span></span>  
<span data-ttu-id="8de86-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8de86-106">\<netHttpBinding></span></span>  
<span data-ttu-id="8de86-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8de86-107">\<binding></span></span>  
<span data-ttu-id="8de86-108">\<security></span><span class="sxs-lookup"><span data-stu-id="8de86-108">\<security></span></span>  
<span data-ttu-id="8de86-109">\<message></span><span class="sxs-lookup"><span data-stu-id="8de86-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de86-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="8de86-110">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8de86-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8de86-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8de86-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8de86-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8de86-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="8de86-113">Attributes</span></span>  
  
|<span data-ttu-id="8de86-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="8de86-114">Attribute</span></span>|<span data-ttu-id="8de86-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8de86-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8de86-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="8de86-116">algorithmSuite</span></span>|<span data-ttu-id="8de86-117">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="8de86-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="8de86-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> und gibt die Algorithmen und Schlüsselgrößen an.</span><span class="sxs-lookup"><span data-stu-id="8de86-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="8de86-119">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="8de86-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="8de86-120">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="8de86-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="8de86-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8de86-121">clientCredentialType</span></span>|<span data-ttu-id="8de86-122">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mithilfe von nachrichtenbasierter Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8de86-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="8de86-123">Die Standardeinstellung ist `UserName`.</span><span class="sxs-lookup"><span data-stu-id="8de86-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8de86-124">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="8de86-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8de86-125">Wert</span><span class="sxs-lookup"><span data-stu-id="8de86-125">Value</span></span>|<span data-ttu-id="8de86-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8de86-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8de86-127">UserName</span><span class="sxs-lookup"><span data-stu-id="8de86-127">UserName</span></span>|<span data-ttu-id="8de86-128">– Erfordert der Client an den Server mit einem UserName authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="8de86-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="8de86-129">Diese Anmeldeinformationen müssen angegeben werden, mithilfe der <`clientCredentials`> Element.</span><span class="sxs-lookup"><span data-stu-id="8de86-129">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="8de86-130">-WCF unterstützt Kennwortdigest ableitenden Schlüssel mit Kennwörtern sowie die Verwendung solcher Schlüssel für die nachrichtensicherheit nicht.</span><span class="sxs-lookup"><span data-stu-id="8de86-130">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="8de86-131">Aus diesem Grund erzwingt WCF an, dass der Transport geschützt werden, wenn UserName-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8de86-131">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="8de86-132">Bei `basicHttpBinding` erfordert dies die Einrichtung eines SSL-Kanals.</span><span class="sxs-lookup"><span data-stu-id="8de86-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="8de86-133">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="8de86-133">Certificate</span></span>|<span data-ttu-id="8de86-134">Erfordert, dass der Client über ein Zertifikat beim Server authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="8de86-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="8de86-135">In diesem Fall muss die Client-Anmeldeinformationen angegeben werden mithilfe von <`clientCredentials`> und <`clientCertificate`>.</span><span class="sxs-lookup"><span data-stu-id="8de86-135">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="8de86-136">Außerdem muss für den Fall, dass der Nachrichtensicherheitsmodus verwendet wird, dem Client das Dienstzertifikat bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8de86-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="8de86-137">Die Dienstanmeldeinformationen muss in diesem Fall unter Verwendung <xref:System.ServiceModel.Description.ClientCredentials> Klasse oder `ClientCredentials` -verhaltenselement und durch Angabe des Dienstzertifikats mit der \<ServiceCertificate >-Element von ServiceCredentials.</span><span class="sxs-lookup"><span data-stu-id="8de86-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8de86-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8de86-138">Child Elements</span></span>  
 <span data-ttu-id="8de86-139">Keiner</span><span class="sxs-lookup"><span data-stu-id="8de86-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8de86-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8de86-140">Parent Elements</span></span>  
  
|<span data-ttu-id="8de86-141">Element</span><span class="sxs-lookup"><span data-stu-id="8de86-141">Element</span></span>|<span data-ttu-id="8de86-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8de86-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8de86-143"><`security`>-Element von <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="8de86-143"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="8de86-144">Definiert die Sicherheitsfunktionen für die <`netHttpBinding`> Element.</span><span class="sxs-lookup"><span data-stu-id="8de86-144">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8de86-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8de86-145">Example</span></span>  
 <span data-ttu-id="8de86-146">In diesem Beispiel wird veranschaulicht, wie eine Anwendung implementiert wird, die basicHttpBinding und Nachrichtensicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="8de86-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="8de86-147">Im folgenden Konfigurationsbeispiel für einen Dienst gibt die Endpunktdefinition die basicHttpBinding an und verweist auf die Bindungskonfiguration `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="8de86-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="8de86-148">Das Zertifikat, das der Dienst zur Authentifizierung beim Client verwendet, wird im `behaviors`-Abschnitt der Konfigurationsdatei im `serviceCredentials`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8de86-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="8de86-149">Der Prüfungsmodus für das Zertifikat, das der Client zum Authentifizieren beim Dienst verwendet, ist auch im `behaviors`-Abschnitt im `clientCertificate`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8de86-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="8de86-150">Die gleichen Bindungs- und Sicherheitsinformationen sind in der Clientkonfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="8de86-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <!-- This configuration defines the SecurityMode as Message and
           the clientCredentialType as Certificate. -->
      <binding name="Binding1" >
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
                 is in the user's Trusted People store, then it will be trusted without performing a
                 validation of the certificate's issuer chain. This setting is used here for convenience so that the
                 sample can be run without having to have certificates issued by a certification authority (CA).
                 This setting is less secure than the default, ChainTrust. The security implications of this
                 setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="8de86-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8de86-151">See also</span></span>

- [<span data-ttu-id="8de86-152">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="8de86-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8de86-153">Bindungen</span><span class="sxs-lookup"><span data-stu-id="8de86-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8de86-154">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="8de86-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8de86-155">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="8de86-155">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8de86-156">\<binding></span><span class="sxs-lookup"><span data-stu-id="8de86-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
