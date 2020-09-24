---
title: <security> von <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 1a231a60d29cc6a4460de69a98753c23c0386027
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170037"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="37fe5-102">\<security> von \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="37fe5-102">\<security> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="37fe5-103">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="37fe5-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="37fe5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37fe5-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37fe5-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="37fe5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="37fe5-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="37fe5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37fe5-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="37fe5-107">Attributes</span></span>  
  
|<span data-ttu-id="37fe5-108">attribute</span><span class="sxs-lookup"><span data-stu-id="37fe5-108">Attribute</span></span>|<span data-ttu-id="37fe5-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37fe5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37fe5-110">Modus</span><span class="sxs-lookup"><span data-stu-id="37fe5-110">mode</span></span>|<span data-ttu-id="37fe5-111">Gibt den Sicherheitstyp an, der auf diese Bindung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="37fe5-111">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="37fe5-112">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="37fe5-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="37fe5-113">-None: Dadurch wird die Sicherheit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="37fe5-113">-   None: This disables security.</span></span><br /><span data-ttu-id="37fe5-114">-Transport: die Sicherheit wird mithilfe der zugrunde liegenden Transport basierten Sicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="37fe5-114">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="37fe5-115">In diesem Modus kann die Schutzstufe gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="37fe5-115">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="37fe5-116">-Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="37fe5-116">-   The default value is Transport.</span></span> <span data-ttu-id="37fe5-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="37fe5-117">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37fe5-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="37fe5-118">Child Elements</span></span>  
  
|<span data-ttu-id="37fe5-119">Element</span><span class="sxs-lookup"><span data-stu-id="37fe5-119">Element</span></span>|<span data-ttu-id="37fe5-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37fe5-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37fe5-121">Transport</span><span class="sxs-lookup"><span data-stu-id="37fe5-121">transport</span></span>|<span data-ttu-id="37fe5-122">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="37fe5-122">Defines the security settings for the transport.</span></span> <span data-ttu-id="37fe5-123">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="37fe5-123">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37fe5-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="37fe5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="37fe5-125">Element</span><span class="sxs-lookup"><span data-stu-id="37fe5-125">Element</span></span>|<span data-ttu-id="37fe5-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37fe5-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37fe5-127">binding</span><span class="sxs-lookup"><span data-stu-id="37fe5-127">binding</span></span>|<span data-ttu-id="37fe5-128">Das Bindungs Element von [\<netNamedPipeBinding>](netnamedpipebinding.md) .</span><span class="sxs-lookup"><span data-stu-id="37fe5-128">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37fe5-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37fe5-129">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="37fe5-130">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="37fe5-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="37fe5-131">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="37fe5-131">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="37fe5-132">Bindungen</span><span class="sxs-lookup"><span data-stu-id="37fe5-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="37fe5-133">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="37fe5-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="37fe5-134">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="37fe5-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
