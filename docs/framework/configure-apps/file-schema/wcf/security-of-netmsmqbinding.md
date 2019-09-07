---
title: <security> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: c780b157d0d566e24c6826c253401a51fbfab69d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399843"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="395de-102">\<security> of \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="395de-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="395de-103">Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung.</span><span class="sxs-lookup"><span data-stu-id="395de-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="395de-104">Dadurch wird angegeben, ob die Transportsicherheit oder die SOAP-Sicherheit aktiviert sind und ggf. welcher Authentifizierungsmodus und welche Schutzebenen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="395de-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="395de-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="395de-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="395de-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="395de-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="395de-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="395de-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="395de-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NetMsmqBinding->** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="395de-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="395de-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="395de-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="395de-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**</span><span class="sxs-lookup"><span data-stu-id="395de-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="395de-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="395de-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="395de-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="395de-112">Attributes and Elements</span></span>  
 <span data-ttu-id="395de-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="395de-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="395de-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="395de-114">Attributes</span></span>  
  
|<span data-ttu-id="395de-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="395de-115">Attribute</span></span>|<span data-ttu-id="395de-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="395de-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="395de-117">Modus</span><span class="sxs-lookup"><span data-stu-id="395de-117">mode</span></span>|<span data-ttu-id="395de-118">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung steuert.</span><span class="sxs-lookup"><span data-stu-id="395de-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="395de-119">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="395de-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="395de-120">Gar Dadurch wird die Sicherheit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="395de-120">-   None: This disables security.</span></span><br /><span data-ttu-id="395de-121">Personen Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="395de-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="395de-122">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="395de-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="395de-123">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="395de-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="395de-124">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="395de-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="395de-125">Vermitteln Gibt die End-End-Anwendungssicherheit an.</span><span class="sxs-lookup"><span data-stu-id="395de-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="395de-126">Es wird keine Sicherheit auf Transportebene bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="395de-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="395de-127">Dies ähnelt der Sicherheit, die von anderen Standardbindungen angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="395de-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="395de-128">Zwar Bietet Sicherheit auf Transport-und SOAP-Messaging Ebene.</span><span class="sxs-lookup"><span data-stu-id="395de-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="395de-129">Auf beiden Ebenen sind die gleichen Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="395de-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="395de-130">Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="395de-130">The default value is Transport.</span></span> <span data-ttu-id="395de-131">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="395de-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="395de-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="395de-132">Child Elements</span></span>  
  
|<span data-ttu-id="395de-133">Element</span><span class="sxs-lookup"><span data-stu-id="395de-133">Element</span></span>|<span data-ttu-id="395de-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="395de-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="395de-135">\<message></span><span class="sxs-lookup"><span data-stu-id="395de-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="395de-136">Definiert die SOAP-Nachrichtensicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="395de-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="395de-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="395de-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="395de-138">\<transport></span><span class="sxs-lookup"><span data-stu-id="395de-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="395de-139">Definiert die Sicherheitseinstellungen für den MSMQ-Transport.</span><span class="sxs-lookup"><span data-stu-id="395de-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="395de-140">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="395de-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="395de-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="395de-141">Parent Elements</span></span>  
  
|<span data-ttu-id="395de-142">Element</span><span class="sxs-lookup"><span data-stu-id="395de-142">Element</span></span>|<span data-ttu-id="395de-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="395de-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="395de-144">Bindung</span><span class="sxs-lookup"><span data-stu-id="395de-144">binding</span></span>|<span data-ttu-id="395de-145">Das Bindungs Element der [ \<NetMsmqBinding->](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="395de-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="395de-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="395de-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="395de-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="395de-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="395de-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="395de-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="395de-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="395de-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="395de-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="395de-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="395de-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="395de-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="395de-152">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="395de-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
