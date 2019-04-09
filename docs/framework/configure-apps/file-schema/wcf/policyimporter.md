---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094176"
---
# <a name="policyimporter"></a><span data-ttu-id="15c0c-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="15c0c-101">\<policyImporter></span></span>
<span data-ttu-id="15c0c-102">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="15c0c-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="15c0c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="15c0c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="15c0c-104">\<client></span><span class="sxs-lookup"><span data-stu-id="15c0c-104">\<client></span></span>  
<span data-ttu-id="15c0c-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="15c0c-105">\<metadata></span></span>  
<span data-ttu-id="15c0c-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="15c0c-106">\<policyImporters></span></span>  
<span data-ttu-id="15c0c-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="15c0c-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c0c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="15c0c-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15c0c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15c0c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="15c0c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15c0c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15c0c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="15c0c-111">Attributes</span></span>  
  
|<span data-ttu-id="15c0c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="15c0c-112">Attribute</span></span>|<span data-ttu-id="15c0c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15c0c-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="15c0c-114">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="15c0c-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15c0c-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15c0c-115">Child Elements</span></span>  
 <span data-ttu-id="15c0c-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="15c0c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15c0c-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15c0c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="15c0c-118">Element</span><span class="sxs-lookup"><span data-stu-id="15c0c-118">Element</span></span>|<span data-ttu-id="15c0c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15c0c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15c0c-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="15c0c-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="15c0c-121">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="15c0c-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15c0c-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15c0c-122">Remarks</span></span>  
 <span data-ttu-id="15c0c-123">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfeatures gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Features implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="15c0c-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c0c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15c0c-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="15c0c-125">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="15c0c-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="15c0c-126">Clients</span><span class="sxs-lookup"><span data-stu-id="15c0c-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
