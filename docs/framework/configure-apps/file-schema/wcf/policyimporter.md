---
title: '&lt;policyImporter&gt;'
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4075f7fcb1c65da3d9e2e5e5dab52452ca2c9b60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632165"
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="6f959-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="6f959-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="6f959-103">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="6f959-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="6f959-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6f959-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6f959-105">\<client></span><span class="sxs-lookup"><span data-stu-id="6f959-105">\<client></span></span>  
<span data-ttu-id="6f959-106">\<metadata></span><span class="sxs-lookup"><span data-stu-id="6f959-106">\<metadata></span></span>  
<span data-ttu-id="6f959-107">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="6f959-107">\<policyImporters></span></span>  
<span data-ttu-id="6f959-108">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="6f959-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f959-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f959-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f959-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6f959-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6f959-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6f959-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f959-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6f959-112">Attributes</span></span>  
  
|<span data-ttu-id="6f959-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6f959-113">Attribute</span></span>|<span data-ttu-id="6f959-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f959-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6f959-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="6f959-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f959-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f959-116">Child Elements</span></span>  
 <span data-ttu-id="6f959-117">Keine</span><span class="sxs-lookup"><span data-stu-id="6f959-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f959-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f959-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6f959-119">Element</span><span class="sxs-lookup"><span data-stu-id="6f959-119">Element</span></span>|<span data-ttu-id="6f959-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f959-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f959-121">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="6f959-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="6f959-122">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="6f959-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f959-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f959-123">Remarks</span></span>  
 <span data-ttu-id="6f959-124">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfunktionen gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Funktionen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f959-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f959-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f959-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="6f959-126">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="6f959-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="6f959-127">Clients</span><span class="sxs-lookup"><span data-stu-id="6f959-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
