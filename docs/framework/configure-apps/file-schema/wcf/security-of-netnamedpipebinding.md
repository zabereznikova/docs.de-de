---
title: <security> von <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736436"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="608e7-102">\<Sicherheits > von \<NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="608e7-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="608e7-103">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="608e7-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="608e7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="608e7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="608e7-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="608e7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="608e7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="608e7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="608e7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NetNamedPipeBinding**](netnamedpipebinding.md) ></span><span class="sxs-lookup"><span data-stu-id="608e7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="608e7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="608e7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="608e7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheit >**</span><span class="sxs-lookup"><span data-stu-id="608e7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="608e7-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="608e7-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="608e7-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="608e7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="608e7-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="608e7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="608e7-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="608e7-113">Attributes</span></span>  
  
|<span data-ttu-id="608e7-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="608e7-114">Attribute</span></span>|<span data-ttu-id="608e7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="608e7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="608e7-116">Modus</span><span class="sxs-lookup"><span data-stu-id="608e7-116">mode</span></span>|<span data-ttu-id="608e7-117">Gibt den Sicherheitstyp an, der auf diese Bindung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="608e7-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="608e7-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="608e7-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="608e7-119">-None: Dadurch wird die Sicherheit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="608e7-119">-   None: This disables security.</span></span><br /><span data-ttu-id="608e7-120">-Transport: die Sicherheit wird mithilfe der zugrunde liegenden Transport basierten Sicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="608e7-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="608e7-121">Es ist möglich, den Schutzgrad mit diesem Modus zu steuern.</span><span class="sxs-lookup"><span data-stu-id="608e7-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="608e7-122">-Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="608e7-122">-   The default value is Transport.</span></span> <span data-ttu-id="608e7-123">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="608e7-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="608e7-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="608e7-124">Child Elements</span></span>  
  
|<span data-ttu-id="608e7-125">Element</span><span class="sxs-lookup"><span data-stu-id="608e7-125">Element</span></span>|<span data-ttu-id="608e7-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="608e7-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="608e7-127">transport</span><span class="sxs-lookup"><span data-stu-id="608e7-127">transport</span></span>|<span data-ttu-id="608e7-128">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="608e7-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="608e7-129">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="608e7-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="608e7-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="608e7-130">Parent Elements</span></span>  
  
|<span data-ttu-id="608e7-131">Element</span><span class="sxs-lookup"><span data-stu-id="608e7-131">Element</span></span>|<span data-ttu-id="608e7-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="608e7-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="608e7-133">Bindung</span><span class="sxs-lookup"><span data-stu-id="608e7-133">binding</span></span>|<span data-ttu-id="608e7-134">Das Bindungs Element der [\<NetNamedPipeBinding->](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="608e7-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="608e7-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="608e7-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="608e7-136">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="608e7-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="608e7-137">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="608e7-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="608e7-138">Bindungen</span><span class="sxs-lookup"><span data-stu-id="608e7-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="608e7-139">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="608e7-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="608e7-140">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="608e7-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="608e7-141">\<binding ></span><span class="sxs-lookup"><span data-stu-id="608e7-141">\<binding></span></span>](bindings.md)
