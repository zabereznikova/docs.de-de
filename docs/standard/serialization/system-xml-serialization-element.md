---
title: <system.xml.serialization>-Element
description: In diesem Artikel wird das <system.xml.serialization>-Element beschrieben, das Element der obersten Ebene zum Steuern der XML-Serialisierung.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 6291799aadc429e943996f2256d773ac36dd370f
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282388"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="1819e-103">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="1819e-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="1819e-104">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1819e-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="1819e-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="1819e-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a><span data-ttu-id="1819e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1819e-106">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1819e-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1819e-107">Attributes and Elements</span></span>

<span data-ttu-id="1819e-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1819e-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1819e-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="1819e-109">Attributes</span></span>

<span data-ttu-id="1819e-110">Keine</span><span class="sxs-lookup"><span data-stu-id="1819e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1819e-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1819e-111">Child Elements</span></span>

|<span data-ttu-id="1819e-112">Element</span><span class="sxs-lookup"><span data-stu-id="1819e-112">Element</span></span>|<span data-ttu-id="1819e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1819e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1819e-114">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="1819e-114">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)|<span data-ttu-id="1819e-115">Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="1819e-115">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="1819e-116">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="1819e-116">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)|<span data-ttu-id="1819e-117">Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1819e-117">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1819e-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1819e-118">Parent Elements</span></span>

|<span data-ttu-id="1819e-119">Element</span><span class="sxs-lookup"><span data-stu-id="1819e-119">Element</span></span>|<span data-ttu-id="1819e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1819e-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1819e-121">\<configuration>-Element</span><span class="sxs-lookup"><span data-stu-id="1819e-121">\<configuration> Element</span></span>](../../framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="1819e-122">Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1819e-122">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="1819e-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1819e-123">Example</span></span>

<span data-ttu-id="1819e-124">Das folgende Codebeispiel veranschaulicht, wie der Serialisierungsmodus eines <xref:System.DateTime>-Objekts und das Hinzufügen von Typen, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, beim Zuordnen von XSD-Typen zu .NET-Typen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1819e-124">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1819e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1819e-125">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="1819e-126">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="1819e-126">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="1819e-127">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="1819e-127">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="1819e-128">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="1819e-128">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="1819e-129">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="1819e-129">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
