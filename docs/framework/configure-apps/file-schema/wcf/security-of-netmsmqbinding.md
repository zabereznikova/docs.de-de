---
title: '&lt;security&gt; von &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0ed1021bdc45d0d64a20ff19410ad56e0d304ed3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750959"
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="bc938-102">&lt;security&gt; von &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="bc938-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="bc938-103">Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung.</span><span class="sxs-lookup"><span data-stu-id="bc938-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="bc938-104">Dadurch wird angegeben, ob die Transportsicherheit oder die SOAP-Sicherheit aktiviert sind und ggf. welcher Authentifizierungsmodus und welche Schutzebenen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc938-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="bc938-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bc938-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="bc938-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="bc938-106">\<bindings></span></span>  
<span data-ttu-id="bc938-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="bc938-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="bc938-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="bc938-108">\<binding></span></span>  
<span data-ttu-id="bc938-109">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="bc938-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc938-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc938-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc938-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bc938-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bc938-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc938-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc938-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="bc938-113">Attributes</span></span>  
  
|<span data-ttu-id="bc938-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="bc938-114">Attribute</span></span>|<span data-ttu-id="bc938-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc938-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bc938-116">Modus</span><span class="sxs-lookup"><span data-stu-id="bc938-116">mode</span></span>|<span data-ttu-id="bc938-117">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung steuert.</span><span class="sxs-lookup"><span data-stu-id="bc938-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="bc938-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="bc938-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bc938-119">-"None": Die Sicherheit wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bc938-119">-   None: This disables security.</span></span><br /><span data-ttu-id="bc938-120">-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bc938-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="bc938-121">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="bc938-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="bc938-122">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="bc938-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="bc938-123">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="bc938-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="bc938-124">-Nachricht: Gibt die Ende-anwendungssicherheit an.</span><span class="sxs-lookup"><span data-stu-id="bc938-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="bc938-125">Es wird keine Sicherheit auf Transportebene bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bc938-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="bc938-126">Dies ähnelt der Sicherheit, die von anderen Standardbindungen angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="bc938-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="bc938-127">-Both: Bietet Sicherheit auf Transportebene und SOAP-Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="bc938-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="bc938-128">Auf beiden Ebenen sind die gleichen Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bc938-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="bc938-129">Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="bc938-129">The default value is Transport.</span></span> <span data-ttu-id="bc938-130">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="bc938-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc938-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc938-131">Child Elements</span></span>  
  
|<span data-ttu-id="bc938-132">Element</span><span class="sxs-lookup"><span data-stu-id="bc938-132">Element</span></span>|<span data-ttu-id="bc938-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc938-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc938-134">\<message></span><span class="sxs-lookup"><span data-stu-id="bc938-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="bc938-135">Definiert die SOAP-Nachrichtensicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="bc938-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="bc938-136">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="bc938-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="bc938-137">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="bc938-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="bc938-138">Definiert die Sicherheitseinstellungen für den MSMQ-Transport.</span><span class="sxs-lookup"><span data-stu-id="bc938-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="bc938-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="bc938-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc938-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc938-140">Parent Elements</span></span>  
  
|<span data-ttu-id="bc938-141">Element</span><span class="sxs-lookup"><span data-stu-id="bc938-141">Element</span></span>|<span data-ttu-id="bc938-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc938-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc938-143">Bindung</span><span class="sxs-lookup"><span data-stu-id="bc938-143">binding</span></span>|<span data-ttu-id="bc938-144">Das Bindungselement, das von der [ \<NetMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="bc938-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc938-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc938-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [<span data-ttu-id="bc938-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="bc938-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="bc938-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="bc938-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bc938-148">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="bc938-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="bc938-149">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="bc938-149">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="bc938-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="bc938-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="bc938-151">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="bc938-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
