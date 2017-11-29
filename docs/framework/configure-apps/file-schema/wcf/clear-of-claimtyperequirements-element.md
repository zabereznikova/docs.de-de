---
title: '&lt;clear&gt; von &lt;claimTypeRequirements&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 69752480a7f399a202d497e12a783ffa091dd4b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="c2655-102">&lt;clear&gt; von &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="c2655-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="c2655-103">Gibt an, dass alle Anspruchstypen in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c2655-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="c2655-104">Dadurch wird sichergestellt, dass die Auflistung beim Starten leer ist.</span><span class="sxs-lookup"><span data-stu-id="c2655-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="c2655-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c2655-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="c2655-106">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="c2655-106">\<bindings></span></span>  
<span data-ttu-id="c2655-107">\<WsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="c2655-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="c2655-108">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="c2655-108">\<binding></span></span>  
<span data-ttu-id="c2655-109">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="c2655-109">\<security></span></span>  
<span data-ttu-id="c2655-110">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="c2655-110">\<message></span></span>  
<span data-ttu-id="c2655-111">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="c2655-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2655-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2655-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <clear />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2655-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c2655-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c2655-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c2655-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2655-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="c2655-115">Attributes</span></span>  
 <span data-ttu-id="c2655-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="c2655-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c2655-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2655-117">Child Elements</span></span>  
 <span data-ttu-id="c2655-118">Keine</span><span class="sxs-lookup"><span data-stu-id="c2655-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2655-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2655-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c2655-120">Element</span><span class="sxs-lookup"><span data-stu-id="c2655-120">Element</span></span>|<span data-ttu-id="c2655-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2655-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2655-122">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="c2655-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="c2655-123">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="c2655-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="c2655-124">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="c2655-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="c2655-125">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="c2655-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c2655-126">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c2655-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c2655-127">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="c2655-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2655-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2655-128">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
