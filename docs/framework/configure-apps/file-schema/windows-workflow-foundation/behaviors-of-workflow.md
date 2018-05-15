---
title: '&lt;behaviors&gt; des Workflows'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 762fd1ff0de7980848ac3921706f406932c7f35d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="1cef8-102">&lt;behaviors&gt; des Workflows</span><span class="sxs-lookup"><span data-stu-id="1cef8-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="1cef8-103">Dieses Element enthält die **ServiceBehaviors** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1cef8-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="1cef8-104">Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="1cef8-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="1cef8-105">Jedes verhaltenselement wird durch seinen eindeutigen identifiziert **Namen** Attribut.</span><span class="sxs-lookup"><span data-stu-id="1cef8-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="1cef8-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1cef8-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cef8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1cef8-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cef8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1cef8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1cef8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1cef8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cef8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="1cef8-110">Attributes</span></span>  
 <span data-ttu-id="1cef8-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="1cef8-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1cef8-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1cef8-112">Child Elements</span></span>  
  
|<span data-ttu-id="1cef8-113">Element</span><span class="sxs-lookup"><span data-stu-id="1cef8-113">Element</span></span>|<span data-ttu-id="1cef8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1cef8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cef8-115">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1cef8-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="1cef8-116">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="1cef8-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1cef8-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1cef8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1cef8-118">Element</span><span class="sxs-lookup"><span data-stu-id="1cef8-118">Element</span></span>|<span data-ttu-id="1cef8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1cef8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cef8-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1cef8-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="1cef8-121">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="1cef8-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cef8-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cef8-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="1cef8-123">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="1cef8-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
