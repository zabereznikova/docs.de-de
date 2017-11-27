---
title: '&lt;add&gt; von &lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bebea15e6d1f24c95905355dbced33aa9c5150f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="1b889-102">&lt;add&gt; von &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="1b889-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="1b889-103">Ein Konfigurationselement, das den Vertragsnamen der Dienste angibt, nach denen gesucht wird, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b889-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="1b889-104">Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1b889-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="1b889-105">Beachten Sie, dass ein Endpunkt unter [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] nur einen Vertrag unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="1b889-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="1b889-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1b889-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b889-107">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="1b889-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b889-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b889-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b889-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1b889-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1b889-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1b889-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b889-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1b889-111">Attributes</span></span>  
  
|<span data-ttu-id="1b889-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="1b889-112">Attribute</span></span>|<span data-ttu-id="1b889-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b889-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b889-114">Name</span><span class="sxs-lookup"><span data-stu-id="1b889-114">name</span></span>|<span data-ttu-id="1b889-115">Eine Zeichenfolge, die den Namen des Vertragstyps angibt.</span><span class="sxs-lookup"><span data-stu-id="1b889-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="1b889-116">namespace</span><span class="sxs-lookup"><span data-stu-id="1b889-116">namespace</span></span>|<span data-ttu-id="1b889-117">Eine Zeichenfolge, die den Namespace des Vertragstyps angibt.</span><span class="sxs-lookup"><span data-stu-id="1b889-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b889-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b889-118">Child Elements</span></span>  
 <span data-ttu-id="1b889-119">Keine</span><span class="sxs-lookup"><span data-stu-id="1b889-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b889-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b889-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1b889-121">Element</span><span class="sxs-lookup"><span data-stu-id="1b889-121">Element</span></span>|<span data-ttu-id="1b889-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b889-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b889-123">\<ContractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="1b889-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="1b889-124">Eine Auflistung von Vertragstypnamen.</span><span class="sxs-lookup"><span data-stu-id="1b889-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b889-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b889-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
