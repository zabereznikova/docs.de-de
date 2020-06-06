---
title: <behaviors>des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398878"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="bbb6a-102">\<behaviors>des Workflows</span><span class="sxs-lookup"><span data-stu-id="bbb6a-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="bbb6a-103">Dieses Element enthält die **Service** Verhaltens-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="bbb6a-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="bbb6a-104">Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="bbb6a-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="bbb6a-105">Jedes Behavior-Element wird durch das eindeutige **Name** -Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bbb6a-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="bbb6a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbb6a-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbb6a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bbb6a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="bbb6a-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bbb6a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbb6a-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="bbb6a-109">Attributes</span></span>  
 <span data-ttu-id="bbb6a-110">Keine</span><span class="sxs-lookup"><span data-stu-id="bbb6a-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bbb6a-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bbb6a-111">Child Elements</span></span>  
  
|<span data-ttu-id="bbb6a-112">Element</span><span class="sxs-lookup"><span data-stu-id="bbb6a-112">Element</span></span>|<span data-ttu-id="bbb6a-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bbb6a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="bbb6a-114">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="bbb6a-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bbb6a-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bbb6a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bbb6a-116">Element</span><span class="sxs-lookup"><span data-stu-id="bbb6a-116">Element</span></span>|<span data-ttu-id="bbb6a-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bbb6a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="bbb6a-118">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="bbb6a-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbb6a-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbb6a-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="bbb6a-120">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="bbb6a-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
