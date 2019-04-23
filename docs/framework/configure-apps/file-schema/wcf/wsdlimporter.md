---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 1f34486296465b3ea0b5b05bd9492062c85ad8c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134432"
---
# <a name="wsdlimporter"></a><span data-ttu-id="702eb-101">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="702eb-101">\<wsdlImporter></span></span>
<span data-ttu-id="702eb-102">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="702eb-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="702eb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="702eb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="702eb-104">\<client></span><span class="sxs-lookup"><span data-stu-id="702eb-104">\<client></span></span>  
<span data-ttu-id="702eb-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="702eb-105">\<metadata></span></span>  
<span data-ttu-id="702eb-106">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="702eb-106">\<wsdlImporters></span></span>  
<span data-ttu-id="702eb-107">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="702eb-107">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="702eb-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="702eb-108">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="702eb-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="702eb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="702eb-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="702eb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="702eb-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="702eb-111">Attributes</span></span>  
  
|<span data-ttu-id="702eb-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="702eb-112">Attribute</span></span>|<span data-ttu-id="702eb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="702eb-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="702eb-114">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="702eb-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="702eb-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="702eb-115">Child Elements</span></span>  
 <span data-ttu-id="702eb-116">Keine</span><span class="sxs-lookup"><span data-stu-id="702eb-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="702eb-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="702eb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="702eb-118">Element</span><span class="sxs-lookup"><span data-stu-id="702eb-118">Element</span></span>|<span data-ttu-id="702eb-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="702eb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="702eb-120">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="702eb-120">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="702eb-121">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="702eb-121">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="702eb-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="702eb-122">Remarks</span></span>  
 <span data-ttu-id="702eb-123">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="702eb-123">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="702eb-124">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="702eb-124">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="702eb-125">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="702eb-125">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="702eb-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="702eb-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="702eb-127">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="702eb-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="702eb-128">Clients</span><span class="sxs-lookup"><span data-stu-id="702eb-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
