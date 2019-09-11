---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855060"
---
# <a name="policyimporter"></a><span data-ttu-id="8fb9d-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="8fb9d-101">\<policyImporter></span></span>
<span data-ttu-id="8fb9d-102">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="8fb9d-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
<span data-ttu-id="8fb9d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8fb9d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8fb9d-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8fb9d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8fb9d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="8fb9d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="8fb9d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Metadaten>** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="8fb9d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="8fb9d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<policyimport->** ](policyimporters.md)</span><span class="sxs-lookup"><span data-stu-id="8fb9d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)</span></span>  
<span data-ttu-id="8fb9d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<policyimport->**</span><span class="sxs-lookup"><span data-stu-id="8fb9d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fb9d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fb9d-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fb9d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8fb9d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8fb9d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8fb9d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fb9d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8fb9d-112">Attributes</span></span>  
  
|<span data-ttu-id="8fb9d-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="8fb9d-113">Attribute</span></span>|<span data-ttu-id="8fb9d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fb9d-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="8fb9d-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="8fb9d-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fb9d-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fb9d-116">Child Elements</span></span>  
 <span data-ttu-id="8fb9d-117">None</span><span class="sxs-lookup"><span data-stu-id="8fb9d-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fb9d-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fb9d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8fb9d-119">Element</span><span class="sxs-lookup"><span data-stu-id="8fb9d-119">Element</span></span>|<span data-ttu-id="8fb9d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fb9d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fb9d-121">\<policyimport-></span><span class="sxs-lookup"><span data-stu-id="8fb9d-121">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="8fb9d-122">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="8fb9d-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fb9d-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8fb9d-123">Remarks</span></span>  
 <span data-ttu-id="8fb9d-124">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfeatures gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Features implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="8fb9d-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb9d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fb9d-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="8fb9d-126">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="8fb9d-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="8fb9d-127">Clients</span><span class="sxs-lookup"><span data-stu-id="8fb9d-127">Clients</span></span>](../../../wcf/feature-details/clients.md)
