---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854757"
---
# <a name="wsdlimporter"></a><span data-ttu-id="71768-101">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="71768-101">\<wsdlImporter></span></span>
<span data-ttu-id="71768-102">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="71768-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="71768-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="71768-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="71768-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="71768-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="71768-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="71768-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="71768-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Metadaten>** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="71768-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="71768-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsdlimporters->** ](wsdlimporters.md)</span><span class="sxs-lookup"><span data-stu-id="71768-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)</span></span>  
<span data-ttu-id="71768-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<WsdlImporter->**</span><span class="sxs-lookup"><span data-stu-id="71768-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71768-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="71768-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71768-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="71768-110">Attributes and Elements</span></span>  
 <span data-ttu-id="71768-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="71768-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71768-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="71768-112">Attributes</span></span>  
  
|<span data-ttu-id="71768-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="71768-113">Attribute</span></span>|<span data-ttu-id="71768-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71768-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="71768-115">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="71768-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71768-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="71768-116">Child Elements</span></span>  
 <span data-ttu-id="71768-117">Keine</span><span class="sxs-lookup"><span data-stu-id="71768-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71768-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="71768-118">Parent Elements</span></span>  
  
|<span data-ttu-id="71768-119">Element</span><span class="sxs-lookup"><span data-stu-id="71768-119">Element</span></span>|<span data-ttu-id="71768-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71768-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71768-121">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="71768-121">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="71768-122">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="71768-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71768-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71768-123">Remarks</span></span>  
 <span data-ttu-id="71768-124">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="71768-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="71768-125">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="71768-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="71768-126">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="71768-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71768-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71768-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="71768-128">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="71768-128">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="71768-129">Clients</span><span class="sxs-lookup"><span data-stu-id="71768-129">Clients</span></span>](../../../wcf/feature-details/clients.md)
