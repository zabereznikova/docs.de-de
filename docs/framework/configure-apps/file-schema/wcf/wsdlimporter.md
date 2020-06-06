---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854757"
---
# \<wsdlImporter>
<span data-ttu-id="6e434-101">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e434-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="6e434-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e434-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e434-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6e434-103">Attributes and Elements</span></span>  
 <span data-ttu-id="6e434-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e434-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e434-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="6e434-105">Attributes</span></span>  
  
|<span data-ttu-id="6e434-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6e434-106">Attribute</span></span>|<span data-ttu-id="6e434-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e434-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6e434-108">Der Typ dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="6e434-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e434-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e434-109">Child Elements</span></span>  
 <span data-ttu-id="6e434-110">Keine</span><span class="sxs-lookup"><span data-stu-id="6e434-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e434-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e434-111">Parent Elements</span></span>  
  
|<span data-ttu-id="6e434-112">Element</span><span class="sxs-lookup"><span data-stu-id="6e434-112">Element</span></span>|<span data-ttu-id="6e434-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e434-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="6e434-114">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e434-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e434-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6e434-115">Remarks</span></span>  
 <span data-ttu-id="6e434-116">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e434-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="6e434-117">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e434-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="6e434-118">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6e434-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e434-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e434-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="6e434-120">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="6e434-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="6e434-121">Clients</span><span class="sxs-lookup"><span data-stu-id="6e434-121">Clients</span></span>](../../../wcf/feature-details/clients.md)
