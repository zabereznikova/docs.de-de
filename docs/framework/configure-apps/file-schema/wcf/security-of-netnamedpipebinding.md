---
title: <security> von <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: fa31dda3274c9768694bdf5232f31554899e1d82
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203391"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="5c69c-102">\<security> of \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="5c69c-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="5c69c-103">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="5c69c-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="5c69c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5c69c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c69c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5c69c-105">\<bindings></span></span>  
<span data-ttu-id="5c69c-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="5c69c-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="5c69c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5c69c-107">\<binding></span></span>  
<span data-ttu-id="5c69c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="5c69c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c69c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c69c-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c69c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5c69c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5c69c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5c69c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c69c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5c69c-112">Attributes</span></span>  
  
|<span data-ttu-id="5c69c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="5c69c-113">Attribute</span></span>|<span data-ttu-id="5c69c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c69c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c69c-115">Modus</span><span class="sxs-lookup"><span data-stu-id="5c69c-115">mode</span></span>|<span data-ttu-id="5c69c-116">Gibt den Sicherheitstyp an, der auf diese Bindung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c69c-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="5c69c-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="5c69c-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5c69c-118">– None: Dadurch werden die Sicherheitsfunktionen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5c69c-118">-   None: This disables security.</span></span><br /><span data-ttu-id="5c69c-119">-Transport: Sicherheit wird bereitgestellt, mit der zugrunde liegende transportsicherheit gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="5c69c-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="5c69c-120">Es ist möglich, den Schutzgrad mit diesem Modus zu steuern.</span><span class="sxs-lookup"><span data-stu-id="5c69c-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="5c69c-121">– Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="5c69c-121">-   The default value is Transport.</span></span> <span data-ttu-id="5c69c-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5c69c-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c69c-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c69c-123">Child Elements</span></span>  
  
|<span data-ttu-id="5c69c-124">Element</span><span class="sxs-lookup"><span data-stu-id="5c69c-124">Element</span></span>|<span data-ttu-id="5c69c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c69c-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c69c-126">transport</span><span class="sxs-lookup"><span data-stu-id="5c69c-126">transport</span></span>|<span data-ttu-id="5c69c-127">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="5c69c-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="5c69c-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="5c69c-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c69c-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c69c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="5c69c-130">Element</span><span class="sxs-lookup"><span data-stu-id="5c69c-130">Element</span></span>|<span data-ttu-id="5c69c-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c69c-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c69c-132">Bindung</span><span class="sxs-lookup"><span data-stu-id="5c69c-132">binding</span></span>|<span data-ttu-id="5c69c-133">Das Bindungselement, das von der [ \<NetNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="5c69c-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c69c-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c69c-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="5c69c-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5c69c-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5c69c-136">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="5c69c-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="5c69c-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5c69c-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5c69c-138">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5c69c-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5c69c-139">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5c69c-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5c69c-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="5c69c-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
