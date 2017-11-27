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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 99bb7c6be02bad85792dfce9de1f6ef8ba1dcd17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="e2cb6-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="e2cb6-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="e2cb6-103">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="e2cb6-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e2cb6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2cb6-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="e2cb6-105">\<client></span></span>  
<span data-ttu-id="e2cb6-106">\<Metadaten ></span><span class="sxs-lookup"><span data-stu-id="e2cb6-106">\<metadata></span></span>  
<span data-ttu-id="e2cb6-107">\<PolicyImporters ></span><span class="sxs-lookup"><span data-stu-id="e2cb6-107">\<policyImporters></span></span>  
<span data-ttu-id="e2cb6-108">\<PolicyImporter ></span><span class="sxs-lookup"><span data-stu-id="e2cb6-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2cb6-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2cb6-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2cb6-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e2cb6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e2cb6-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2cb6-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e2cb6-112">Attributes</span></span>  
  
|<span data-ttu-id="e2cb6-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e2cb6-113">Attribute</span></span>|<span data-ttu-id="e2cb6-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2cb6-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e2cb6-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2cb6-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2cb6-116">Child Elements</span></span>  
 <span data-ttu-id="e2cb6-117">Keine</span><span class="sxs-lookup"><span data-stu-id="e2cb6-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2cb6-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2cb6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e2cb6-119">Element</span><span class="sxs-lookup"><span data-stu-id="e2cb6-119">Element</span></span>|<span data-ttu-id="e2cb6-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2cb6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2cb6-121">\<PolicyImporters ></span><span class="sxs-lookup"><span data-stu-id="e2cb6-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="e2cb6-122">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2cb6-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2cb6-123">Remarks</span></span>  
 <span data-ttu-id="e2cb6-124">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfunktionen gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Funktionen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2cb6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2cb6-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="e2cb6-126">WCF-Client-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e2cb6-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="e2cb6-127">Clients</span><span class="sxs-lookup"><span data-stu-id="e2cb6-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
