---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 572ff7e119828897860944a430e5f51f5d1c3cad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194842"
---
# \<workflowControlEndpoint>

<span data-ttu-id="a4423-101">Dieses Konfigurationselement definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).</span><span class="sxs-lookup"><span data-stu-id="a4423-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="a4423-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4423-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4423-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a4423-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a4423-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4423-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4423-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="a4423-105">Attributes</span></span>  
  
|<span data-ttu-id="a4423-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a4423-106">Attribute</span></span>|<span data-ttu-id="a4423-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4423-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4423-108">name</span><span class="sxs-lookup"><span data-stu-id="a4423-108">name</span></span>|<span data-ttu-id="a4423-109">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="a4423-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="a4423-110">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4423-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4423-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4423-111">Child Elements</span></span>  

 <span data-ttu-id="a4423-112">Keine</span><span class="sxs-lookup"><span data-stu-id="a4423-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4423-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4423-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a4423-114">Element</span><span class="sxs-lookup"><span data-stu-id="a4423-114">Element</span></span>|<span data-ttu-id="a4423-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4423-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="a4423-116">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="a4423-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4423-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4423-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
