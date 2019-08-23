---
title: <behaviors>des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 7dd3b0b20c9d7accd80a85b3693e67ffc9b729e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945997"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="c8277-102">\<Verhaltens > des Workflows</span><span class="sxs-lookup"><span data-stu-id="c8277-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="c8277-103">Dieses Element enthält die **Service** Verhaltens-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c8277-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="c8277-104">Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="c8277-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="c8277-105">Jedes Behavior-Element wird durch das eindeutige **Name** -Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c8277-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="c8277-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c8277-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8277-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8277-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8277-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c8277-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c8277-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8277-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8277-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c8277-110">Attributes</span></span>  
 <span data-ttu-id="c8277-111">None</span><span class="sxs-lookup"><span data-stu-id="c8277-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8277-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8277-112">Child Elements</span></span>  
  
|<span data-ttu-id="c8277-113">Element</span><span class="sxs-lookup"><span data-stu-id="c8277-113">Element</span></span>|<span data-ttu-id="c8277-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8277-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8277-115">\<serviceverhaltens></span><span class="sxs-lookup"><span data-stu-id="c8277-115">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="c8277-116">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="c8277-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8277-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8277-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c8277-118">Element</span><span class="sxs-lookup"><span data-stu-id="c8277-118">Element</span></span>|<span data-ttu-id="c8277-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8277-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8277-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c8277-120">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="c8277-121">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="c8277-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8277-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8277-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="c8277-123">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="c8277-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
