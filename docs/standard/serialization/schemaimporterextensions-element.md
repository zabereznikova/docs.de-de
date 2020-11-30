---
title: <schemaImporterExtensions>-Element
description: Das <schemaImporterExtensions>-Element enthält Typen, mit denen XmlSchemaImporter XSD-Typen .NET-Typen zuordnet.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 6b644ed1112b748be4dd301d6fa6f2a6416dc67e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722140"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="8e232-103">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="8e232-103">\<schemaImporterExtensions> element</span></span>

<span data-ttu-id="8e232-104">Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e232-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET types.</span></span> <span data-ttu-id="8e232-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="8e232-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e232-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e232-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="8e232-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e232-107">Child Elements</span></span>  
  
|<span data-ttu-id="8e232-108">Element</span><span class="sxs-lookup"><span data-stu-id="8e232-108">Element</span></span>|<span data-ttu-id="8e232-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e232-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e232-110">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="8e232-110">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)|<span data-ttu-id="8e232-111">Fügt Typen hinzu, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden, um Zuordnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8e232-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="8e232-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e232-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8e232-113">Element</span><span class="sxs-lookup"><span data-stu-id="8e232-113">Element</span></span>|<span data-ttu-id="8e232-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e232-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e232-115">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="8e232-115">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="8e232-116">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="8e232-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8e232-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e232-117">Example</span></span>  

 <span data-ttu-id="8e232-118">Das folgende Codebeispiel veranschaulicht, wie Typen hinzugefügt werden, die von <xref:System.Xml.Serialization.XmlSchemaImporter> beim Zuordnen von XSD-Typen zu .NET-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e232-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8e232-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e232-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="8e232-120">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="8e232-120">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="8e232-121">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="8e232-121">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="8e232-122">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="8e232-122">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="8e232-123">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="8e232-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
