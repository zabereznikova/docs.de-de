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
ms.openlocfilehash: efb6289c63cdc98402336949ef5916e7568775a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="095ff-102">&lt;security&gt; von &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="095ff-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="095ff-103">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="095ff-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="095ff-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="095ff-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="095ff-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="095ff-105">\<bindings></span></span>  
<span data-ttu-id="095ff-106">\<NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="095ff-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="095ff-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="095ff-107">\<binding></span></span>  
<span data-ttu-id="095ff-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="095ff-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="095ff-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="095ff-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="095ff-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="095ff-110">Attributes and Elements</span></span>  
 <span data-ttu-id="095ff-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="095ff-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="095ff-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="095ff-112">Attributes</span></span>  
  
|<span data-ttu-id="095ff-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="095ff-113">Attribute</span></span>|<span data-ttu-id="095ff-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="095ff-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="095ff-115">Modus</span><span class="sxs-lookup"><span data-stu-id="095ff-115">mode</span></span>|<span data-ttu-id="095ff-116">Gibt den Sicherheitstyp an, der auf diese Bindung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="095ff-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="095ff-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="095ff-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="095ff-118">-"None": Die Sicherheit wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="095ff-118">-   None: This disables security.</span></span><br /><span data-ttu-id="095ff-119">-Transport: Sicherheit wird über die zugrunde liegende transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="095ff-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="095ff-120">Es ist möglich, den Schutzgrad mit diesem Modus zu steuern.</span><span class="sxs-lookup"><span data-stu-id="095ff-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="095ff-121">– Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="095ff-121">-   The default value is Transport.</span></span> <span data-ttu-id="095ff-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="095ff-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="095ff-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="095ff-123">Child Elements</span></span>  
  
|<span data-ttu-id="095ff-124">Element</span><span class="sxs-lookup"><span data-stu-id="095ff-124">Element</span></span>|<span data-ttu-id="095ff-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="095ff-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="095ff-126">transport</span><span class="sxs-lookup"><span data-stu-id="095ff-126">transport</span></span>|<span data-ttu-id="095ff-127">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="095ff-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="095ff-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="095ff-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="095ff-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="095ff-129">Parent Elements</span></span>  
  
|<span data-ttu-id="095ff-130">Element</span><span class="sxs-lookup"><span data-stu-id="095ff-130">Element</span></span>|<span data-ttu-id="095ff-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="095ff-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="095ff-132">Bindung</span><span class="sxs-lookup"><span data-stu-id="095ff-132">binding</span></span>|<span data-ttu-id="095ff-133">Das Bindungselement, das von der [ \<NetNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="095ff-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="095ff-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="095ff-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="095ff-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="095ff-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="095ff-136">Auswählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="095ff-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="095ff-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="095ff-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="095ff-138">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="095ff-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="095ff-139">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="095ff-139">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="095ff-140">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="095ff-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
