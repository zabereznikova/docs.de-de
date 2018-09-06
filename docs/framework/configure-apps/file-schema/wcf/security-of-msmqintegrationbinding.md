---
title: '&lt;security&gt; von &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6419c2157281d00cf79de16d4f494fc52bcee598
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43876731"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="2c527-102">&lt;security&gt; von &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="2c527-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="2c527-103">Definiert die Transportsicherheitseinstellungen für den Message Queuing (MSMQ)-Integrationskanal.</span><span class="sxs-lookup"><span data-stu-id="2c527-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="2c527-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2c527-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2c527-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2c527-105">\<bindings></span></span>  
<span data-ttu-id="2c527-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="2c527-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="2c527-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="2c527-107">\<binding></span></span>  
<span data-ttu-id="2c527-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="2c527-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c527-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c527-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c527-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2c527-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2c527-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c527-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c527-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2c527-112">Attributes</span></span>  
  
|<span data-ttu-id="2c527-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2c527-113">Attribute</span></span>|<span data-ttu-id="2c527-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c527-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c527-115">Modus</span><span class="sxs-lookup"><span data-stu-id="2c527-115">mode</span></span>|<span data-ttu-id="2c527-116">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung mit dem Message Queuing-Integrationskanal steuert.</span><span class="sxs-lookup"><span data-stu-id="2c527-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="2c527-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="2c527-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2c527-118">– None: Die Sicherheit wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2c527-118">-   None: This disables security.</span></span><br /><span data-ttu-id="2c527-119">-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2c527-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="2c527-120">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="2c527-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="2c527-121">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="2c527-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="2c527-122">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="2c527-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="2c527-123">Der Standardwert ist `Transport`.</span><span class="sxs-lookup"><span data-stu-id="2c527-123">The default value is `Transport`.</span></span> <span data-ttu-id="2c527-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2c527-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c527-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c527-125">Child Elements</span></span>  
  
|<span data-ttu-id="2c527-126">Element</span><span class="sxs-lookup"><span data-stu-id="2c527-126">Element</span></span>|<span data-ttu-id="2c527-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c527-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c527-128">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="2c527-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="2c527-129">Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.</span><span class="sxs-lookup"><span data-stu-id="2c527-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="2c527-130">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2c527-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c527-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c527-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2c527-132">Element</span><span class="sxs-lookup"><span data-stu-id="2c527-132">Element</span></span>|<span data-ttu-id="2c527-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c527-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c527-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="2c527-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="2c527-135">Das Bindungselement, das von der [ \<MsmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2c527-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c527-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c527-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="2c527-137">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="2c527-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="2c527-138">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2c527-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="2c527-139">Bindungen</span><span class="sxs-lookup"><span data-stu-id="2c527-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2c527-140">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="2c527-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="2c527-141">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2c527-141">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="2c527-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="2c527-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="2c527-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="2c527-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
