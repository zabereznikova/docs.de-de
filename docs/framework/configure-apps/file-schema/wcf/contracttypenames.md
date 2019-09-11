---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: c67e5b9e82b96e27ce73512680bd4236b26ef4dd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855455"
---
# <a name="contracttypenames"></a><span data-ttu-id="9a5fb-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="9a5fb-101">\<contractTypeNames></span></span>
<span data-ttu-id="9a5fb-102">Ein Konfigurationsabschnitt, der eine Liste von Vertragstypnamen angibt, bei denen es sich um die Vertragsnamen der gesuchten Dienste handelt, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a5fb-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="9a5fb-103">Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9a5fb-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="9a5fb-104">Beachten Sie, dass ein Endpunkt in Windows Communication Foundation (WCF) nur einen Vertrag unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="9a5fb-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="9a5fb-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a5fb-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9a5fb-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9a5fb-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9a5fb-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="9a5fb-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="9a5fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DynamicEndpoint->** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="9a5fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="9a5fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardendpoint->** </span><span class="sxs-lookup"><span data-stu-id="9a5fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="9a5fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryclientsettings->** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="9a5fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="9a5fb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<FindCriteria->** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="9a5fb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="9a5fb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> "kontrattypames"**</span><span class="sxs-lookup"><span data-stu-id="9a5fb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a5fb-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a5fb-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a5fb-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9a5fb-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9a5fb-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a5fb-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a5fb-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="9a5fb-116">Attributes</span></span>  
 <span data-ttu-id="9a5fb-117">Keine</span><span class="sxs-lookup"><span data-stu-id="9a5fb-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a5fb-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a5fb-118">Child Elements</span></span>  
  
|<span data-ttu-id="9a5fb-119">Element</span><span class="sxs-lookup"><span data-stu-id="9a5fb-119">Element</span></span>|<span data-ttu-id="9a5fb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a5fb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a5fb-121">\<add></span><span class="sxs-lookup"><span data-stu-id="9a5fb-121">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="9a5fb-122">Ein Vertragstypname ist eine Eigenschaft, die auf den Kriteriensatz verweist, der in der Regel beim Suchen nach einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9a5fb-122">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a5fb-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a5fb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9a5fb-124">Element</span><span class="sxs-lookup"><span data-stu-id="9a5fb-124">Element</span></span>|<span data-ttu-id="9a5fb-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a5fb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a5fb-126">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="9a5fb-126">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="9a5fb-127">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9a5fb-127">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="9a5fb-128">Kriterien können in Suchkriterien gruppiert werden (wobei angegeben wird, welche Dienste Sie suchen) und nach Beendigungs Kriterien suchen (wie lange die Suche dauern sollte).</span><span class="sxs-lookup"><span data-stu-id="9a5fb-128">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a5fb-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a5fb-129">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
