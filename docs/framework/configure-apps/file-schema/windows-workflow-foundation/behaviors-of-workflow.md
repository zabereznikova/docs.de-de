---
title: <behaviors>des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398878"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="b1344-102">\<Verhaltens > des Workflows</span><span class="sxs-lookup"><span data-stu-id="b1344-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="b1344-103">Dieses Element enthält die **Service** Verhaltens-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b1344-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="b1344-104">Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="b1344-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="b1344-105">Jedes Behavior-Element wird durch das eindeutige **Name** -Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b1344-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
<span data-ttu-id="b1344-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b1344-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b1344-107">&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b1344-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b1344-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<Verhaltens >**</span><span class="sxs-lookup"><span data-stu-id="b1344-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1344-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1344-109">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1344-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1344-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b1344-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1344-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1344-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1344-112">Attributes</span></span>  
 <span data-ttu-id="b1344-113">None</span><span class="sxs-lookup"><span data-stu-id="b1344-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1344-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1344-114">Child Elements</span></span>  
  
|<span data-ttu-id="b1344-115">Element</span><span class="sxs-lookup"><span data-stu-id="b1344-115">Element</span></span>|<span data-ttu-id="b1344-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1344-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1344-117">\<serviceverhaltens></span><span class="sxs-lookup"><span data-stu-id="b1344-117">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="b1344-118">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="b1344-118">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1344-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1344-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b1344-120">Element</span><span class="sxs-lookup"><span data-stu-id="b1344-120">Element</span></span>|<span data-ttu-id="b1344-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1344-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1344-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b1344-122">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="b1344-123">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="b1344-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1344-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1344-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="b1344-125">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="b1344-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
