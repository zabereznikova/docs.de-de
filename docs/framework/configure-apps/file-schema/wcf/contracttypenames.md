---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 12f9d4eca02ae3b306646826667c4eafef51a95c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919380"
---
# <a name="contracttypenames"></a><span data-ttu-id="e8b79-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="e8b79-101">\<contractTypeNames></span></span>
<span data-ttu-id="e8b79-102">Ein Konfigurationsabschnitt, der eine Liste von Vertragstypnamen angibt, bei denen es sich um die Vertragsnamen der gesuchten Dienste handelt, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8b79-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="e8b79-103">Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e8b79-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="e8b79-104">Beachten Sie, dass ein Endpunkt in Windows Communication Foundation (WCF) nur einen Vertrag unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="e8b79-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="e8b79-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e8b79-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8b79-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e8b79-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b79-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8b79-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8b79-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e8b79-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e8b79-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8b79-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8b79-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e8b79-110">Attributes</span></span>  
 <span data-ttu-id="e8b79-111">Keine</span><span class="sxs-lookup"><span data-stu-id="e8b79-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8b79-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8b79-112">Child Elements</span></span>  
  
|<span data-ttu-id="e8b79-113">Element</span><span class="sxs-lookup"><span data-stu-id="e8b79-113">Element</span></span>|<span data-ttu-id="e8b79-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8b79-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8b79-115">\<add></span><span class="sxs-lookup"><span data-stu-id="e8b79-115">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="e8b79-116">Ein Vertragstypname ist eine Eigenschaft, die auf den Kriteriensatz verweist, der in der Regel beim Suchen nach einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8b79-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8b79-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8b79-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e8b79-118">Element</span><span class="sxs-lookup"><span data-stu-id="e8b79-118">Element</span></span>|<span data-ttu-id="e8b79-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8b79-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8b79-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="e8b79-120">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="e8b79-121">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8b79-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="e8b79-122">Kriterien können in Suchkriterien gruppiert werden (wobei angegeben wird, welche Dienste Sie suchen) und nach Beendigungs Kriterien suchen (wie lange die Suche dauern sollte).</span><span class="sxs-lookup"><span data-stu-id="e8b79-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8b79-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8b79-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
