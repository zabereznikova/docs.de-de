---
title: '&lt;workflowControlEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8371b9180fec9877ac58026c26fb60c8ccdaa752
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="89ee7-102">&lt;workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="89ee7-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="89ee7-103">Dieses Konfigurationselement definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).</span><span class="sxs-lookup"><span data-stu-id="89ee7-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="89ee7-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="89ee7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="89ee7-105">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="89ee7-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89ee7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="89ee7-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89ee7-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89ee7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="89ee7-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89ee7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89ee7-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="89ee7-109">Attributes</span></span>  
  
|<span data-ttu-id="89ee7-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="89ee7-110">Attribute</span></span>|<span data-ttu-id="89ee7-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89ee7-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89ee7-112">Name</span><span class="sxs-lookup"><span data-stu-id="89ee7-112">name</span></span>|<span data-ttu-id="89ee7-113">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="89ee7-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="89ee7-114">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="89ee7-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89ee7-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89ee7-115">Child Elements</span></span>  
 <span data-ttu-id="89ee7-116">Keine</span><span class="sxs-lookup"><span data-stu-id="89ee7-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89ee7-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89ee7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="89ee7-118">Element</span><span class="sxs-lookup"><span data-stu-id="89ee7-118">Element</span></span>|<span data-ttu-id="89ee7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89ee7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89ee7-120">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="89ee7-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="89ee7-121">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="89ee7-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89ee7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89ee7-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
