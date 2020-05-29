---
title: <system.xml.serialization>-Element
description: In diesem Artikel wird das <system.xml.serialization>-Element beschrieben, das Element der obersten Ebene zum Steuern der XML-Serialisierung.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 1e66220004d561f937d03c506e6f30db4ccc635b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380118"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="fe3ee-103">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="fe3ee-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="fe3ee-104">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="fe3ee-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="fe3ee-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="fe3ee-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="fe3ee-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fe3ee-106">\<configuration>\</span></span>
<span data-ttu-id="fe3ee-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="fe3ee-107">\<system.xml.serialization></span></span>

## <a name="syntax"></a><span data-ttu-id="fe3ee-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe3ee-108">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fe3ee-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe3ee-109">Attributes and Elements</span></span>

<span data-ttu-id="fe3ee-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe3ee-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe3ee-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe3ee-111">Attributes</span></span>

<span data-ttu-id="fe3ee-112">Keine</span><span class="sxs-lookup"><span data-stu-id="fe3ee-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fe3ee-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe3ee-113">Child Elements</span></span>

|<span data-ttu-id="fe3ee-114">Element</span><span class="sxs-lookup"><span data-stu-id="fe3ee-114">Element</span></span>|<span data-ttu-id="fe3ee-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe3ee-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe3ee-116">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="fe3ee-116">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="fe3ee-117">Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="fe3ee-117">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="fe3ee-118">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="fe3ee-118">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="fe3ee-119">Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe3ee-119">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fe3ee-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe3ee-120">Parent Elements</span></span>

|<span data-ttu-id="fe3ee-121">Element</span><span class="sxs-lookup"><span data-stu-id="fe3ee-121">Element</span></span>|<span data-ttu-id="fe3ee-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe3ee-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe3ee-123">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="fe3ee-123">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="fe3ee-124">Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe3ee-124">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="fe3ee-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe3ee-125">Example</span></span>

<span data-ttu-id="fe3ee-126">Das folgende Codebeispiel veranschaulicht, wie der Serialisierungsmodus eines <xref:System.DateTime>-Objekts und das Hinzufügen von Typen, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, beim Zuordnen von XSD-Typen zu .NET Framework-Typen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fe3ee-126">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a><span data-ttu-id="fe3ee-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe3ee-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="fe3ee-128">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="fe3ee-128">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="fe3ee-129">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="fe3ee-129">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="fe3ee-130">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="fe3ee-130">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="fe3ee-131">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="fe3ee-131">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
