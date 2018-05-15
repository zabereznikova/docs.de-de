---
title: '&lt;wsdllImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 33c2b0e4286ce746f745e4aebe10fd4bbd96810f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="0837b-102">&lt;wsdllImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="0837b-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="0837b-103">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="0837b-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="0837b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0837b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0837b-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="0837b-105">\<client></span></span>  
<span data-ttu-id="0837b-106">\<Metadaten ></span><span class="sxs-lookup"><span data-stu-id="0837b-106">\<metadata></span></span>  
<span data-ttu-id="0837b-107">\<WsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="0837b-107">\<wsdlImporters></span></span>  
<span data-ttu-id="0837b-108">\<wsdllImporter ></span><span class="sxs-lookup"><span data-stu-id="0837b-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0837b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0837b-109">Syntax</span></span>  
  
```xml  
<metadata>  
  <wsdlImporters>  
    <wsdlImporter type="string" />  
  </wsdlImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0837b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0837b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0837b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0837b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0837b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0837b-112">Attributes</span></span>  
  
|<span data-ttu-id="0837b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0837b-113">Attribute</span></span>|<span data-ttu-id="0837b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0837b-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0837b-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="0837b-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0837b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0837b-116">Child Elements</span></span>  
 <span data-ttu-id="0837b-117">Keine</span><span class="sxs-lookup"><span data-stu-id="0837b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0837b-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0837b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0837b-119">Element</span><span class="sxs-lookup"><span data-stu-id="0837b-119">Element</span></span>|<span data-ttu-id="0837b-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0837b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0837b-121">\<WsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="0837b-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="0837b-122">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="0837b-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0837b-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0837b-123">Remarks</span></span>  
 <span data-ttu-id="0837b-124">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="0837b-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="0837b-125">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="0837b-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="0837b-126">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0837b-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0837b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0837b-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="0837b-128">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="0837b-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="0837b-129">Clients</span><span class="sxs-lookup"><span data-stu-id="0837b-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
