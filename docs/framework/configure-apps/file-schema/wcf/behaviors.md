---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139689"
---
# <a name="behaviors"></a><span data-ttu-id="93a8e-101">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="93a8e-101">\<behaviors></span></span>
<span data-ttu-id="93a8e-102">Dieses Element definiert zwei untergeordnete Auflistungen mit dem Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="93a8e-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="93a8e-103">Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="93a8e-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="93a8e-104">Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="93a8e-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="93a8e-105">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="93a8e-105">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="93a8e-106">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="93a8e-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
<span data-ttu-id="93a8e-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="93a8e-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="93a8e-108">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="93a8e-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="93a8e-109">&nbsp;&nbsp;&nbsp;&nbsp; **\<Verhalten >**</span><span class="sxs-lookup"><span data-stu-id="93a8e-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93a8e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="93a8e-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93a8e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="93a8e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="93a8e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="93a8e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93a8e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="93a8e-113">Attributes</span></span>  
 <span data-ttu-id="93a8e-114">Keiner</span><span class="sxs-lookup"><span data-stu-id="93a8e-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="93a8e-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="93a8e-115">Child Elements</span></span>  
  
|<span data-ttu-id="93a8e-116">Element</span><span class="sxs-lookup"><span data-stu-id="93a8e-116">Element</span></span>|<span data-ttu-id="93a8e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a8e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93a8e-118">\<endpointverhaltens ></span><span class="sxs-lookup"><span data-stu-id="93a8e-118">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="93a8e-119">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Endpunkt definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="93a8e-119">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="93a8e-120">\<serviceverhaltens></span><span class="sxs-lookup"><span data-stu-id="93a8e-120">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="93a8e-121">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Dienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="93a8e-121">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93a8e-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="93a8e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="93a8e-123">Element</span><span class="sxs-lookup"><span data-stu-id="93a8e-123">Element</span></span>|<span data-ttu-id="93a8e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a8e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93a8e-125">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="93a8e-125">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="93a8e-126">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="93a8e-126">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93a8e-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93a8e-127">Remarks</span></span>  
 <span data-ttu-id="93a8e-128">Sie können das `<remove>`-Element verwenden, um ein bestimmtes Verhalten aus der Auflistung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="93a8e-128">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="93a8e-129">Geben Sie hierzu im `name`-Attribut des `<remove>`-Elements den Namen des zu entfernenden Verhaltens an.</span><span class="sxs-lookup"><span data-stu-id="93a8e-129">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="93a8e-130">Sie können auch das `<clear>`-Element verwenden, um sicherzustellen, dass eine Verhaltensauflistung zu Beginn leer ist, indem Sie den gesamten Inhalt der Auflistung entfernen.</span><span class="sxs-lookup"><span data-stu-id="93a8e-130">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a8e-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93a8e-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="93a8e-132">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="93a8e-132">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="93a8e-133">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="93a8e-133">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="93a8e-134">Angeben des Clientlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="93a8e-134">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="93a8e-135">Angeben des Dienstlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="93a8e-135">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="93a8e-136">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="93a8e-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
