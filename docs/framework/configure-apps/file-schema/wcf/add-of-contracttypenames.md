---
title: <add> von <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850530"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="3a570-102">\<Fügen Sie > \<von "kontrattypames" hinzu ></span><span class="sxs-lookup"><span data-stu-id="3a570-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="3a570-103">Ein Konfigurationselement, das den Vertragsnamen der Dienste angibt, nach denen gesucht wird, sowie die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a570-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="3a570-104">Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die ALLEN Verträgen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3a570-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="3a570-105">Beachten Sie, dass ein Endpunkt in Windows Communication Foundation (WCF) nur einen Vertrag unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="3a570-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="3a570-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a570-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a570-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3a570-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3a570-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3a570-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="3a570-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DynamicEndpoint->** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="3a570-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="3a570-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardendpoint->** </span><span class="sxs-lookup"><span data-stu-id="3a570-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="3a570-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryclientsettings->** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="3a570-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="3a570-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<FindCriteria->** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="3a570-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="3a570-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> "kontrattypames"** ](contracttypenames.md)</span><span class="sxs-lookup"><span data-stu-id="3a570-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)</span></span>\
<span data-ttu-id="3a570-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="3a570-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a570-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a570-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a570-116">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a570-116">Attributes and Elements</span></span>  
 <span data-ttu-id="3a570-117">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a570-117">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a570-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a570-118">Attributes</span></span>  
  
|<span data-ttu-id="3a570-119">Attribut</span><span class="sxs-lookup"><span data-stu-id="3a570-119">Attribute</span></span>|<span data-ttu-id="3a570-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a570-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a570-121">NAME</span><span class="sxs-lookup"><span data-stu-id="3a570-121">name</span></span>|<span data-ttu-id="3a570-122">Eine Zeichenfolge, die den Namen des Vertragstyps angibt.</span><span class="sxs-lookup"><span data-stu-id="3a570-122">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="3a570-123">namespace</span><span class="sxs-lookup"><span data-stu-id="3a570-123">namespace</span></span>|<span data-ttu-id="3a570-124">Eine Zeichenfolge, die den Namespace des Vertragstyps angibt.</span><span class="sxs-lookup"><span data-stu-id="3a570-124">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a570-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a570-125">Child Elements</span></span>  
 <span data-ttu-id="3a570-126">None</span><span class="sxs-lookup"><span data-stu-id="3a570-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a570-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a570-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3a570-128">Element</span><span class="sxs-lookup"><span data-stu-id="3a570-128">Element</span></span>|<span data-ttu-id="3a570-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a570-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a570-130">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="3a570-130">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="3a570-131">Eine Auflistung von Vertragstypnamen.</span><span class="sxs-lookup"><span data-stu-id="3a570-131">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a570-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a570-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
