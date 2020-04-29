---
title: <schemaImporterExtensions>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 5ed80ac370e34d6b62bb2b601cb7bd978228a302
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159818"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="21d0a-102">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="21d0a-102">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="21d0a-103">Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21d0a-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="21d0a-104">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="21d0a-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d0a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="21d0a-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="21d0a-106">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21d0a-106">Child Elements</span></span>  
  
|<span data-ttu-id="21d0a-107">Element</span><span class="sxs-lookup"><span data-stu-id="21d0a-107">Element</span></span>|<span data-ttu-id="21d0a-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21d0a-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21d0a-109">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="21d0a-109">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="21d0a-110">Fügt Typen hinzu, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden, um Zuordnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="21d0a-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="21d0a-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21d0a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="21d0a-112">Element</span><span class="sxs-lookup"><span data-stu-id="21d0a-112">Element</span></span>|<span data-ttu-id="21d0a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21d0a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21d0a-114">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="21d0a-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="21d0a-115">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="21d0a-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="21d0a-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21d0a-116">Example</span></span>  
 <span data-ttu-id="21d0a-117">Das folgende Codebeispiel veranschaulicht, wie Typen hinzugefügt werden, die von <xref:System.Xml.Serialization.XmlSchemaImporter> beim Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21d0a-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="21d0a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21d0a-118">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="21d0a-119">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="21d0a-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="21d0a-120">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="21d0a-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="21d0a-121">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="21d0a-121">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="21d0a-122">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="21d0a-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
