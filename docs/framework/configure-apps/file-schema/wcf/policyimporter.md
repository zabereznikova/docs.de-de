---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855060"
---
# \<policyImporter>
<span data-ttu-id="a723d-101">Gibt einen Richtlinienimporter an, der den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuert.</span><span class="sxs-lookup"><span data-stu-id="a723d-101">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="a723d-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="a723d-102">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a723d-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a723d-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a723d-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a723d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a723d-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="a723d-105">Attributes</span></span>  
  
|<span data-ttu-id="a723d-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a723d-106">Attribute</span></span>|<span data-ttu-id="a723d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a723d-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="a723d-108">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="a723d-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a723d-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a723d-109">Child Elements</span></span>  
 <span data-ttu-id="a723d-110">Keine</span><span class="sxs-lookup"><span data-stu-id="a723d-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a723d-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a723d-111">Parent Elements</span></span>  
  
|<span data-ttu-id="a723d-112">Element</span><span class="sxs-lookup"><span data-stu-id="a723d-112">Element</span></span>|<span data-ttu-id="a723d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a723d-113">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="a723d-114">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="a723d-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a723d-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a723d-115">Remarks</span></span>  
 <span data-ttu-id="a723d-116">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfeatures gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Features implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a723d-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a723d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a723d-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="a723d-118">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a723d-118">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="a723d-119">Clients</span><span class="sxs-lookup"><span data-stu-id="a723d-119">Clients</span></span>](../../../wcf/feature-details/clients.md)
