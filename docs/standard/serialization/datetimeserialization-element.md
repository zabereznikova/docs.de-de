---
title: <dateTimeSerialization>-Element
description: In diesem Artikel wird das <dateTimeSerialization>-Element beschrieben, das den Serialisierungsmodus von DateTime-Objekten bestimmt.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 652a88e25f59cd905e47ef71351e47e67f375286
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375823"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="eb7dd-103">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="eb7dd-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="eb7dd-104">Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="eb7dd-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="eb7dd-105">\<configuration></span></span>  
<span data-ttu-id="eb7dd-106">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="eb7dd-106">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb7dd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb7dd-107">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb7dd-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb7dd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eb7dd-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb7dd-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb7dd-110">Attributes</span></span>  
  
|<span data-ttu-id="eb7dd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb7dd-111">Attributes</span></span>|<span data-ttu-id="eb7dd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb7dd-112">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="eb7dd-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-113">Optional.</span></span> <span data-ttu-id="eb7dd-114">Gibt den Serialisierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-114">Specifies the serialization mode.</span></span> <span data-ttu-id="eb7dd-115">Legen Sie hierfür einen der <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>-Werte fest.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-115">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="eb7dd-116">Der Standardwert ist **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-116">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb7dd-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb7dd-117">Child Elements</span></span>  
 <span data-ttu-id="eb7dd-118">Keine</span><span class="sxs-lookup"><span data-stu-id="eb7dd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb7dd-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb7dd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="eb7dd-120">Element</span><span class="sxs-lookup"><span data-stu-id="eb7dd-120">Element</span></span>|<span data-ttu-id="eb7dd-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb7dd-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb7dd-122">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="eb7dd-122">system.xml.serialization</span></span>|<span data-ttu-id="eb7dd-123">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-123">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb7dd-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb7dd-124">Remarks</span></span>  
 <span data-ttu-id="eb7dd-125">Wenn in den Versionen 1.0, 1.1, 2.0 und höheren Versionen von .NET Framework diese Eigenschaft auf **Local** festgelegt ist, werden <xref:System.DateTime>-Objekte immer entsprechend der Ortszeit formatiert.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-125">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="eb7dd-126">Das heißt, Ortszeitzoneninformationen sind in den serialisierten Daten immer enthalten.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-126">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="eb7dd-127">Legen Sie diese Eigenschaft auf **Local** fest, um die Kompatibilität mit früheren Versionen von .NET Framework sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-127">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="eb7dd-128">Wenn diese Eigenschaft in .NET Framework Version 2.0 und höher auf **Roundtrip** festgelegt ist, werden <xref:System.DateTime>-Objekte überprüft, um zu ermitteln, ob sie entsprechend einer lokalen Zeitzone, der UTC-Zone oder einer unbestimmten Zeitzone formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-128">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="eb7dd-129">Die <xref:System.DateTime>-Objekte werden dann so serialisiert, dass diese Informationen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-129">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="eb7dd-130">Dies ist das Standardverhalten, das für alle neuen Anwendungen empfohlen wird, die nicht mit älteren Versionen des Framework kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="eb7dd-130">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb7dd-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb7dd-131">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="eb7dd-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="eb7dd-132">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="eb7dd-133">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="eb7dd-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="eb7dd-134">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="eb7dd-134">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="eb7dd-135">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="eb7dd-135">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
