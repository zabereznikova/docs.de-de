---
title: '&lt;security&gt; von &lt;wsFederationHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: dd4f517c17efce85f7a83d7d8545cf58322d5373
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="31250-102">&lt;security&gt; von &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="31250-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="31250-103">Definiert die Sicherheitseinstellungen für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="31250-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="31250-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="31250-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="31250-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="31250-105">\<bindings></span></span>  
<span data-ttu-id="31250-106">\<WsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="31250-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="31250-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="31250-107">\<binding></span></span>  
<span data-ttu-id="31250-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="31250-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31250-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="31250-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31250-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="31250-110">Attributes and Elements</span></span>  
 <span data-ttu-id="31250-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31250-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31250-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="31250-112">Attributes</span></span>  
  
|<span data-ttu-id="31250-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="31250-113">Attribute</span></span>|<span data-ttu-id="31250-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31250-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31250-115">Modus</span><span class="sxs-lookup"><span data-stu-id="31250-115">Mode</span></span>|<span data-ttu-id="31250-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="31250-116">Optional.</span></span> <span data-ttu-id="31250-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="31250-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="31250-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="31250-118">The default value is `Message`.</span></span> <span data-ttu-id="31250-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="31250-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="31250-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="31250-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="31250-121">Wert</span><span class="sxs-lookup"><span data-stu-id="31250-121">Value</span></span>|<span data-ttu-id="31250-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31250-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="31250-123">Keine</span><span class="sxs-lookup"><span data-stu-id="31250-123">None</span></span>|<span data-ttu-id="31250-124">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="31250-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="31250-125">Meldung</span><span class="sxs-lookup"><span data-stu-id="31250-125">Message</span></span>|<span data-ttu-id="31250-126">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="31250-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="31250-127">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="31250-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="31250-128">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="31250-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="31250-129">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="31250-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="31250-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="31250-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="31250-131">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="31250-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="31250-132">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="31250-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="31250-133">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="31250-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31250-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31250-134">Child Elements</span></span>  
  
|<span data-ttu-id="31250-135">Element</span><span class="sxs-lookup"><span data-stu-id="31250-135">Element</span></span>|<span data-ttu-id="31250-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31250-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31250-137">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="31250-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="31250-138">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="31250-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="31250-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="31250-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31250-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31250-140">Parent Elements</span></span>  
  
|<span data-ttu-id="31250-141">Element</span><span class="sxs-lookup"><span data-stu-id="31250-141">Element</span></span>|<span data-ttu-id="31250-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31250-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31250-143">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="31250-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="31250-144">Definiert alle bindungsmöglichkeiten der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="31250-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31250-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31250-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="31250-146">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="31250-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="31250-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="31250-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="31250-148">Auswählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="31250-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="31250-149">Bindungen</span><span class="sxs-lookup"><span data-stu-id="31250-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="31250-150">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="31250-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="31250-151">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="31250-151">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="31250-152">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="31250-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
