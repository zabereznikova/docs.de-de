---
title: '&lt;security&gt; von &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
author: BrucePerlerMS
ms.openlocfilehash: 98671f9fe73f60325025f88b94717e8a06afc55c
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845516"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="31aef-102">&lt;security&gt; von &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="31aef-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="31aef-103">Definiert die Transportsicherheitseinstellungen für den Message Queuing (MSMQ)-Integrationskanal.</span><span class="sxs-lookup"><span data-stu-id="31aef-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="31aef-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="31aef-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="31aef-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="31aef-105">\<bindings></span></span>  
<span data-ttu-id="31aef-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="31aef-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="31aef-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="31aef-107">\<binding></span></span>  
<span data-ttu-id="31aef-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="31aef-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31aef-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="31aef-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31aef-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="31aef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="31aef-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31aef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31aef-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="31aef-112">Attributes</span></span>  
  
|<span data-ttu-id="31aef-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="31aef-113">Attribute</span></span>|<span data-ttu-id="31aef-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31aef-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31aef-115">Modus</span><span class="sxs-lookup"><span data-stu-id="31aef-115">mode</span></span>|<span data-ttu-id="31aef-116">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung mit dem Message Queuing-Integrationskanal steuert.</span><span class="sxs-lookup"><span data-stu-id="31aef-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="31aef-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="31aef-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="31aef-118">– None: Die Sicherheit wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="31aef-118">-   None: This disables security.</span></span><br /><span data-ttu-id="31aef-119">-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="31aef-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="31aef-120">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="31aef-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="31aef-121">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="31aef-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="31aef-122">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="31aef-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="31aef-123">Der Standardwert ist `Transport`.</span><span class="sxs-lookup"><span data-stu-id="31aef-123">The default value is `Transport`.</span></span> <span data-ttu-id="31aef-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="31aef-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31aef-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31aef-125">Child Elements</span></span>  
  
|<span data-ttu-id="31aef-126">Element</span><span class="sxs-lookup"><span data-stu-id="31aef-126">Element</span></span>|<span data-ttu-id="31aef-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31aef-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31aef-128">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="31aef-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="31aef-129">Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.</span><span class="sxs-lookup"><span data-stu-id="31aef-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="31aef-130">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="31aef-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31aef-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31aef-131">Parent Elements</span></span>  
  
|<span data-ttu-id="31aef-132">Element</span><span class="sxs-lookup"><span data-stu-id="31aef-132">Element</span></span>|<span data-ttu-id="31aef-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31aef-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31aef-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="31aef-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="31aef-135">Das Bindungselement, das von der [ \<MsmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="31aef-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31aef-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31aef-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="31aef-137">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="31aef-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="31aef-138">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="31aef-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="31aef-139">Bindungen</span><span class="sxs-lookup"><span data-stu-id="31aef-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="31aef-140">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="31aef-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="31aef-141">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="31aef-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="31aef-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="31aef-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="31aef-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="31aef-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
