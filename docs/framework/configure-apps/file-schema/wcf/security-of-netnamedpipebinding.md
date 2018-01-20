---
title: '&lt;security&gt; von &lt;netNamedPipeBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3a018c502aead84eb6936001acb5bc24c59188f8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="fcec1-102">&lt;security&gt; von &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="fcec1-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="fcec1-103">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="fcec1-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="fcec1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fcec1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fcec1-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fcec1-105">\<bindings></span></span>  
<span data-ttu-id="fcec1-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="fcec1-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="fcec1-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="fcec1-107">\<binding></span></span>  
<span data-ttu-id="fcec1-108">\<security></span><span class="sxs-lookup"><span data-stu-id="fcec1-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcec1-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcec1-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcec1-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fcec1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fcec1-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fcec1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcec1-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="fcec1-112">Attributes</span></span>  
  
|<span data-ttu-id="fcec1-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="fcec1-113">Attribute</span></span>|<span data-ttu-id="fcec1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcec1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcec1-115">Modus</span><span class="sxs-lookup"><span data-stu-id="fcec1-115">mode</span></span>|<span data-ttu-id="fcec1-116">Gibt den Sicherheitstyp an, der auf diese Bindung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcec1-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="fcec1-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="fcec1-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fcec1-118">-"None": Die Sicherheit wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fcec1-118">-   None: This disables security.</span></span><br /><span data-ttu-id="fcec1-119">-Transport: Sicherheit wird über die zugrunde liegende transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fcec1-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="fcec1-120">Es ist möglich, den Schutzgrad mit diesem Modus zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fcec1-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="fcec1-121">– Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="fcec1-121">-   The default value is Transport.</span></span> <span data-ttu-id="fcec1-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="fcec1-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcec1-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcec1-123">Child Elements</span></span>  
  
|<span data-ttu-id="fcec1-124">Element</span><span class="sxs-lookup"><span data-stu-id="fcec1-124">Element</span></span>|<span data-ttu-id="fcec1-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcec1-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fcec1-126">transport</span><span class="sxs-lookup"><span data-stu-id="fcec1-126">transport</span></span>|<span data-ttu-id="fcec1-127">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="fcec1-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="fcec1-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="fcec1-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcec1-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcec1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="fcec1-130">Element</span><span class="sxs-lookup"><span data-stu-id="fcec1-130">Element</span></span>|<span data-ttu-id="fcec1-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcec1-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fcec1-132">Bindung</span><span class="sxs-lookup"><span data-stu-id="fcec1-132">binding</span></span>|<span data-ttu-id="fcec1-133">Das Bindungselement, das von der [ \<NetNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="fcec1-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fcec1-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcec1-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="fcec1-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="fcec1-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fcec1-136">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="fcec1-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="fcec1-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fcec1-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fcec1-138">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="fcec1-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fcec1-139">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="fcec1-139">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fcec1-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="fcec1-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
