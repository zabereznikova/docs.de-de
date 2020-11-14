---
title: <dateTimeSerialization>-Element
description: In diesem Artikel wird das <dateTimeSerialization>-Element beschrieben, das den Serialisierungsmodus von DateTime-Objekten bestimmt.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 90ae911c8942fef7a9e8238921990b0a52a47ca0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281769"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="1be20-103">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="1be20-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="1be20-104">Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="1be20-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="1be20-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1be20-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1be20-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1be20-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1be20-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1be20-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1be20-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="1be20-108">Attributes</span></span>  
  
|<span data-ttu-id="1be20-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="1be20-109">Attributes</span></span>|<span data-ttu-id="1be20-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1be20-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="1be20-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1be20-111">Optional.</span></span> <span data-ttu-id="1be20-112">Gibt den Serialisierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="1be20-112">Specifies the serialization mode.</span></span> <span data-ttu-id="1be20-113">Legen Sie hierfür einen der <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>-Werte fest.</span><span class="sxs-lookup"><span data-stu-id="1be20-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="1be20-114">Der Standardwert ist **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="1be20-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1be20-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1be20-115">Child Elements</span></span>  
 <span data-ttu-id="1be20-116">Keine</span><span class="sxs-lookup"><span data-stu-id="1be20-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1be20-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1be20-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1be20-118">Element</span><span class="sxs-lookup"><span data-stu-id="1be20-118">Element</span></span>|<span data-ttu-id="1be20-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1be20-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1be20-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="1be20-120">system.xml.serialization</span></span>|<span data-ttu-id="1be20-121">Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="1be20-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1be20-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1be20-122">Remarks</span></span>  

<span data-ttu-id="1be20-123">Wenn diese Eigenschaft auf **Local** festgelegt ist, werden <xref:System.DateTime>-Objekte stets mit der Ortszeit formatiert.</span><span class="sxs-lookup"><span data-stu-id="1be20-123">When this property is set to **Local** , <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="1be20-124">Das heißt, Ortszeitzoneninformationen sind in den serialisierten Daten immer enthalten.</span><span class="sxs-lookup"><span data-stu-id="1be20-124">That is, local time zone information is always included with the serialized data.</span></span>
  
<span data-ttu-id="1be20-125">Wenn diese Eigenschaft auf **Roundtrip** festgelegt ist, werden <xref:System.DateTime>-Objekte überprüft, um zu bestimmen, ob sie sich in der lokalen, UTC- oder einer nicht angegebenen Zeitzone befinden.</span><span class="sxs-lookup"><span data-stu-id="1be20-125">When this property is set to **Roundtrip** , <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="1be20-126">Die <xref:System.DateTime>-Objekte werden dann so serialisiert, dass diese Informationen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="1be20-126">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="1be20-127">Dies ist das Standardverhalten, das für alle neuen Anwendungen empfohlen wird, die nicht mit älteren Versionen des Framework kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="1be20-127">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be20-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1be20-128">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="1be20-129">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="1be20-129">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="1be20-130">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="1be20-130">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="1be20-131">\<add>-Element für \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="1be20-131">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="1be20-132">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="1be20-132">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
