---
title: '&lt;wsdllImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3b3eaa4e4a229000bb0e2412adee541f4d59484
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="25402-102">&lt;wsdllImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="25402-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="25402-103">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="25402-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="25402-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="25402-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="25402-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="25402-105">\<client></span></span>  
<span data-ttu-id="25402-106">\<Metadaten ></span><span class="sxs-lookup"><span data-stu-id="25402-106">\<metadata></span></span>  
<span data-ttu-id="25402-107">\<WsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="25402-107">\<wsdlImporters></span></span>  
<span data-ttu-id="25402-108">\<wsdllImporter ></span><span class="sxs-lookup"><span data-stu-id="25402-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25402-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="25402-109">Syntax</span></span>  
  
```xml  
<metadata>  
  <wsdlImporters>  
    <wsdlImporter type="string" />  
  </wsdlImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25402-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="25402-110">Attributes and Elements</span></span>  
 <span data-ttu-id="25402-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25402-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25402-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="25402-112">Attributes</span></span>  
  
|<span data-ttu-id="25402-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="25402-113">Attribute</span></span>|<span data-ttu-id="25402-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25402-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="25402-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="25402-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25402-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25402-116">Child Elements</span></span>  
 <span data-ttu-id="25402-117">Keine</span><span class="sxs-lookup"><span data-stu-id="25402-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25402-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25402-118">Parent Elements</span></span>  
  
|<span data-ttu-id="25402-119">Element</span><span class="sxs-lookup"><span data-stu-id="25402-119">Element</span></span>|<span data-ttu-id="25402-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25402-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25402-121">\<WsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="25402-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="25402-122">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="25402-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25402-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25402-123">Remarks</span></span>  
 <span data-ttu-id="25402-124">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="25402-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="25402-125">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="25402-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="25402-126">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="25402-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25402-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25402-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="25402-128">WCF-Client-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="25402-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="25402-129">Clients</span><span class="sxs-lookup"><span data-stu-id="25402-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
