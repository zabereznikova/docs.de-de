---
title: <behaviors> des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: e61a2078c5989a3b100e77e6b2f753b0ee5dd934
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271785"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="df42f-102">\<Behaviors > des Workflows</span><span class="sxs-lookup"><span data-stu-id="df42f-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="df42f-103">Dieses Element enthält die **ServiceBehaviors** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="df42f-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="df42f-104">Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="df42f-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="df42f-105">Jedes verhaltenselement wird durch seinen eindeutigen identifiziert **Namen** Attribut.</span><span class="sxs-lookup"><span data-stu-id="df42f-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="df42f-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="df42f-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df42f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="df42f-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df42f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="df42f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="df42f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="df42f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df42f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="df42f-110">Attributes</span></span>  
 <span data-ttu-id="df42f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="df42f-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="df42f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df42f-112">Child Elements</span></span>  
  
|<span data-ttu-id="df42f-113">Element</span><span class="sxs-lookup"><span data-stu-id="df42f-113">Element</span></span>|<span data-ttu-id="df42f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df42f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df42f-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="df42f-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="df42f-116">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="df42f-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df42f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df42f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="df42f-118">Element</span><span class="sxs-lookup"><span data-stu-id="df42f-118">Element</span></span>|<span data-ttu-id="df42f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df42f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df42f-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="df42f-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="df42f-121">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="df42f-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df42f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df42f-122">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="df42f-123">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="df42f-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
