---
title: <schemaImporterExtensions>-Element
description: Das <schemaImporterExtensions>-Element enthält Typen, mit denen XmlSchemaImporter XSD-Typen .NET Framework-Typen zuordnet.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 5b9820ccdf2c75bed9beda72358c4c4d82ff9ff7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379789"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="616da-103">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="616da-103">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="616da-104">Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="616da-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="616da-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="616da-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="616da-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="616da-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="616da-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="616da-107">Child Elements</span></span>  
  
|<span data-ttu-id="616da-108">Element</span><span class="sxs-lookup"><span data-stu-id="616da-108">Element</span></span>|<span data-ttu-id="616da-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="616da-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="616da-110">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="616da-110">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="616da-111">Fügt Typen hinzu, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden, um Zuordnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="616da-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="616da-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="616da-112">Parent Elements</span></span>  
  
|<span data-ttu-id="616da-113">Element</span><span class="sxs-lookup"><span data-stu-id="616da-113">Element</span></span>|<span data-ttu-id="616da-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="616da-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="616da-115">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="616da-115">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="616da-116">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="616da-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="616da-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="616da-117">Example</span></span>  
 <span data-ttu-id="616da-118">Das folgende Codebeispiel veranschaulicht, wie Typen hinzugefügt werden, die von <xref:System.Xml.Serialization.XmlSchemaImporter> beim Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="616da-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="616da-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="616da-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="616da-120">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="616da-120">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="616da-121">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="616da-121">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="616da-122">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="616da-122">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="616da-123">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="616da-123">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
