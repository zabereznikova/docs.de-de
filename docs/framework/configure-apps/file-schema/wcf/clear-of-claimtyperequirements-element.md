---
title: <clear> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 35d0391951204bd352918d3004f0cc4f9480b0e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090322"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="796dd-102">\<Deaktivieren Sie > der \<ClaimTypeRequirements >-Element</span><span class="sxs-lookup"><span data-stu-id="796dd-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="796dd-103">Gibt an, dass alle Anspruchstypen in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="796dd-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="796dd-104">Dadurch wird sichergestellt, dass die Auflistung beim Starten leer ist.</span><span class="sxs-lookup"><span data-stu-id="796dd-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="796dd-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="796dd-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="796dd-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="796dd-106">\<bindings></span></span>  
<span data-ttu-id="796dd-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="796dd-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="796dd-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="796dd-108">\<binding></span></span>  
<span data-ttu-id="796dd-109">\<security></span><span class="sxs-lookup"><span data-stu-id="796dd-109">\<security></span></span>  
<span data-ttu-id="796dd-110">\<message></span><span class="sxs-lookup"><span data-stu-id="796dd-110">\<message></span></span>  
<span data-ttu-id="796dd-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="796dd-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="796dd-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="796dd-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="796dd-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="796dd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="796dd-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="796dd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="796dd-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="796dd-115">Attributes</span></span>  
 <span data-ttu-id="796dd-116">Keine</span><span class="sxs-lookup"><span data-stu-id="796dd-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="796dd-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="796dd-117">Child Elements</span></span>  
 <span data-ttu-id="796dd-118">Keine</span><span class="sxs-lookup"><span data-stu-id="796dd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="796dd-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="796dd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="796dd-120">Element</span><span class="sxs-lookup"><span data-stu-id="796dd-120">Element</span></span>|<span data-ttu-id="796dd-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="796dd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="796dd-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="796dd-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="796dd-123">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="796dd-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="796dd-124">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="796dd-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="796dd-125">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="796dd-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="796dd-126">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="796dd-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="796dd-127">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="796dd-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="796dd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="796dd-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
