---
title: '&lt;security&gt; von &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6419c2157281d00cf79de16d4f494fc52bcee598
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45617687"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="5743b-102">&lt;security&gt; von &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5743b-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="5743b-103">Definiert die Transportsicherheitseinstellungen für den Message Queuing (MSMQ)-Integrationskanal.</span><span class="sxs-lookup"><span data-stu-id="5743b-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="5743b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5743b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5743b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5743b-105">\<bindings></span></span>  
<span data-ttu-id="5743b-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="5743b-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="5743b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5743b-107">\<binding></span></span>  
<span data-ttu-id="5743b-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="5743b-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5743b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="5743b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5743b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5743b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5743b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5743b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5743b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5743b-112">Attributes</span></span>  
  
|<span data-ttu-id="5743b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="5743b-113">Attribute</span></span>|<span data-ttu-id="5743b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5743b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5743b-115">Modus</span><span class="sxs-lookup"><span data-stu-id="5743b-115">mode</span></span>|<span data-ttu-id="5743b-116">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung mit dem Message Queuing-Integrationskanal steuert.</span><span class="sxs-lookup"><span data-stu-id="5743b-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="5743b-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="5743b-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5743b-118">– None: Die Sicherheit wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5743b-118">-   None: This disables security.</span></span><br /><span data-ttu-id="5743b-119">-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5743b-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="5743b-120">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="5743b-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="5743b-121">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="5743b-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="5743b-122">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="5743b-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="5743b-123">Der Standardwert ist `Transport`.</span><span class="sxs-lookup"><span data-stu-id="5743b-123">The default value is `Transport`.</span></span> <span data-ttu-id="5743b-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5743b-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5743b-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5743b-125">Child Elements</span></span>  
  
|<span data-ttu-id="5743b-126">Element</span><span class="sxs-lookup"><span data-stu-id="5743b-126">Element</span></span>|<span data-ttu-id="5743b-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5743b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5743b-128">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="5743b-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="5743b-129">Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.</span><span class="sxs-lookup"><span data-stu-id="5743b-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="5743b-130">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="5743b-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5743b-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5743b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="5743b-132">Element</span><span class="sxs-lookup"><span data-stu-id="5743b-132">Element</span></span>|<span data-ttu-id="5743b-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5743b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5743b-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="5743b-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5743b-135">Das Bindungselement, das von der [ \<MsmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5743b-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5743b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5743b-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="5743b-137">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="5743b-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="5743b-138">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5743b-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="5743b-139">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5743b-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5743b-140">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5743b-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5743b-141">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5743b-141">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5743b-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="5743b-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="5743b-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="5743b-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
