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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 96155ed805d99a3678c5d20d83a490efb9811815
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="cc70c-102">&lt;remove&gt; des &lt;claimTypeRequirements&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="cc70c-102">&lt;remove&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="cc70c-103">Gibt die Typen von Ansprüchen an, die in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc70c-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="cc70c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cc70c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cc70c-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="cc70c-105">\<bindings></span></span>  
<span data-ttu-id="cc70c-106">\<WsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="cc70c-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="cc70c-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="cc70c-107">\<binding></span></span>  
<span data-ttu-id="cc70c-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="cc70c-108">\<security></span></span>  
<span data-ttu-id="cc70c-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="cc70c-109">\<message></span></span>  
<span data-ttu-id="cc70c-110">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="cc70c-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc70c-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc70c-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <remove claimType="URI" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc70c-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cc70c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cc70c-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc70c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc70c-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="cc70c-114">Attributes</span></span>  
  
|<span data-ttu-id="cc70c-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="cc70c-115">Attribute</span></span>|<span data-ttu-id="cc70c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc70c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc70c-117">claimType</span><span class="sxs-lookup"><span data-stu-id="cc70c-117">claimType</span></span>|<span data-ttu-id="cc70c-118">Ein URI, der den Typ eines zu entfernenden Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="cc70c-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc70c-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc70c-119">Child Elements</span></span>  
 <span data-ttu-id="cc70c-120">Keine</span><span class="sxs-lookup"><span data-stu-id="cc70c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc70c-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc70c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cc70c-122">Element</span><span class="sxs-lookup"><span data-stu-id="cc70c-122">Element</span></span>|<span data-ttu-id="cc70c-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc70c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc70c-124">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="cc70c-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="cc70c-125">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="cc70c-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="cc70c-126">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="cc70c-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="cc70c-127">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="cc70c-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="cc70c-128">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cc70c-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="cc70c-129">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="cc70c-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc70c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc70c-130">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
