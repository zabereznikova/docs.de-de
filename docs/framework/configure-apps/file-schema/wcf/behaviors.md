---
title: '&lt;behaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: a6786efb289ee66da3f0635e1a86e23f9b7302d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528432"
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="7f81e-102">&lt;behaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="7f81e-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="7f81e-103">Dieses Element definiert zwei untergeordnete Auflistungen mit dem Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="7f81e-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="7f81e-104">Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="7f81e-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="7f81e-105">Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7f81e-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="7f81e-106">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7f81e-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7f81e-107">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7f81e-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="7f81e-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7f81e-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f81e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f81e-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f81e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7f81e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f81e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f81e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f81e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7f81e-112">Attributes</span></span>  
 <span data-ttu-id="7f81e-113">Keine</span><span class="sxs-lookup"><span data-stu-id="7f81e-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f81e-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f81e-114">Child Elements</span></span>  
  
|<span data-ttu-id="7f81e-115">Element</span><span class="sxs-lookup"><span data-stu-id="7f81e-115">Element</span></span>|<span data-ttu-id="7f81e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f81e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f81e-117">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="7f81e-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="7f81e-118">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Endpunkt definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="7f81e-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="7f81e-119">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7f81e-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="7f81e-120">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Dienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="7f81e-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f81e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f81e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7f81e-122">Element</span><span class="sxs-lookup"><span data-stu-id="7f81e-122">Element</span></span>|<span data-ttu-id="7f81e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f81e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f81e-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7f81e-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="7f81e-125">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="7f81e-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f81e-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7f81e-126">Remarks</span></span>  
 <span data-ttu-id="7f81e-127">Sie können das `<remove>`-Element verwenden, um ein bestimmtes Verhalten aus der Auflistung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7f81e-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="7f81e-128">Geben Sie hierzu im `name`-Attribut des `<remove>`-Elements den Namen des zu entfernenden Verhaltens an.</span><span class="sxs-lookup"><span data-stu-id="7f81e-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="7f81e-129">Sie können auch das `<clear>`-Element verwenden, um sicherzustellen, dass eine Verhaltensauflistung zu Beginn leer ist, indem Sie den gesamten Inhalt der Auflistung entfernen.</span><span class="sxs-lookup"><span data-stu-id="7f81e-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f81e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f81e-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="7f81e-131">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="7f81e-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="7f81e-132">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="7f81e-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="7f81e-133">Angeben des Clientlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="7f81e-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="7f81e-134">Angeben des Dienstlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="7f81e-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="7f81e-135">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="7f81e-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
