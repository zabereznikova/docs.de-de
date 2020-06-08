---
title: <xmlSerializer>-Element
description: Das <xmlSerializer>-Element gibt an, ob eine zusätzliche Zustandsüberprüfung für den XmlSerializer durchgeführt wird.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 667d59f7eb0d1c7682afcdda584cc5b0ca2da802
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84288926"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="d3379-103">\<xmlSerializer>-Element</span><span class="sxs-lookup"><span data-stu-id="d3379-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="d3379-104">Gibt an, ob eine zusätzliche Zustandsüberprüfung für <xref:System.Xml.Serialization.XmlSerializer> durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d3379-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a><span data-ttu-id="d3379-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3379-105">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3379-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3379-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d3379-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3379-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3379-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3379-108">Attributes</span></span>  
  
|<span data-ttu-id="d3379-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="d3379-109">Attribute</span></span>|<span data-ttu-id="d3379-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3379-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3379-111">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="d3379-111">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="d3379-112">Gibt an, ob der Zustand von <xref:System.Xml.Serialization.XmlSerializer> überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="d3379-112">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="d3379-113">Legen Sie das Attribut auf "true" oder "false" fest.</span><span class="sxs-lookup"><span data-stu-id="d3379-113">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="d3379-114">Der Standardwert ist "true".</span><span class="sxs-lookup"><span data-stu-id="d3379-114">The default is "true".</span></span>|  
|<span data-ttu-id="d3379-115">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="d3379-115">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="d3379-116">Gibt an, ob <xref:System.Xml.Serialization.XmlSerializer> eine Vorgänger-Serialisierungsgenerierung verwendet, die Assemblys generiert, indem C#-Code in eine Datei geschrieben und anschließend in eine Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="d3379-116">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="d3379-117">Der Standardwert ist **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="d3379-117">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3379-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3379-118">Child Elements</span></span>  
 <span data-ttu-id="d3379-119">Keine</span><span class="sxs-lookup"><span data-stu-id="d3379-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3379-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3379-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d3379-121">Element</span><span class="sxs-lookup"><span data-stu-id="d3379-121">Element</span></span>|<span data-ttu-id="d3379-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3379-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3379-123">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="d3379-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="d3379-124">Enthält Konfigurationseinstellungen für die <xref:System.Xml.Serialization.XmlSerializer>-Klasse und die <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d3379-124">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3379-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3379-125">Remarks</span></span>  
 <span data-ttu-id="d3379-126">Standardmäßig bietet <xref:System.Xml.Serialization.XmlSerializer> eine zusätzliche Sicherheitsebene, um mögliche Denial-of-Service-Angriffe beim Serialisieren nicht vertrauenswürdiger Daten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="d3379-126">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="d3379-127">Hierzu wird während der Deserialisierung versucht, Endlosschleifen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="d3379-127">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="d3379-128">Wenn eine solche Bedingung erkannt wird, wird eine Ausnahme mit der folgenden Meldung ausgelöst: „Interner Fehler: Die Deserialisierung konnte über den zugrunde liegenden Datenstrom hinaus nicht erweitert werden.“</span><span class="sxs-lookup"><span data-stu-id="d3379-128">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="d3379-129">Diese Meldung bedeutet nicht unbedingt, dass gerade ein Denial-of-Service-Angriff ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d3379-129">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="d3379-130">In einigen seltenen Fällen erzeugt der Erkennungsmechanismus für Endlosschleifen einen falschen positiven Wert und die Ausnahme wird aufgrund einer zulässigen eingehenden Meldung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d3379-130">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="d3379-131">Wenn in Ihrer Anwendung zulässige Meldungen durch diese zusätzliche Sicherheitsebene verweigert werden, legen Sie das **checkDeserializeAdvances**-Attribut auf FALSE fest.</span><span class="sxs-lookup"><span data-stu-id="d3379-131">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3379-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3379-132">Example</span></span>  
 <span data-ttu-id="d3379-133">Im folgenden Codebeispiel wird das **checkDeserializeAdvances**-Attribut auf FALSE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d3379-133">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3379-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3379-134">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="d3379-135">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="d3379-135">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="d3379-136">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d3379-136">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
