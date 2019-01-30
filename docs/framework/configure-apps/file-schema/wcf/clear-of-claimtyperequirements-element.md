---
title: <clear> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: b20d5c1808bf41d1ecd6b3e3a61606ae45b0fbdd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270337"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="67f6d-102">\<Deaktivieren Sie > der \<ClaimTypeRequirements >-Element</span><span class="sxs-lookup"><span data-stu-id="67f6d-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="67f6d-103">Gibt an, dass alle Anspruchstypen in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="67f6d-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="67f6d-104">Dadurch wird sichergestellt, dass die Auflistung beim Starten leer ist.</span><span class="sxs-lookup"><span data-stu-id="67f6d-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="67f6d-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="67f6d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="67f6d-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="67f6d-106">\<bindings></span></span>  
<span data-ttu-id="67f6d-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="67f6d-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="67f6d-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="67f6d-108">\<binding></span></span>  
<span data-ttu-id="67f6d-109">\<security></span><span class="sxs-lookup"><span data-stu-id="67f6d-109">\<security></span></span>  
<span data-ttu-id="67f6d-110">\<message></span><span class="sxs-lookup"><span data-stu-id="67f6d-110">\<message></span></span>  
<span data-ttu-id="67f6d-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="67f6d-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f6d-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="67f6d-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67f6d-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="67f6d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="67f6d-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="67f6d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67f6d-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="67f6d-115">Attributes</span></span>  
 <span data-ttu-id="67f6d-116">Keine</span><span class="sxs-lookup"><span data-stu-id="67f6d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="67f6d-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="67f6d-117">Child Elements</span></span>  
 <span data-ttu-id="67f6d-118">Keine</span><span class="sxs-lookup"><span data-stu-id="67f6d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67f6d-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="67f6d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="67f6d-120">Element</span><span class="sxs-lookup"><span data-stu-id="67f6d-120">Element</span></span>|<span data-ttu-id="67f6d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67f6d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67f6d-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="67f6d-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="67f6d-123">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="67f6d-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="67f6d-124">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="67f6d-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="67f6d-125">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="67f6d-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="67f6d-126">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="67f6d-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="67f6d-127">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="67f6d-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67f6d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67f6d-128">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
