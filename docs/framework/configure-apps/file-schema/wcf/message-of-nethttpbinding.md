---
title: <message> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 62b1793d18ddc8edc1f55b02137c4e0a9f7327d2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738963"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="7af8f-102">\<message> von \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7af8f-102">\<message> of \<netHttpBinding></span></span>
<span data-ttu-id="7af8f-103">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7af8f-103">Defines the settings for message-level security of the [\<netHttpBinding>](nethttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="7af8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7af8f-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7af8f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7af8f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7af8f-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7af8f-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7af8f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7af8f-107">Attributes</span></span>  
  
|<span data-ttu-id="7af8f-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7af8f-108">Attribute</span></span>|<span data-ttu-id="7af8f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7af8f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7af8f-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="7af8f-110">algorithmSuite</span></span>|<span data-ttu-id="7af8f-111">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="7af8f-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="7af8f-112">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> und gibt die Algorithmen und Schlüsselgrößen an.</span><span class="sxs-lookup"><span data-stu-id="7af8f-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="7af8f-113">Diese Algorithmen sind den Algorithmen in der Spezifikation der Sicherheitsrichtliniensprache (WS-SecurityPolicy) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7af8f-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="7af8f-114">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="7af8f-114">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="7af8f-115">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7af8f-115">clientCredentialType</span></span>|<span data-ttu-id="7af8f-116">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mithilfe von nachrichtenbasierter Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7af8f-116">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="7af8f-117">Der Standardwert lautet `UserName`.</span><span class="sxs-lookup"><span data-stu-id="7af8f-117">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7af8f-118">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="7af8f-118">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7af8f-119">Wert</span><span class="sxs-lookup"><span data-stu-id="7af8f-119">Value</span></span>|<span data-ttu-id="7af8f-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7af8f-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7af8f-121">UserName</span><span class="sxs-lookup"><span data-stu-id="7af8f-121">UserName</span></span>|<span data-ttu-id="7af8f-122">: Erfordert, dass der Client mit Benutzernamen-Anmelde Informationen auf dem Server authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="7af8f-122">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="7af8f-123">Diese Anmelde Informationen müssen mithilfe des <>-Elements angegeben werden `clientCredentials` .</span><span class="sxs-lookup"><span data-stu-id="7af8f-123">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="7af8f-124">-WCF unterstützt nicht das Senden eines Kenn Wort Hashwerts oder das Ableiten von Schlüsseln mit Kenn Wörtern und die Verwendung solcher Schlüssel für die Nachrichten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="7af8f-124">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="7af8f-125">Daher erzwingt WCF, dass der Transport geschützt wird, wenn Benutzernamen Anmelde Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7af8f-125">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="7af8f-126">Bei `basicHttpBinding` erfordert dies die Einrichtung eines SSL-Kanals.</span><span class="sxs-lookup"><span data-stu-id="7af8f-126">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="7af8f-127">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="7af8f-127">Certificate</span></span>|<span data-ttu-id="7af8f-128">Erfordert, dass der Client über ein Zertifikat beim Server authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="7af8f-128">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="7af8f-129">Die Client Anmelde Informationen müssen in diesem Fall mithilfe <`clientCredentials`> und der <> angegeben werden `clientCertificate` .</span><span class="sxs-lookup"><span data-stu-id="7af8f-129">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="7af8f-130">Außerdem muss für den Fall, dass der Nachrichtensicherheitsmodus verwendet wird, dem Client das Dienstzertifikat bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7af8f-130">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="7af8f-131">Die Dienst Anmelde Informationen müssen in diesem Fall mithilfe <xref:System.ServiceModel.Description.ClientCredentials> der-Klasse oder dem `ClientCredentials` Behavior-Element angegeben werden, und das Dienst Zertifikat wird mithilfe des- \<serviceCertificate> Elements von servicecredential angegeben.</span><span class="sxs-lookup"><span data-stu-id="7af8f-131">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7af8f-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7af8f-132">Child Elements</span></span>  
 <span data-ttu-id="7af8f-133">Keine</span><span class="sxs-lookup"><span data-stu-id="7af8f-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7af8f-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7af8f-134">Parent Elements</span></span>  
  
|<span data-ttu-id="7af8f-135">Element</span><span class="sxs-lookup"><span data-stu-id="7af8f-135">Element</span></span>|<span data-ttu-id="7af8f-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7af8f-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7af8f-137"><`security`> Element von <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="7af8f-137"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="7af8f-138">Definiert die Sicherheitsfunktionen für das <`netHttpBinding`>-Element.</span><span class="sxs-lookup"><span data-stu-id="7af8f-138">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7af8f-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7af8f-139">Example</span></span>  
 <span data-ttu-id="7af8f-140">In diesem Beispiel wird veranschaulicht, wie eine Anwendung implementiert wird, die basicHttpBinding und Nachrichtensicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="7af8f-140">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="7af8f-141">Im folgenden Konfigurationsbeispiel für einen Dienst gibt die Endpunktdefinition die basicHttpBinding an und verweist auf die Bindungskonfiguration `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="7af8f-141">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="7af8f-142">Das Zertifikat, das der Dienst zur Authentifizierung beim Client verwendet, wird im `behaviors`-Abschnitt der Konfigurationsdatei im `serviceCredentials`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7af8f-142">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="7af8f-143">Der Prüfungsmodus für das Zertifikat, das der Client zum Authentifizieren beim Dienst verwendet, ist auch im `behaviors`-Abschnitt im `clientCertificate`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7af8f-143">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="7af8f-144">Die gleichen Bindungs- und Sicherheitsinformationen sind in der Clientkonfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="7af8f-144">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7af8f-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7af8f-145">See also</span></span>

- [<span data-ttu-id="7af8f-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7af8f-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7af8f-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7af8f-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7af8f-148">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="7af8f-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7af8f-149">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7af8f-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
