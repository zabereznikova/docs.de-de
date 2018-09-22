---
title: '&lt;xmlSerializer&gt;-Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 2770b82f71f3c4b43df4c44f75248e5392c528c2
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46585253"
---
# <a name="ltxmlserializergt-element"></a><span data-ttu-id="5bab4-102">&lt;xmlSerializer&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="5bab4-102">&lt;xmlSerializer&gt; Element</span></span>
<span data-ttu-id="5bab4-103">Gibt an, ob eine zusätzliche Zustandsüberprüfung für <xref:System.Xml.Serialization.XmlSerializer> durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5bab4-103">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="5bab4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5bab4-104">\<configuration></span></span>  
<span data-ttu-id="5bab4-105">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="5bab4-105">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bab4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bab4-106">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bab4-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5bab4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5bab4-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5bab4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bab4-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="5bab4-109">Attributes</span></span>  
  
|<span data-ttu-id="5bab4-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="5bab4-110">Attribute</span></span>|<span data-ttu-id="5bab4-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bab4-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5bab4-112">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="5bab4-112">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="5bab4-113">Gibt an, ob der Zustand von <xref:System.Xml.Serialization.XmlSerializer> überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="5bab4-113">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="5bab4-114">Legen Sie das Attribut auf "true" oder "false" fest.</span><span class="sxs-lookup"><span data-stu-id="5bab4-114">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="5bab4-115">Der Standardwert ist "true".</span><span class="sxs-lookup"><span data-stu-id="5bab4-115">The default is "true".</span></span>|  
|<span data-ttu-id="5bab4-116">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="5bab4-116">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="5bab4-117">Gibt an, ob <xref:System.Xml.Serialization.XmlSerializer> eine Vorgänger-Serialisierungsgenerierung verwendet, die Assemblys generiert, indem C#-Code in eine Datei geschrieben und anschließend in eine Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="5bab4-117">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="5bab4-118">Der Standardwert ist **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="5bab4-118">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5bab4-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5bab4-119">Child Elements</span></span>  
 <span data-ttu-id="5bab4-120">Keine</span><span class="sxs-lookup"><span data-stu-id="5bab4-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5bab4-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5bab4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5bab4-122">Element</span><span class="sxs-lookup"><span data-stu-id="5bab4-122">Element</span></span>|<span data-ttu-id="5bab4-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bab4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bab4-124">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="5bab4-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="5bab4-125">Enthält Konfigurationseinstellungen für die <xref:System.Xml.Serialization.XmlSerializer>-Klasse und die <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="5bab4-125">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bab4-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5bab4-126">Remarks</span></span>  
 <span data-ttu-id="5bab4-127">Standardmäßig bietet <xref:System.Xml.Serialization.XmlSerializer> eine zusätzliche Sicherheitsebene, um mögliche Denial-of-Service-Angriffe beim Serialisieren nicht vertrauenswürdiger Daten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="5bab4-127">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="5bab4-128">Hierzu wird während der Deserialisierung versucht, Endlosschleifen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="5bab4-128">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="5bab4-129">Wenn eine solche Bedingung erkannt wird, wird eine Ausnahme ausgelöst und folgende Meldung ausgegeben: "Interner Fehler: Deserialisierung des zugrunde liegenden Streams konnte nicht fortgesetzt werden."</span><span class="sxs-lookup"><span data-stu-id="5bab4-129">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="5bab4-130">Diese Meldung bedeutet nicht unbedingt, dass gerade ein Denial-of-Service-Angriff ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5bab4-130">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="5bab4-131">In einigen seltenen Fällen erzeugt der Erkennungsmechanismus für Endlosschleifen einen falschen positiven Wert und die Ausnahme wird aufgrund einer zulässigen eingehenden Meldung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5bab4-131">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="5bab4-132">Wenn in Ihrer Anwendung zulässige Meldungen durch diese zusätzliche Sicherheitsebene verweigert werden, legen Sie das **checkDeserializeAdvances**-Attribut auf FALSE fest.</span><span class="sxs-lookup"><span data-stu-id="5bab4-132">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bab4-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5bab4-133">Example</span></span>  
 <span data-ttu-id="5bab4-134">Im folgenden Codebeispiel wird das **checkDeserializeAdvances**-Attribut auf FALSE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5bab4-134">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bab4-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bab4-135">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>  
- [<span data-ttu-id="5bab4-136">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="5bab4-136">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
- [<span data-ttu-id="5bab4-137">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5bab4-137">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
