---
title: <xmlSerializer>-Element
description: Das <xmlSerializer>-Element gibt an, ob eine zusätzliche Zustandsüberprüfung für den XmlSerializer durchgeführt wird.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 68037959893ec307a896ea86d21e40a9d7aa824c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380024"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="4fd3c-103">\<xmlSerializer>-Element</span><span class="sxs-lookup"><span data-stu-id="4fd3c-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="4fd3c-104">Gibt an, ob eine zusätzliche Zustandsüberprüfung für <xref:System.Xml.Serialization.XmlSerializer> durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="4fd3c-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4fd3c-105">\<configuration></span></span>  
<span data-ttu-id="4fd3c-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="4fd3c-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fd3c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fd3c-107">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fd3c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4fd3c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4fd3c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fd3c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4fd3c-110">Attributes</span></span>  
  
|<span data-ttu-id="4fd3c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4fd3c-111">Attribute</span></span>|<span data-ttu-id="4fd3c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4fd3c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4fd3c-113">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="4fd3c-113">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="4fd3c-114">Gibt an, ob der Zustand von <xref:System.Xml.Serialization.XmlSerializer> überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-114">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="4fd3c-115">Legen Sie das Attribut auf "true" oder "false" fest.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-115">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="4fd3c-116">Der Standardwert ist "true".</span><span class="sxs-lookup"><span data-stu-id="4fd3c-116">The default is "true".</span></span>|  
|<span data-ttu-id="4fd3c-117">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="4fd3c-117">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="4fd3c-118">Gibt an, ob <xref:System.Xml.Serialization.XmlSerializer> eine Vorgänger-Serialisierungsgenerierung verwendet, die Assemblys generiert, indem C#-Code in eine Datei geschrieben und anschließend in eine Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-118">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="4fd3c-119">Der Standardwert ist **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-119">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fd3c-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4fd3c-120">Child Elements</span></span>  
 <span data-ttu-id="4fd3c-121">Keine</span><span class="sxs-lookup"><span data-stu-id="4fd3c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4fd3c-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4fd3c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4fd3c-123">Element</span><span class="sxs-lookup"><span data-stu-id="4fd3c-123">Element</span></span>|<span data-ttu-id="4fd3c-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4fd3c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fd3c-125">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="4fd3c-125">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="4fd3c-126">Enthält Konfigurationseinstellungen für die <xref:System.Xml.Serialization.XmlSerializer>-Klasse und die <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-126">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fd3c-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4fd3c-127">Remarks</span></span>  
 <span data-ttu-id="4fd3c-128">Standardmäßig bietet <xref:System.Xml.Serialization.XmlSerializer> eine zusätzliche Sicherheitsebene, um mögliche Denial-of-Service-Angriffe beim Serialisieren nicht vertrauenswürdiger Daten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-128">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="4fd3c-129">Hierzu wird während der Deserialisierung versucht, Endlosschleifen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-129">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="4fd3c-130">Wenn eine solche Bedingung erkannt wird, wird eine Ausnahme mit der folgenden Meldung ausgelöst: „Interner Fehler: Die Deserialisierung konnte über den zugrunde liegenden Datenstrom hinaus nicht erweitert werden.“</span><span class="sxs-lookup"><span data-stu-id="4fd3c-130">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="4fd3c-131">Diese Meldung bedeutet nicht unbedingt, dass gerade ein Denial-of-Service-Angriff ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-131">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="4fd3c-132">In einigen seltenen Fällen erzeugt der Erkennungsmechanismus für Endlosschleifen einen falschen positiven Wert und die Ausnahme wird aufgrund einer zulässigen eingehenden Meldung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-132">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="4fd3c-133">Wenn in Ihrer Anwendung zulässige Meldungen durch diese zusätzliche Sicherheitsebene verweigert werden, legen Sie das **checkDeserializeAdvances**-Attribut auf FALSE fest.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-133">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fd3c-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4fd3c-134">Example</span></span>  
 <span data-ttu-id="4fd3c-135">Im folgenden Codebeispiel wird das **checkDeserializeAdvances**-Attribut auf FALSE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-135">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fd3c-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fd3c-136">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="4fd3c-137">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="4fd3c-137">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="4fd3c-138">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4fd3c-138">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
