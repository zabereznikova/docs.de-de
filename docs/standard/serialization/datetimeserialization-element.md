---
title: '&lt;dateTimeSerialization&gt;-Element'
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: cd275cdbc51c86b1d774058db839c38349b319a6
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078388"
---
# <a name="ltdatetimeserializationgt-element"></a><span data-ttu-id="3e503-102">&lt;dateTimeSerialization&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="3e503-102">&lt;dateTimeSerialization&gt; Element</span></span>
<span data-ttu-id="3e503-103">Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="3e503-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="3e503-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3e503-104">\<configuration></span></span>  
<span data-ttu-id="3e503-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="3e503-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e503-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e503-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e503-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3e503-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3e503-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3e503-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e503-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="3e503-109">Attributes</span></span>  
  
|<span data-ttu-id="3e503-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3e503-110">Attributes</span></span>|<span data-ttu-id="3e503-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e503-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="3e503-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3e503-112">Optional.</span></span> <span data-ttu-id="3e503-113">Gibt den Serialisierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="3e503-113">Specifies the serialization mode.</span></span> <span data-ttu-id="3e503-114">Legen Sie hierfür einen der <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>-Werte fest.</span><span class="sxs-lookup"><span data-stu-id="3e503-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="3e503-115">Der Standardwert ist **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="3e503-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e503-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e503-116">Child Elements</span></span>  
 <span data-ttu-id="3e503-117">Keine</span><span class="sxs-lookup"><span data-stu-id="3e503-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e503-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e503-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3e503-119">Element</span><span class="sxs-lookup"><span data-stu-id="3e503-119">Element</span></span>|<span data-ttu-id="3e503-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e503-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e503-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="3e503-121">system.xml.serialization</span></span>|<span data-ttu-id="3e503-122">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="3e503-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e503-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e503-123">Remarks</span></span>  
 <span data-ttu-id="3e503-124">Wenn in den Versionen 1.0, 1.1, 2.0 und höheren Versionen von .NET Framework diese Eigenschaft auf **Local** festgelegt ist, werden <xref:System.DateTime>-Objekte immer entsprechend der Ortszeit formatiert.</span><span class="sxs-lookup"><span data-stu-id="3e503-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="3e503-125">Das heißt, Ortszeitzoneninformationen sind in den serialisierten Daten immer enthalten.</span><span class="sxs-lookup"><span data-stu-id="3e503-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="3e503-126">Legen Sie diese Eigenschaft auf **Local** fest, um die Kompatibilität mit früheren Versionen von .NET Framework sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="3e503-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="3e503-127">Wenn diese Eigenschaft in .NET Framework Version 2.0 und höher auf **Roundtrip** festgelegt ist, werden <xref:System.DateTime>-Objekte überprüft, um zu ermitteln, ob sie entsprechend einer lokalen Zeitzone, der UTC-Zone oder einer unbestimmten Zeitzone formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="3e503-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="3e503-128">Die <xref:System.DateTime>-Objekte werden dann so serialisiert, dass diese Informationen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="3e503-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="3e503-129">Dies ist das Standardverhalten, das für alle neuen Anwendungen empfohlen wird, die nicht mit älteren Versionen des Framework kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="3e503-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e503-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e503-130">See also</span></span>

- <xref:System.DateTime>  
- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="3e503-131">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="3e503-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="3e503-132">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="3e503-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
- [<span data-ttu-id="3e503-133">\<Hinzufügen >-Element für \<SchemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="3e503-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
- [<span data-ttu-id="3e503-134">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="3e503-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
