---
title: '&lt;security&gt; von &lt;wsFederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
author: BrucePerlerMS
ms.openlocfilehash: 7c7868561ea4d41b308d3bcd963e10e9b81df314
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078239"
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="86433-102">&lt;security&gt; von &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="86433-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="86433-103">Definiert die Sicherheitseinstellungen der [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="86433-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="86433-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="86433-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="86433-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="86433-105">\<bindings></span></span>  
<span data-ttu-id="86433-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="86433-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="86433-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="86433-107">\<binding></span></span>  
<span data-ttu-id="86433-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="86433-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86433-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="86433-109">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
    <binding >  
       <security mode="None/Message/TransportWithMessageCredential">  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                                 <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
         </message>  
       </security>  
    </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86433-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86433-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86433-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86433-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86433-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="86433-112">Attributes</span></span>  
  
|<span data-ttu-id="86433-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="86433-113">Attribute</span></span>|<span data-ttu-id="86433-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86433-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86433-115">Modus</span><span class="sxs-lookup"><span data-stu-id="86433-115">Mode</span></span>|<span data-ttu-id="86433-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="86433-116">Optional.</span></span> <span data-ttu-id="86433-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="86433-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="86433-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="86433-118">The default value is `Message`.</span></span> <span data-ttu-id="86433-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="86433-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="86433-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="86433-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="86433-121">Wert</span><span class="sxs-lookup"><span data-stu-id="86433-121">Value</span></span>|<span data-ttu-id="86433-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86433-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="86433-123">Keine</span><span class="sxs-lookup"><span data-stu-id="86433-123">None</span></span>|<span data-ttu-id="86433-124">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="86433-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="86433-125">Meldung</span><span class="sxs-lookup"><span data-stu-id="86433-125">Message</span></span>|<span data-ttu-id="86433-126">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="86433-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="86433-127">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="86433-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="86433-128">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="86433-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="86433-129">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="86433-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="86433-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="86433-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="86433-131">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="86433-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="86433-132">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="86433-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="86433-133">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="86433-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86433-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86433-134">Child Elements</span></span>  
  
|<span data-ttu-id="86433-135">Element</span><span class="sxs-lookup"><span data-stu-id="86433-135">Element</span></span>|<span data-ttu-id="86433-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86433-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86433-137">\<message></span><span class="sxs-lookup"><span data-stu-id="86433-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="86433-138">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="86433-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="86433-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="86433-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86433-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86433-140">Parent Elements</span></span>  
  
|<span data-ttu-id="86433-141">Element</span><span class="sxs-lookup"><span data-stu-id="86433-141">Element</span></span>|<span data-ttu-id="86433-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86433-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86433-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="86433-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="86433-144">Definiert alle bindungsfähigkeiten von der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="86433-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86433-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86433-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="86433-146">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="86433-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="86433-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="86433-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="86433-148">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="86433-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="86433-149">Bindungen</span><span class="sxs-lookup"><span data-stu-id="86433-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="86433-150">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="86433-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="86433-151">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="86433-151">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="86433-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="86433-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
