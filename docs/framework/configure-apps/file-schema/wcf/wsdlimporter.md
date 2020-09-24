---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 82704aa40b508f1b1e2237c9768a7b7599c5c87e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158590"
---
# \<wsdlImporter>

<span data-ttu-id="159df-101">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="159df-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="159df-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="159df-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="159df-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="159df-103">Attributes and Elements</span></span>  

 <span data-ttu-id="159df-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="159df-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="159df-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="159df-105">Attributes</span></span>  
  
|<span data-ttu-id="159df-106">attribute</span><span class="sxs-lookup"><span data-stu-id="159df-106">Attribute</span></span>|<span data-ttu-id="159df-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="159df-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="159df-108">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="159df-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="159df-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="159df-109">Child Elements</span></span>  

 <span data-ttu-id="159df-110">Keine</span><span class="sxs-lookup"><span data-stu-id="159df-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="159df-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="159df-111">Parent Elements</span></span>  
  
|<span data-ttu-id="159df-112">Element</span><span class="sxs-lookup"><span data-stu-id="159df-112">Element</span></span>|<span data-ttu-id="159df-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="159df-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="159df-114">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="159df-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="159df-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="159df-115">Remarks</span></span>  

 <span data-ttu-id="159df-116">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="159df-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="159df-117">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="159df-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="159df-118">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="159df-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159df-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="159df-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="159df-120">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="159df-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="159df-121">Clients</span><span class="sxs-lookup"><span data-stu-id="159df-121">Clients</span></span>](../../../wcf/feature-details/clients.md)
