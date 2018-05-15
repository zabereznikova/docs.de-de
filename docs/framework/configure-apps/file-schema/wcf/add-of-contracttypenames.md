---
title: '&lt;add&gt; von &lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 159ab5a40a69c075b648a0c161babe604d13377b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="dec72-102">&lt;add&gt; von &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="dec72-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="dec72-103">Ein Konfigurationselement, das den Vertragsnamen der Dienste angibt, nach denen gesucht wird, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dec72-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="dec72-104">Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dec72-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="dec72-105">Beachten Sie, dass in der Windows Communication Foundation (WCF) ein Endpunkt nur als einen Vertrag unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="dec72-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="dec72-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dec72-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="dec72-107">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="dec72-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec72-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="dec72-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dec72-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dec72-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dec72-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dec72-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dec72-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="dec72-111">Attributes</span></span>  
  
|<span data-ttu-id="dec72-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="dec72-112">Attribute</span></span>|<span data-ttu-id="dec72-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dec72-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dec72-114">Name</span><span class="sxs-lookup"><span data-stu-id="dec72-114">name</span></span>|<span data-ttu-id="dec72-115">Eine Zeichenfolge, die den Namen des Vertragstyps angibt.</span><span class="sxs-lookup"><span data-stu-id="dec72-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="dec72-116">namespace</span><span class="sxs-lookup"><span data-stu-id="dec72-116">namespace</span></span>|<span data-ttu-id="dec72-117">Eine Zeichenfolge, die den Namespace des Vertragstyps angibt.</span><span class="sxs-lookup"><span data-stu-id="dec72-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dec72-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dec72-118">Child Elements</span></span>  
 <span data-ttu-id="dec72-119">Keiner</span><span class="sxs-lookup"><span data-stu-id="dec72-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dec72-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dec72-120">Parent Elements</span></span>  
  
|<span data-ttu-id="dec72-121">Element</span><span class="sxs-lookup"><span data-stu-id="dec72-121">Element</span></span>|<span data-ttu-id="dec72-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dec72-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dec72-123">\<ContractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="dec72-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="dec72-124">Eine Auflistung von Vertragstypnamen.</span><span class="sxs-lookup"><span data-stu-id="dec72-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dec72-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dec72-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
