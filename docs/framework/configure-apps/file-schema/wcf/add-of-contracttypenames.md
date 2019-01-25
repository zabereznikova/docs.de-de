---
title: '&lt;add&gt; von &lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: cf9a1ae28b53b841ac5d8d85d31e1548e36369ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735726"
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="953f4-102">&lt;add&gt; von &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="953f4-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="953f4-103">Ein Konfigurationselement, das den Vertragsnamen der Dienste angibt, nach denen gesucht wird, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="953f4-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="953f4-104">Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="953f4-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="953f4-105">Beachten Sie, dass in Windows Communication Foundation (WCF), ein Endpunkt nur als einen Vertrag unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="953f4-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="953f4-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="953f4-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="953f4-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="953f4-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="953f4-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="953f4-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="953f4-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="953f4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="953f4-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="953f4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="953f4-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="953f4-111">Attributes</span></span>  
  
|<span data-ttu-id="953f4-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="953f4-112">Attribute</span></span>|<span data-ttu-id="953f4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="953f4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="953f4-114">Name</span><span class="sxs-lookup"><span data-stu-id="953f4-114">name</span></span>|<span data-ttu-id="953f4-115">Eine Zeichenfolge, die den Namen des Vertragstyps angibt.</span><span class="sxs-lookup"><span data-stu-id="953f4-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="953f4-116">namespace</span><span class="sxs-lookup"><span data-stu-id="953f4-116">namespace</span></span>|<span data-ttu-id="953f4-117">Eine Zeichenfolge, die den Namespace des Vertragstyps angibt.</span><span class="sxs-lookup"><span data-stu-id="953f4-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="953f4-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="953f4-118">Child Elements</span></span>  
 <span data-ttu-id="953f4-119">Keine</span><span class="sxs-lookup"><span data-stu-id="953f4-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="953f4-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="953f4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="953f4-121">Element</span><span class="sxs-lookup"><span data-stu-id="953f4-121">Element</span></span>|<span data-ttu-id="953f4-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="953f4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="953f4-123">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="953f4-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="953f4-124">Eine Auflistung von Vertragstypnamen.</span><span class="sxs-lookup"><span data-stu-id="953f4-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="953f4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="953f4-125">See also</span></span>
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
