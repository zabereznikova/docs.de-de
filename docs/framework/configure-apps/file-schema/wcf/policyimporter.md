---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: ab9193d5974ccffcbfa3e741ac4d32ff357ed372
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269236"
---
# <a name="policyimporter"></a><span data-ttu-id="3540f-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="3540f-101">\<policyImporter></span></span>
<span data-ttu-id="3540f-102">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="3540f-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="3540f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3540f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3540f-104">\<client></span><span class="sxs-lookup"><span data-stu-id="3540f-104">\<client></span></span>  
<span data-ttu-id="3540f-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="3540f-105">\<metadata></span></span>  
<span data-ttu-id="3540f-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="3540f-106">\<policyImporters></span></span>  
<span data-ttu-id="3540f-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="3540f-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3540f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3540f-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3540f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3540f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3540f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3540f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3540f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="3540f-111">Attributes</span></span>  
  
|<span data-ttu-id="3540f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="3540f-112">Attribute</span></span>|<span data-ttu-id="3540f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3540f-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3540f-114">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="3540f-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3540f-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3540f-115">Child Elements</span></span>  
 <span data-ttu-id="3540f-116">Keine</span><span class="sxs-lookup"><span data-stu-id="3540f-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3540f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3540f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3540f-118">Element</span><span class="sxs-lookup"><span data-stu-id="3540f-118">Element</span></span>|<span data-ttu-id="3540f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3540f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3540f-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="3540f-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="3540f-121">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="3540f-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3540f-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3540f-122">Remarks</span></span>  
 <span data-ttu-id="3540f-123">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfunktionen gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Funktionen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="3540f-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3540f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3540f-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="3540f-125">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="3540f-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="3540f-126">Clients</span><span class="sxs-lookup"><span data-stu-id="3540f-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
