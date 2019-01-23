---
title: '&lt;security&gt; von &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: db263148a5a0993b546ffdd565ae7cf2edef580c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493780"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="36f11-102">&lt;security&gt; von &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="36f11-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="36f11-103">Definiert die Transportsicherheitseinstellungen für den Message Queuing (MSMQ)-Integrationskanal.</span><span class="sxs-lookup"><span data-stu-id="36f11-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="36f11-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="36f11-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="36f11-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="36f11-105">\<bindings></span></span>  
<span data-ttu-id="36f11-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="36f11-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="36f11-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="36f11-107">\<binding></span></span>  
<span data-ttu-id="36f11-108">\<security></span><span class="sxs-lookup"><span data-stu-id="36f11-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36f11-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="36f11-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36f11-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="36f11-110">Attributes and Elements</span></span>  
 <span data-ttu-id="36f11-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="36f11-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36f11-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="36f11-112">Attributes</span></span>  
  
|<span data-ttu-id="36f11-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="36f11-113">Attribute</span></span>|<span data-ttu-id="36f11-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36f11-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36f11-115">Modus</span><span class="sxs-lookup"><span data-stu-id="36f11-115">mode</span></span>|<span data-ttu-id="36f11-116">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung mit dem Message Queuing-Integrationskanal steuert.</span><span class="sxs-lookup"><span data-stu-id="36f11-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="36f11-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="36f11-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="36f11-118">– None: Dadurch werden die Sicherheitsfunktionen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="36f11-118">-   None: This disables security.</span></span><br /><span data-ttu-id="36f11-119">-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="36f11-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="36f11-120">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="36f11-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="36f11-121">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="36f11-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="36f11-122">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="36f11-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="36f11-123">Der Standardwert ist `Transport`.</span><span class="sxs-lookup"><span data-stu-id="36f11-123">The default value is `Transport`.</span></span> <span data-ttu-id="36f11-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="36f11-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36f11-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="36f11-125">Child Elements</span></span>  
  
|<span data-ttu-id="36f11-126">Element</span><span class="sxs-lookup"><span data-stu-id="36f11-126">Element</span></span>|<span data-ttu-id="36f11-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36f11-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36f11-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="36f11-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="36f11-129">Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.</span><span class="sxs-lookup"><span data-stu-id="36f11-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="36f11-130">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="36f11-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36f11-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="36f11-131">Parent Elements</span></span>  
  
|<span data-ttu-id="36f11-132">Element</span><span class="sxs-lookup"><span data-stu-id="36f11-132">Element</span></span>|<span data-ttu-id="36f11-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36f11-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36f11-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="36f11-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="36f11-135">Das Bindungselement, das von der [ \<MsmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="36f11-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36f11-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36f11-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="36f11-137">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="36f11-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="36f11-138">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="36f11-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="36f11-139">Bindungen</span><span class="sxs-lookup"><span data-stu-id="36f11-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="36f11-140">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="36f11-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="36f11-141">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="36f11-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="36f11-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="36f11-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="36f11-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="36f11-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
