---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: b1cec9272a1de029ab72ea4d5f36c74630e5b93a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089496"
---
# <a name="contracttypenames"></a><span data-ttu-id="e71c8-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="e71c8-101">\<contractTypeNames></span></span>
<span data-ttu-id="e71c8-102">Ein Konfigurationsabschnitt, der eine Liste von Vertragstypnamen angibt, bei denen es sich um die Vertragsnamen der gesuchten Dienste handelt, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e71c8-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="e71c8-103">Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e71c8-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="e71c8-104">Beachten Sie, dass in Windows Communication Foundation (WCF), ein Endpunkt nur als einen Vertrag unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="e71c8-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="e71c8-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e71c8-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e71c8-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e71c8-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e71c8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e71c8-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e71c8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e71c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e71c8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e71c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e71c8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e71c8-110">Attributes</span></span>  
 <span data-ttu-id="e71c8-111">Keine</span><span class="sxs-lookup"><span data-stu-id="e71c8-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e71c8-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e71c8-112">Child Elements</span></span>  
  
|<span data-ttu-id="e71c8-113">Element</span><span class="sxs-lookup"><span data-stu-id="e71c8-113">Element</span></span>|<span data-ttu-id="e71c8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e71c8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e71c8-115">\<add></span><span class="sxs-lookup"><span data-stu-id="e71c8-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="e71c8-116">Ein Vertragstypname ist eine Eigenschaft, die auf den Kriteriensatz verweist, der in der Regel beim Suchen nach einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e71c8-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e71c8-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e71c8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e71c8-118">Element</span><span class="sxs-lookup"><span data-stu-id="e71c8-118">Element</span></span>|<span data-ttu-id="e71c8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e71c8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e71c8-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="e71c8-120">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="e71c8-121">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e71c8-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="e71c8-122">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden, für die) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).</span><span class="sxs-lookup"><span data-stu-id="e71c8-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e71c8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e71c8-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
