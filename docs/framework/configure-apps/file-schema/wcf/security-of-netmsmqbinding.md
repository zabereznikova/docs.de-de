---
title: <security> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 1bbc3a460ce707e71b72a469af2e03acd8dc79e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936691"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="c1cff-102">\<security> of \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="c1cff-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="c1cff-103">Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung.</span><span class="sxs-lookup"><span data-stu-id="c1cff-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="c1cff-104">Dadurch wird angegeben, ob die Transportsicherheit oder die SOAP-Sicherheit aktiviert sind und ggf. welcher Authentifizierungsmodus und welche Schutzebenen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1cff-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="c1cff-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1cff-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1cff-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c1cff-106">\<bindings></span></span>  
<span data-ttu-id="c1cff-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="c1cff-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="c1cff-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="c1cff-108">\<binding></span></span>  
<span data-ttu-id="c1cff-109">\<security></span><span class="sxs-lookup"><span data-stu-id="c1cff-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1cff-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1cff-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1cff-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1cff-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c1cff-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1cff-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1cff-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1cff-113">Attributes</span></span>  
  
|<span data-ttu-id="c1cff-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c1cff-114">Attribute</span></span>|<span data-ttu-id="c1cff-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1cff-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1cff-116">Modus</span><span class="sxs-lookup"><span data-stu-id="c1cff-116">mode</span></span>|<span data-ttu-id="c1cff-117">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung steuert.</span><span class="sxs-lookup"><span data-stu-id="c1cff-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="c1cff-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="c1cff-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c1cff-119">Gar Dadurch wird die Sicherheit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c1cff-119">-   None: This disables security.</span></span><br /><span data-ttu-id="c1cff-120">Personen Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c1cff-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="c1cff-121">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="c1cff-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="c1cff-122">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="c1cff-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="c1cff-123">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="c1cff-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="c1cff-124">Vermitteln Gibt die End-End-Anwendungssicherheit an.</span><span class="sxs-lookup"><span data-stu-id="c1cff-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="c1cff-125">Es wird keine Sicherheit auf Transportebene bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c1cff-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="c1cff-126">Dies ähnelt der Sicherheit, die von anderen Standardbindungen angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="c1cff-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="c1cff-127">Zwar Bietet Sicherheit auf Transport-und SOAP-Messaging Ebene.</span><span class="sxs-lookup"><span data-stu-id="c1cff-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="c1cff-128">Auf beiden Ebenen sind die gleichen Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c1cff-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="c1cff-129">Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="c1cff-129">The default value is Transport.</span></span> <span data-ttu-id="c1cff-130">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c1cff-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1cff-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1cff-131">Child Elements</span></span>  
  
|<span data-ttu-id="c1cff-132">Element</span><span class="sxs-lookup"><span data-stu-id="c1cff-132">Element</span></span>|<span data-ttu-id="c1cff-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1cff-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1cff-134">\<message></span><span class="sxs-lookup"><span data-stu-id="c1cff-134">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="c1cff-135">Definiert die SOAP-Nachrichtensicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="c1cff-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="c1cff-136">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="c1cff-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="c1cff-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="c1cff-137">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="c1cff-138">Definiert die Sicherheitseinstellungen für den MSMQ-Transport.</span><span class="sxs-lookup"><span data-stu-id="c1cff-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="c1cff-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c1cff-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1cff-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1cff-140">Parent Elements</span></span>  
  
|<span data-ttu-id="c1cff-141">Element</span><span class="sxs-lookup"><span data-stu-id="c1cff-141">Element</span></span>|<span data-ttu-id="c1cff-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1cff-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1cff-143">Bindung</span><span class="sxs-lookup"><span data-stu-id="c1cff-143">binding</span></span>|<span data-ttu-id="c1cff-144">Das Bindungs Element der [ \<NetMsmqBinding->](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c1cff-144">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1cff-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1cff-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="c1cff-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="c1cff-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c1cff-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c1cff-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c1cff-148">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="c1cff-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c1cff-149">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c1cff-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c1cff-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="c1cff-150">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="c1cff-151">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="c1cff-151">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
