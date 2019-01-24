---
title: '&lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 2c3f501f44d9e3c601e654041eb9d5a7de8a0a07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626770"
---
# <a name="ltcontracttypenamesgt"></a><span data-ttu-id="d4dda-102">&lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="d4dda-102">&lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="d4dda-103">Ein Konfigurationsabschnitt, der eine Liste von Vertragstypnamen angibt, bei denen es sich um die Vertragsnamen der gesuchten Dienste handelt, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4dda-103">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="d4dda-104">Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d4dda-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="d4dda-105">Beachten Sie, dass in Windows Communication Foundation (WCF), ein Endpunkt nur als einen Vertrag unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="d4dda-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="d4dda-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d4dda-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="d4dda-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d4dda-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4dda-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4dda-108">Syntax</span></span>  
  
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
              <add name="String"
                   namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4dda-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d4dda-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d4dda-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d4dda-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4dda-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d4dda-111">Attributes</span></span>  
 <span data-ttu-id="d4dda-112">Keine</span><span class="sxs-lookup"><span data-stu-id="d4dda-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4dda-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4dda-113">Child Elements</span></span>  
  
|<span data-ttu-id="d4dda-114">Element</span><span class="sxs-lookup"><span data-stu-id="d4dda-114">Element</span></span>|<span data-ttu-id="d4dda-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4dda-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4dda-116">\<add></span><span class="sxs-lookup"><span data-stu-id="d4dda-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="d4dda-117">Ein Vertragstypname ist eine Eigenschaft, die auf den Kriteriensatz verweist, der in der Regel beim Suchen nach einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4dda-117">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4dda-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4dda-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d4dda-119">Element</span><span class="sxs-lookup"><span data-stu-id="d4dda-119">Element</span></span>|<span data-ttu-id="d4dda-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4dda-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4dda-121">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="d4dda-121">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="d4dda-122">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4dda-122">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="d4dda-123">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden, für die) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).</span><span class="sxs-lookup"><span data-stu-id="d4dda-123">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4dda-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4dda-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
