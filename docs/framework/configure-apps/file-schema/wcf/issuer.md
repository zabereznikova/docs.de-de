---
title: '&lt;Aussteller&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dcd85443a802db2b6f2e0b1823dd6cb60ed8f705
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuergt"></a><span data-ttu-id="9571f-102">&lt;Aussteller&gt;</span><span class="sxs-lookup"><span data-stu-id="9571f-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="9571f-103">Gibt den Sicherheitstokendienst an, der Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="9571f-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="9571f-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9571f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9571f-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="9571f-105">\<bindings></span></span>  
<span data-ttu-id="9571f-106">\<WsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9571f-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="9571f-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="9571f-107">\<binding></span></span>  
<span data-ttu-id="9571f-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="9571f-108">\<security></span></span>  
<span data-ttu-id="9571f-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="9571f-109">\<message></span></span>  
<span data-ttu-id="9571f-110">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="9571f-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9571f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="9571f-111">Syntax</span></span>  
  
```xml  
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
                  x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
      <dns value="String"/>  
      <rsa value="String"/>  
      <servicePrincipalName value="String"/>  
      <usePrincipalName value="String"/>  
   </identity>  
</issuer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9571f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9571f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9571f-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9571f-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9571f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="9571f-114">Attributes</span></span>  
  
|<span data-ttu-id="9571f-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="9571f-115">Attribute</span></span>|<span data-ttu-id="9571f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9571f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9571f-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="9571f-117">address</span></span>|<span data-ttu-id="9571f-118">Erforderliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9571f-118">Required string.</span></span> <span data-ttu-id="9571f-119">Die URL des STS.</span><span class="sxs-lookup"><span data-stu-id="9571f-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9571f-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9571f-120">Child Elements</span></span>  
  
|<span data-ttu-id="9571f-121">Element</span><span class="sxs-lookup"><span data-stu-id="9571f-121">Element</span></span>|<span data-ttu-id="9571f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9571f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9571f-123">\<Header ></span><span class="sxs-lookup"><span data-stu-id="9571f-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="9571f-124">Eine Auflistung mit Adressheadern für die Endpunkte, die vom Generator erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="9571f-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="9571f-125">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="9571f-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="9571f-126">Gibt bei Verwendung eines ausgestellten Tokens die Einstellungen an, mit denen der Client den Server authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="9571f-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9571f-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9571f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="9571f-128">Element</span><span class="sxs-lookup"><span data-stu-id="9571f-128">Element</span></span>|<span data-ttu-id="9571f-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9571f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9571f-130">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="9571f-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="9571f-131">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9571f-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9571f-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9571f-132">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 [<span data-ttu-id="9571f-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9571f-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9571f-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="9571f-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9571f-135">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9571f-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9571f-136">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="9571f-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9571f-137">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="9571f-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="9571f-138">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="9571f-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
