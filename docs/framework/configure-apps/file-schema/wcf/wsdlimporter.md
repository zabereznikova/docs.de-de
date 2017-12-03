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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f4fe6c82d0a6f53dfa05a82622e0412280212cc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="0ff70-102">&lt;wsdllImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="0ff70-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="0ff70-103">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ff70-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="0ff70-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0ff70-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0ff70-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="0ff70-105">\<client></span></span>  
<span data-ttu-id="0ff70-106">\<Metadaten ></span><span class="sxs-lookup"><span data-stu-id="0ff70-106">\<metadata></span></span>  
<span data-ttu-id="0ff70-107">\<WsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="0ff70-107">\<wsdlImporters></span></span>  
<span data-ttu-id="0ff70-108">\<wsdllImporter ></span><span class="sxs-lookup"><span data-stu-id="0ff70-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ff70-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ff70-109">Syntax</span></span>  
  
```xml  
<metadata>  
  <wsdlImporters>  
    <wsdlImporter type="string" />  
  </wsdlImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ff70-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0ff70-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0ff70-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ff70-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ff70-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ff70-112">Attributes</span></span>  
  
|<span data-ttu-id="0ff70-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0ff70-113">Attribute</span></span>|<span data-ttu-id="0ff70-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ff70-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0ff70-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="0ff70-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ff70-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ff70-116">Child Elements</span></span>  
 <span data-ttu-id="0ff70-117">Keine</span><span class="sxs-lookup"><span data-stu-id="0ff70-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ff70-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ff70-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0ff70-119">Element</span><span class="sxs-lookup"><span data-stu-id="0ff70-119">Element</span></span>|<span data-ttu-id="0ff70-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ff70-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ff70-121">\<WsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="0ff70-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="0ff70-122">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ff70-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ff70-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ff70-123">Remarks</span></span>  
 <span data-ttu-id="0ff70-124">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="0ff70-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="0ff70-125">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ff70-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="0ff70-126">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0ff70-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ff70-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ff70-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="0ff70-128">WCF-Client-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0ff70-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="0ff70-129">Clients</span><span class="sxs-lookup"><span data-stu-id="0ff70-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
