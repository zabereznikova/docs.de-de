---
title: '&lt;remove&gt; des &lt;claimTypeRequirements&gt;-Elements'
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 5d1f9c963792336f0938113beefbdef770831e9d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753242"
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="6779c-102">&lt;remove&gt; des &lt;claimTypeRequirements&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="6779c-102">&lt;remove&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="6779c-103">Gibt die Typen von Ansprüchen an, die in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6779c-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="6779c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6779c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6779c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6779c-105">\<bindings></span></span>  
<span data-ttu-id="6779c-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="6779c-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="6779c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="6779c-107">\<binding></span></span>  
<span data-ttu-id="6779c-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="6779c-108">\<security></span></span>  
<span data-ttu-id="6779c-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="6779c-109">\<message></span></span>  
<span data-ttu-id="6779c-110">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="6779c-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6779c-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="6779c-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <remove claimType="URI" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6779c-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6779c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6779c-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6779c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6779c-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="6779c-114">Attributes</span></span>  
  
|<span data-ttu-id="6779c-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="6779c-115">Attribute</span></span>|<span data-ttu-id="6779c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6779c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6779c-117">claimType</span><span class="sxs-lookup"><span data-stu-id="6779c-117">claimType</span></span>|<span data-ttu-id="6779c-118">Ein URI, der den Typ eines zu entfernenden Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="6779c-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6779c-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6779c-119">Child Elements</span></span>  
 <span data-ttu-id="6779c-120">Keine</span><span class="sxs-lookup"><span data-stu-id="6779c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6779c-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6779c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6779c-122">Element</span><span class="sxs-lookup"><span data-stu-id="6779c-122">Element</span></span>|<span data-ttu-id="6779c-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6779c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6779c-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="6779c-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="6779c-125">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="6779c-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="6779c-126">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="6779c-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="6779c-127">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="6779c-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="6779c-128">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6779c-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="6779c-129">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="6779c-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6779c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6779c-130">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
