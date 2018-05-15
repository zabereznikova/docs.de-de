---
title: '&lt;policyImporter&gt;'
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 7483a95accef0a4bc956d919087379363b4762ca
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="66eee-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="66eee-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="66eee-103">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="66eee-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="66eee-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="66eee-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="66eee-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="66eee-105">\<client></span></span>  
<span data-ttu-id="66eee-106">\<Metadaten ></span><span class="sxs-lookup"><span data-stu-id="66eee-106">\<metadata></span></span>  
<span data-ttu-id="66eee-107">\<PolicyImporters ></span><span class="sxs-lookup"><span data-stu-id="66eee-107">\<policyImporters></span></span>  
<span data-ttu-id="66eee-108">\<PolicyImporter ></span><span class="sxs-lookup"><span data-stu-id="66eee-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66eee-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="66eee-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66eee-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="66eee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="66eee-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="66eee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66eee-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="66eee-112">Attributes</span></span>  
  
|<span data-ttu-id="66eee-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="66eee-113">Attribute</span></span>|<span data-ttu-id="66eee-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66eee-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="66eee-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="66eee-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66eee-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66eee-116">Child Elements</span></span>  
 <span data-ttu-id="66eee-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="66eee-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66eee-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66eee-118">Parent Elements</span></span>  
  
|<span data-ttu-id="66eee-119">Element</span><span class="sxs-lookup"><span data-stu-id="66eee-119">Element</span></span>|<span data-ttu-id="66eee-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66eee-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66eee-121">\<PolicyImporters ></span><span class="sxs-lookup"><span data-stu-id="66eee-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="66eee-122">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="66eee-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66eee-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66eee-123">Remarks</span></span>  
 <span data-ttu-id="66eee-124">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfunktionen gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Funktionen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="66eee-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66eee-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66eee-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="66eee-126">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="66eee-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="66eee-127">Clients</span><span class="sxs-lookup"><span data-stu-id="66eee-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
