---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 914fa04c9aff0c287913104cd9bedc570c473330
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201485"
---
# \<behaviors>

<span data-ttu-id="7cc27-101">Dieses Element definiert zwei untergeordnete Auflistungen mit dem Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="7cc27-101">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="7cc27-102">Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="7cc27-102">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="7cc27-103">Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7cc27-103">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="7cc27-104">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="7cc27-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7cc27-105">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7cc27-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="7cc27-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cc27-106">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cc27-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7cc27-107">Attributes and Elements</span></span>  

 <span data-ttu-id="7cc27-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7cc27-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cc27-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="7cc27-109">Attributes</span></span>  

 <span data-ttu-id="7cc27-110">Keine</span><span class="sxs-lookup"><span data-stu-id="7cc27-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7cc27-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7cc27-111">Child Elements</span></span>  
  
|<span data-ttu-id="7cc27-112">Element</span><span class="sxs-lookup"><span data-stu-id="7cc27-112">Element</span></span>|<span data-ttu-id="7cc27-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cc27-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="7cc27-114">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Endpunkt definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="7cc27-114">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="7cc27-115">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Dienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="7cc27-115">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7cc27-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7cc27-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7cc27-117">Element</span><span class="sxs-lookup"><span data-stu-id="7cc27-117">Element</span></span>|<span data-ttu-id="7cc27-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cc27-118">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="7cc27-119">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="7cc27-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cc27-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7cc27-120">Remarks</span></span>  

 <span data-ttu-id="7cc27-121">Sie können das `<remove>`-Element verwenden, um ein bestimmtes Verhalten aus der Auflistung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7cc27-121">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="7cc27-122">Geben Sie hierzu im `name`-Attribut des `<remove>`-Elements den Namen des zu entfernenden Verhaltens an.</span><span class="sxs-lookup"><span data-stu-id="7cc27-122">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="7cc27-123">Sie können auch das `<clear>`-Element verwenden, um sicherzustellen, dass eine Verhaltensauflistung zu Beginn leer ist, indem Sie den gesamten Inhalt der Auflistung entfernen.</span><span class="sxs-lookup"><span data-stu-id="7cc27-123">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc27-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cc27-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="7cc27-125">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="7cc27-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="7cc27-126">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="7cc27-126">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="7cc27-127">Angeben des Clientlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="7cc27-127">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="7cc27-128">Angeben des Dienstlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="7cc27-128">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="7cc27-129">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="7cc27-129">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
