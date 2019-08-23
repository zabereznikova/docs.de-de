---
title: <security> von <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 0996a98438dc344d96d640abced52ac99709adbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936676"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="901a7-102">\<Sicherheits > von \<NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="901a7-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="901a7-103">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="901a7-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="901a7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="901a7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="901a7-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="901a7-105">\<bindings></span></span>  
<span data-ttu-id="901a7-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="901a7-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="901a7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="901a7-107">\<binding></span></span>  
<span data-ttu-id="901a7-108">\<security></span><span class="sxs-lookup"><span data-stu-id="901a7-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="901a7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="901a7-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="901a7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="901a7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="901a7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="901a7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="901a7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="901a7-112">Attributes</span></span>  
  
|<span data-ttu-id="901a7-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="901a7-113">Attribute</span></span>|<span data-ttu-id="901a7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="901a7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="901a7-115">Modus</span><span class="sxs-lookup"><span data-stu-id="901a7-115">mode</span></span>|<span data-ttu-id="901a7-116">Gibt den Sicherheitstyp an, der auf diese Bindung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="901a7-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="901a7-117">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="901a7-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="901a7-118">Gar Dadurch wird die Sicherheit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="901a7-118">-   None: This disables security.</span></span><br /><span data-ttu-id="901a7-119">Personen Sicherheit wird mithilfe der zugrunde liegenden Transport basierten Sicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="901a7-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="901a7-120">Es ist möglich, den Schutzgrad mit diesem Modus zu steuern.</span><span class="sxs-lookup"><span data-stu-id="901a7-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="901a7-121">-Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="901a7-121">-   The default value is Transport.</span></span> <span data-ttu-id="901a7-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="901a7-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="901a7-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="901a7-123">Child Elements</span></span>  
  
|<span data-ttu-id="901a7-124">Element</span><span class="sxs-lookup"><span data-stu-id="901a7-124">Element</span></span>|<span data-ttu-id="901a7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="901a7-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="901a7-126">transport</span><span class="sxs-lookup"><span data-stu-id="901a7-126">transport</span></span>|<span data-ttu-id="901a7-127">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="901a7-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="901a7-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="901a7-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="901a7-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="901a7-129">Parent Elements</span></span>  
  
|<span data-ttu-id="901a7-130">Element</span><span class="sxs-lookup"><span data-stu-id="901a7-130">Element</span></span>|<span data-ttu-id="901a7-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="901a7-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="901a7-132">Bindung</span><span class="sxs-lookup"><span data-stu-id="901a7-132">binding</span></span>|<span data-ttu-id="901a7-133">Das Bindungs Element des [ \<NetNamedPipeBinding->](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="901a7-133">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="901a7-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="901a7-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="901a7-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="901a7-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="901a7-136">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="901a7-136">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="901a7-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="901a7-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="901a7-138">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="901a7-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="901a7-139">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="901a7-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="901a7-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="901a7-140">\<binding></span></span>](../../../misc/binding.md)
