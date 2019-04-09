---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 108c349a44ed3ac902652f86241c1e96a622549b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204236"
---
# <a name="behaviors"></a><span data-ttu-id="3ea86-101">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3ea86-101">\<behaviors></span></span>
<span data-ttu-id="3ea86-102">Dieses Element definiert zwei untergeordnete Auflistungen mit dem Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="3ea86-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="3ea86-103">Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="3ea86-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="3ea86-104">Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3ea86-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="3ea86-105">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3ea86-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3ea86-106">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ea86-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="3ea86-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3ea86-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ea86-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ea86-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ea86-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3ea86-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3ea86-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ea86-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ea86-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="3ea86-111">Attributes</span></span>  
 <span data-ttu-id="3ea86-112">Keiner</span><span class="sxs-lookup"><span data-stu-id="3ea86-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3ea86-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ea86-113">Child Elements</span></span>  
  
|<span data-ttu-id="3ea86-114">Element</span><span class="sxs-lookup"><span data-stu-id="3ea86-114">Element</span></span>|<span data-ttu-id="3ea86-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ea86-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ea86-116">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="3ea86-116">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="3ea86-117">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Endpunkt definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="3ea86-117">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="3ea86-118">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3ea86-118">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="3ea86-119">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Dienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="3ea86-119">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ea86-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ea86-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3ea86-121">Element</span><span class="sxs-lookup"><span data-stu-id="3ea86-121">Element</span></span>|<span data-ttu-id="3ea86-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ea86-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ea86-123">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3ea86-123">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="3ea86-124">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="3ea86-124">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ea86-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ea86-125">Remarks</span></span>  
 <span data-ttu-id="3ea86-126">Sie können das `<remove>`-Element verwenden, um ein bestimmtes Verhalten aus der Auflistung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="3ea86-126">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="3ea86-127">Geben Sie hierzu im `name`-Attribut des `<remove>`-Elements den Namen des zu entfernenden Verhaltens an.</span><span class="sxs-lookup"><span data-stu-id="3ea86-127">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="3ea86-128">Sie können auch das `<clear>`-Element verwenden, um sicherzustellen, dass eine Verhaltensauflistung zu Beginn leer ist, indem Sie den gesamten Inhalt der Auflistung entfernen.</span><span class="sxs-lookup"><span data-stu-id="3ea86-128">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea86-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ea86-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="3ea86-130">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="3ea86-130">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="3ea86-131">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="3ea86-131">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="3ea86-132">Angeben des Clientlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="3ea86-132">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="3ea86-133">Angeben des Dienstlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="3ea86-133">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="3ea86-134">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="3ea86-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
