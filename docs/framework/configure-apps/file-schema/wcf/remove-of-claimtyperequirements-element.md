---
title: '&lt;remove&gt; des &lt;claimTypeRequirements&gt;-Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49009cb7e988c27ccc426e29c6ac973e553a0f73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="ab70f-102">&lt;remove&gt; des &lt;claimTypeRequirements&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="ab70f-102">&lt;remove&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="ab70f-103">Gibt die Typen von Ansprüchen an, die in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ab70f-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="ab70f-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ab70f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ab70f-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="ab70f-105">\<bindings></span></span>  
<span data-ttu-id="ab70f-106">\<WsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="ab70f-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="ab70f-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="ab70f-107">\<binding></span></span>  
<span data-ttu-id="ab70f-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="ab70f-108">\<security></span></span>  
<span data-ttu-id="ab70f-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="ab70f-109">\<message></span></span>  
<span data-ttu-id="ab70f-110">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="ab70f-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab70f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab70f-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <remove claimType="URI" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab70f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ab70f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ab70f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab70f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab70f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="ab70f-114">Attributes</span></span>  
  
|<span data-ttu-id="ab70f-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="ab70f-115">Attribute</span></span>|<span data-ttu-id="ab70f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab70f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab70f-117">claimType</span><span class="sxs-lookup"><span data-stu-id="ab70f-117">claimType</span></span>|<span data-ttu-id="ab70f-118">Ein URI, der den Typ eines zu entfernenden Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="ab70f-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab70f-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab70f-119">Child Elements</span></span>  
 <span data-ttu-id="ab70f-120">Keine</span><span class="sxs-lookup"><span data-stu-id="ab70f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab70f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab70f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ab70f-122">Element</span><span class="sxs-lookup"><span data-stu-id="ab70f-122">Element</span></span>|<span data-ttu-id="ab70f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab70f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab70f-124">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="ab70f-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="ab70f-125">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="ab70f-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="ab70f-126">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="ab70f-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="ab70f-127">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="ab70f-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="ab70f-128">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ab70f-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="ab70f-129">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="ab70f-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab70f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab70f-130">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
