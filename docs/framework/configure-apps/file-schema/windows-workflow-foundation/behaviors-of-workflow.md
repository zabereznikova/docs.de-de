---
title: '&lt;behaviors&gt; des Workflows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40278c0a3d99dd5c37df1d642b8a2e13e9f62633
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="89c69-102">&lt;behaviors&gt; des Workflows</span><span class="sxs-lookup"><span data-stu-id="89c69-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="89c69-103">Dieses Element enthält die **ServiceBehaviors** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="89c69-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="89c69-104">Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente.</span><span class="sxs-lookup"><span data-stu-id="89c69-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="89c69-105">Jedes verhaltenselement wird durch seinen eindeutigen identifiziert **Namen** Attribut.</span><span class="sxs-lookup"><span data-stu-id="89c69-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="89c69-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="89c69-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c69-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="89c69-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89c69-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89c69-108">Attributes and Elements</span></span>  
 <span data-ttu-id="89c69-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89c69-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89c69-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="89c69-110">Attributes</span></span>  
 <span data-ttu-id="89c69-111">Keine</span><span class="sxs-lookup"><span data-stu-id="89c69-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89c69-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89c69-112">Child Elements</span></span>  
  
|<span data-ttu-id="89c69-113">Element</span><span class="sxs-lookup"><span data-stu-id="89c69-113">Element</span></span>|<span data-ttu-id="89c69-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89c69-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89c69-115">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="89c69-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="89c69-116">Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="89c69-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89c69-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89c69-117">Parent Elements</span></span>  
  
|<span data-ttu-id="89c69-118">Element</span><span class="sxs-lookup"><span data-stu-id="89c69-118">Element</span></span>|<span data-ttu-id="89c69-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89c69-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89c69-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="89c69-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="89c69-121">Das Stammelement aller Workflow-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="89c69-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89c69-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89c69-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="89c69-123">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="89c69-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
