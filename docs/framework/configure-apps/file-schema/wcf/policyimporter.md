---
title: '&lt;policyImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b56c431c0e8dbab7bd4680a6e692d9b4f6e0eec4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="ff5f3-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="ff5f3-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="ff5f3-103">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="ff5f3-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="ff5f3-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ff5f3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ff5f3-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="ff5f3-105">\<client></span></span>  
<span data-ttu-id="ff5f3-106">\<Metadaten ></span><span class="sxs-lookup"><span data-stu-id="ff5f3-106">\<metadata></span></span>  
<span data-ttu-id="ff5f3-107">\<PolicyImporters ></span><span class="sxs-lookup"><span data-stu-id="ff5f3-107">\<policyImporters></span></span>  
<span data-ttu-id="ff5f3-108">\<PolicyImporter ></span><span class="sxs-lookup"><span data-stu-id="ff5f3-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff5f3-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff5f3-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff5f3-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ff5f3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ff5f3-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff5f3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff5f3-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="ff5f3-112">Attributes</span></span>  
  
|<span data-ttu-id="ff5f3-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="ff5f3-113">Attribute</span></span>|<span data-ttu-id="ff5f3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff5f3-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="ff5f3-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="ff5f3-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff5f3-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff5f3-116">Child Elements</span></span>  
 <span data-ttu-id="ff5f3-117">Keine</span><span class="sxs-lookup"><span data-stu-id="ff5f3-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff5f3-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff5f3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ff5f3-119">Element</span><span class="sxs-lookup"><span data-stu-id="ff5f3-119">Element</span></span>|<span data-ttu-id="ff5f3-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff5f3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff5f3-121">\<PolicyImporters ></span><span class="sxs-lookup"><span data-stu-id="ff5f3-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="ff5f3-122">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="ff5f3-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff5f3-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff5f3-123">Remarks</span></span>  
 <span data-ttu-id="ff5f3-124">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfunktionen gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Funktionen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff5f3-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff5f3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff5f3-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="ff5f3-126">WCF-Client-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ff5f3-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="ff5f3-127">Clients</span><span class="sxs-lookup"><span data-stu-id="ff5f3-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
