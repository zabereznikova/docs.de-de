---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783181"
---
# <a name="policyimporter"></a><span data-ttu-id="75f2e-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="75f2e-101">\<policyImporter></span></span>
<span data-ttu-id="75f2e-102">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="75f2e-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="75f2e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="75f2e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="75f2e-104">\<client></span><span class="sxs-lookup"><span data-stu-id="75f2e-104">\<client></span></span>  
<span data-ttu-id="75f2e-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="75f2e-105">\<metadata></span></span>  
<span data-ttu-id="75f2e-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="75f2e-106">\<policyImporters></span></span>  
<span data-ttu-id="75f2e-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="75f2e-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f2e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="75f2e-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75f2e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="75f2e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="75f2e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75f2e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75f2e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="75f2e-111">Attributes</span></span>  
  
|<span data-ttu-id="75f2e-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="75f2e-112">Attribute</span></span>|<span data-ttu-id="75f2e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75f2e-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="75f2e-114">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="75f2e-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75f2e-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75f2e-115">Child Elements</span></span>  
 <span data-ttu-id="75f2e-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="75f2e-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75f2e-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75f2e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="75f2e-118">Element</span><span class="sxs-lookup"><span data-stu-id="75f2e-118">Element</span></span>|<span data-ttu-id="75f2e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75f2e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75f2e-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="75f2e-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="75f2e-121">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="75f2e-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75f2e-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75f2e-122">Remarks</span></span>  
 <span data-ttu-id="75f2e-123">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfeatures gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Features implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="75f2e-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f2e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75f2e-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="75f2e-125">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="75f2e-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="75f2e-126">Clients</span><span class="sxs-lookup"><span data-stu-id="75f2e-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
