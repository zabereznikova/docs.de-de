---
title: <system.xml.serialization>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 02027a238bc9a2f82963ea841584d2bb3c6446c6
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410546"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="b10bf-102">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="b10bf-102">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="b10bf-103">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="b10bf-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="b10bf-104">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="b10bf-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="b10bf-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b10bf-105">\<configuration>\</span></span>
<span data-ttu-id="b10bf-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="b10bf-106">\<system.xml.serialization></span></span>

## <a name="syntax"></a><span data-ttu-id="b10bf-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b10bf-107">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b10bf-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b10bf-108">Attributes and Elements</span></span>

<span data-ttu-id="b10bf-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b10bf-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b10bf-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b10bf-110">Attributes</span></span>

<span data-ttu-id="b10bf-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b10bf-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b10bf-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b10bf-112">Child Elements</span></span>

|<span data-ttu-id="b10bf-113">Element</span><span class="sxs-lookup"><span data-stu-id="b10bf-113">Element</span></span>|<span data-ttu-id="b10bf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b10bf-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b10bf-115">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="b10bf-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="b10bf-116">Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="b10bf-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="b10bf-117">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="b10bf-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="b10bf-118">Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b10bf-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b10bf-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b10bf-119">Parent Elements</span></span>

|<span data-ttu-id="b10bf-120">Element</span><span class="sxs-lookup"><span data-stu-id="b10bf-120">Element</span></span>|<span data-ttu-id="b10bf-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b10bf-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b10bf-122">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="b10bf-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="b10bf-123">Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b10bf-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="b10bf-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b10bf-124">Example</span></span>

<span data-ttu-id="b10bf-125">Das folgende Codebeispiel veranschaulicht, wie der Serialisierungsmodus eines <xref:System.DateTime>-Objekts und das Hinzufügen von Typen, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, beim Zuordnen von XSD-Typen zu .NET Framework-Typen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b10bf-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b10bf-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b10bf-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="b10bf-127">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b10bf-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b10bf-128">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="b10bf-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="b10bf-129">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="b10bf-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="b10bf-130">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="b10bf-130">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
