---
title: <message> von <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: 8b1e889efc53d0132368111037399ea8872008b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204865"
---
# <a name="message-of-basichttpbinding"></a><span data-ttu-id="6e280-102">\<message> von \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6e280-102">\<message> of \<basicHttpBinding></span></span>

<span data-ttu-id="6e280-103">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6e280-103">Defines the settings for message-level security of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="6e280-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e280-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e280-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6e280-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6e280-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e280-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e280-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="6e280-107">Attributes</span></span>  
  
|<span data-ttu-id="6e280-108">attribute</span><span class="sxs-lookup"><span data-stu-id="6e280-108">Attribute</span></span>|<span data-ttu-id="6e280-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e280-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e280-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="6e280-110">algorithmSuite</span></span>|<span data-ttu-id="6e280-111">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="6e280-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="6e280-112">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> und gibt die Algorithmen und Schlüsselgrößen an.</span><span class="sxs-lookup"><span data-stu-id="6e280-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="6e280-113">Diese Algorithmen sind den Algorithmen in der Spezifikation der Sicherheitsrichtliniensprache (WS-SecurityPolicy) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6e280-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="6e280-114">Standardwert: `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="6e280-114">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="6e280-115">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="6e280-115">clientCredentialType</span></span>|<span data-ttu-id="6e280-116">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mithilfe von nachrichtenbasierter Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e280-116">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="6e280-117">Der Standardwert lautet `UserName`.</span><span class="sxs-lookup"><span data-stu-id="6e280-117">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="6e280-118">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="6e280-118">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6e280-119">Wert</span><span class="sxs-lookup"><span data-stu-id="6e280-119">Value</span></span>|<span data-ttu-id="6e280-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e280-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e280-121">UserName</span><span class="sxs-lookup"><span data-stu-id="6e280-121">UserName</span></span>|<span data-ttu-id="6e280-122">: Erfordert, dass der Client mit Benutzernamen-Anmelde Informationen auf dem Server authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="6e280-122">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="6e280-123">Diese Anmelde Informationen müssen mithilfe von angegeben werden [\<clientCredentials>](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="6e280-123">This credential needs to be specified using the [\<clientCredentials>](clientcredentials.md).</span></span><br /><span data-ttu-id="6e280-124">-WCF unterstützt nicht das Senden eines Kenn Wort Hashwerts oder das Ableiten von Schlüsseln mit Kenn Wörtern und die Verwendung solcher Schlüssel für die Nachrichten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="6e280-124">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="6e280-125">Daher erzwingt WCF, dass der Transport geschützt wird, wenn Benutzernamen Anmelde Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e280-125">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="6e280-126">Bei `basicHttpBinding` erfordert dies die Einrichtung eines SSL-Kanals.</span><span class="sxs-lookup"><span data-stu-id="6e280-126">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="6e280-127">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="6e280-127">Certificate</span></span>|<span data-ttu-id="6e280-128">Erfordert, dass der Client über ein Zertifikat beim Server authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="6e280-128">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="6e280-129">Die Client Anmelde Informationen müssen in diesem Fall mithilfe von und angegeben werden [\<clientCredentials>](clientcredentials.md) [\<clientCertificate>](clientcertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="6e280-129">The client credential in this case needs to be specified using [\<clientCredentials>](clientcredentials.md) and the [\<clientCertificate>](clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="6e280-130">Außerdem muss für den Fall, dass der Nachrichtensicherheitsmodus verwendet wird, dem Client das Dienstzertifikat bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6e280-130">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="6e280-131">Die Dienst Anmelde Informationen müssen in diesem Fall mithilfe <xref:System.ServiceModel.Description.ClientCredentials> der-Klasse oder dem `ClientCredentials` Behavior-Element angegeben werden und das Dienst Zertifikat mithilfe von angegeben werden [\<serviceCertificate>](servicecertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="6e280-131">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e280-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e280-132">Child Elements</span></span>  

 <span data-ttu-id="6e280-133">Keine</span><span class="sxs-lookup"><span data-stu-id="6e280-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e280-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e280-134">Parent Elements</span></span>  
  
|<span data-ttu-id="6e280-135">Element</span><span class="sxs-lookup"><span data-stu-id="6e280-135">Element</span></span>|<span data-ttu-id="6e280-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e280-136">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="6e280-137">Definiert die Sicherheitsfunktionen für [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6e280-137">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6e280-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e280-138">Example</span></span>  

 <span data-ttu-id="6e280-139">In diesem Beispiel wird veranschaulicht, wie eine Anwendung implementiert wird, die basicHttpBinding und Nachrichtensicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e280-139">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="6e280-140">Im folgenden Konfigurationsbeispiel für einen Dienst gibt die Endpunktdefinition die basicHttpBinding an und verweist auf die Bindungskonfiguration `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="6e280-140">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="6e280-141">Das Zertifikat, das der Dienst zur Authentifizierung beim Client verwendet, wird im `behaviors`-Abschnitt der Konfigurationsdatei im `serviceCredentials`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6e280-141">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="6e280-142">Der Prüfungsmodus für das Zertifikat, das der Client zum Authentifizieren beim Dienst verwendet, ist auch im `behaviors`-Abschnitt im `clientCertificate`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6e280-142">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="6e280-143">Die gleichen Bindungs- und Sicherheitsinformationen sind in der Clientkonfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="6e280-143">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service -->
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
      <binding name="Binding1">
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
  
## <a name="see-also"></a><span data-ttu-id="6e280-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e280-144">See also</span></span>

- <xref:System.ServiceModel.BasicHttpMessageSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>
- [<span data-ttu-id="6e280-145">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="6e280-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6e280-146">Bindungen</span><span class="sxs-lookup"><span data-stu-id="6e280-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6e280-147">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="6e280-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6e280-148">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="6e280-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
