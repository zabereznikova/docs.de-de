---
title: '&lt;Verhalten&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: ca9cf5daa6590c14d4b5fd15c502d67af1f93b52
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="c1643-102">&lt;Verhalten&gt;</span><span class="sxs-lookup"><span data-stu-id="c1643-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="c1643-103">Dieses Element definiert zwei untergeordnete Auflistungen mit dem Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="c1643-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="c1643-104">Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="c1643-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="c1643-105">Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c1643-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="c1643-106">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c1643-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c1643-107">Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1643-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="c1643-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1643-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1643-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1643-109">Syntax</span></span>  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1643-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1643-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1643-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1643-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1643-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1643-112">Attributes</span></span>  
 <span data-ttu-id="c1643-113">Keiner</span><span class="sxs-lookup"><span data-stu-id="c1643-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1643-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1643-114">Child Elements</span></span>  
  
|<span data-ttu-id="c1643-115">Element</span><span class="sxs-lookup"><span data-stu-id="c1643-115">Element</span></span>|<span data-ttu-id="c1643-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1643-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1643-117">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c1643-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="c1643-118">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Endpunkt definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="c1643-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="c1643-119">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c1643-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="c1643-120">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Dienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="c1643-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1643-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1643-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c1643-122">Element</span><span class="sxs-lookup"><span data-stu-id="c1643-122">Element</span></span>|<span data-ttu-id="c1643-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1643-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1643-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c1643-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="c1643-125">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="c1643-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1643-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1643-126">Remarks</span></span>  
 <span data-ttu-id="c1643-127">Sie können das `<remove>`-Element verwenden, um ein bestimmtes Verhalten aus der Auflistung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c1643-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="c1643-128">Geben Sie hierzu im `name`-Attribut des `<remove>`-Elements den Namen des zu entfernenden Verhaltens an.</span><span class="sxs-lookup"><span data-stu-id="c1643-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="c1643-129">Sie können auch das `<clear>`-Element verwenden, um sicherzustellen, dass eine Verhaltensauflistung zu Beginn leer ist, indem Sie den gesamten Inhalt der Auflistung entfernen.</span><span class="sxs-lookup"><span data-stu-id="c1643-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1643-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1643-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="c1643-131">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="c1643-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [<span data-ttu-id="c1643-132">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="c1643-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="c1643-133">Angeben des Clientlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="c1643-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="c1643-134">Angeben des Dienstlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="c1643-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [<span data-ttu-id="c1643-135">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="c1643-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
