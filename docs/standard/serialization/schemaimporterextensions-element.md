---
title: <schemaImporterExtensions>-Element
description: Das <schemaImporterExtensions>-Element enthält Typen, mit denen XmlSchemaImporter XSD-Typen .NET Framework-Typen zuordnet.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: c46c5cb6e01463723f0f2ce3873fb4a6ec0b4e60
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84278401"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="87f5b-103">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="87f5b-103">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="87f5b-104">Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87f5b-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="87f5b-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="87f5b-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f5b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="87f5b-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="87f5b-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87f5b-107">Child Elements</span></span>  
  
|<span data-ttu-id="87f5b-108">Element</span><span class="sxs-lookup"><span data-stu-id="87f5b-108">Element</span></span>|<span data-ttu-id="87f5b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87f5b-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87f5b-110">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="87f5b-110">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)|<span data-ttu-id="87f5b-111">Fügt Typen hinzu, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden, um Zuordnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87f5b-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="87f5b-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87f5b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="87f5b-113">Element</span><span class="sxs-lookup"><span data-stu-id="87f5b-113">Element</span></span>|<span data-ttu-id="87f5b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87f5b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87f5b-115">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="87f5b-115">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="87f5b-116">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="87f5b-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="87f5b-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87f5b-117">Example</span></span>  
 <span data-ttu-id="87f5b-118">Das folgende Codebeispiel veranschaulicht, wie Typen hinzugefügt werden, die von <xref:System.Xml.Serialization.XmlSchemaImporter> beim Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87f5b-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87f5b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87f5b-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="87f5b-120">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="87f5b-120">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="87f5b-121">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="87f5b-121">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="87f5b-122">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="87f5b-122">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="87f5b-123">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="87f5b-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
