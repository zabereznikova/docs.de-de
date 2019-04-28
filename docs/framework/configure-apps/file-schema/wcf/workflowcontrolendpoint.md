---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: a9c16d1036a8177120cd152d4ac211ad084d588e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769641"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="a4d08-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="a4d08-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="a4d08-102">Dieses Konfigurationselement definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).</span><span class="sxs-lookup"><span data-stu-id="a4d08-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="a4d08-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a4d08-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4d08-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a4d08-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d08-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4d08-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4d08-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a4d08-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a4d08-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4d08-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4d08-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="a4d08-108">Attributes</span></span>  
  
|<span data-ttu-id="a4d08-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="a4d08-109">Attribute</span></span>|<span data-ttu-id="a4d08-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4d08-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4d08-111">Name</span><span class="sxs-lookup"><span data-stu-id="a4d08-111">name</span></span>|<span data-ttu-id="a4d08-112">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="a4d08-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="a4d08-113">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4d08-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4d08-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4d08-114">Child Elements</span></span>  
 <span data-ttu-id="a4d08-115">Keine</span><span class="sxs-lookup"><span data-stu-id="a4d08-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4d08-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4d08-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a4d08-117">Element</span><span class="sxs-lookup"><span data-stu-id="a4d08-117">Element</span></span>|<span data-ttu-id="a4d08-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4d08-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4d08-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a4d08-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="a4d08-120">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="a4d08-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4d08-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4d08-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
