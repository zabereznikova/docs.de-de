---
title: <dateTimeSerialization>-Element
description: In diesem Artikel wird das <dateTimeSerialization>-Element beschrieben, das den Serialisierungsmodus von DateTime-Objekten bestimmt.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: a2684ab72c1fb109d711e333e01836d3399caf86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289641"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="e1957-103">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="e1957-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="e1957-104">Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="e1957-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="e1957-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1957-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1957-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1957-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e1957-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1957-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1957-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1957-108">Attributes</span></span>  
  
|<span data-ttu-id="e1957-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1957-109">Attributes</span></span>|<span data-ttu-id="e1957-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1957-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="e1957-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e1957-111">Optional.</span></span> <span data-ttu-id="e1957-112">Gibt den Serialisierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="e1957-112">Specifies the serialization mode.</span></span> <span data-ttu-id="e1957-113">Legen Sie hierfür einen der <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>-Werte fest.</span><span class="sxs-lookup"><span data-stu-id="e1957-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="e1957-114">Der Standardwert ist **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="e1957-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1957-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1957-115">Child Elements</span></span>  
 <span data-ttu-id="e1957-116">Keine</span><span class="sxs-lookup"><span data-stu-id="e1957-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1957-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1957-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e1957-118">Element</span><span class="sxs-lookup"><span data-stu-id="e1957-118">Element</span></span>|<span data-ttu-id="e1957-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1957-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1957-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="e1957-120">system.xml.serialization</span></span>|<span data-ttu-id="e1957-121">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="e1957-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1957-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1957-122">Remarks</span></span>  
 <span data-ttu-id="e1957-123">Wenn in den Versionen 1.0, 1.1, 2.0 und höheren Versionen von .NET Framework diese Eigenschaft auf **Local** festgelegt ist, werden <xref:System.DateTime>-Objekte immer entsprechend der Ortszeit formatiert.</span><span class="sxs-lookup"><span data-stu-id="e1957-123">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="e1957-124">Das heißt, Ortszeitzoneninformationen sind in den serialisierten Daten immer enthalten.</span><span class="sxs-lookup"><span data-stu-id="e1957-124">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="e1957-125">Legen Sie diese Eigenschaft auf **Local** fest, um die Kompatibilität mit früheren Versionen von .NET Framework sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e1957-125">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e1957-126">Wenn diese Eigenschaft in .NET Framework Version 2.0 und höher auf **Roundtrip** festgelegt ist, werden <xref:System.DateTime>-Objekte überprüft, um zu ermitteln, ob sie entsprechend einer lokalen Zeitzone, der UTC-Zone oder einer unbestimmten Zeitzone formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="e1957-126">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="e1957-127">Die <xref:System.DateTime>-Objekte werden dann so serialisiert, dass diese Informationen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="e1957-127">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="e1957-128">Dies ist das Standardverhalten, das für alle neuen Anwendungen empfohlen wird, die nicht mit älteren Versionen des Framework kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e1957-128">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1957-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1957-129">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="e1957-130">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e1957-130">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e1957-131">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="e1957-131">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="e1957-132">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="e1957-132">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="e1957-133">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="e1957-133">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
