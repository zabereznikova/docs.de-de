---
title: '&lt;xmlSerializer&gt;-Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 4b511dc229c9e8321b91fbb0f9395627680e5d12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591954"
---
# <a name="ltxmlserializergt-element"></a><span data-ttu-id="ee53a-102">&lt;xmlSerializer&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="ee53a-102">&lt;xmlSerializer&gt; Element</span></span>
<span data-ttu-id="ee53a-103">Gibt an, ob eine zusätzliche Zustandsüberprüfung für <xref:System.Xml.Serialization.XmlSerializer> durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ee53a-103">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="ee53a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ee53a-104">\<configuration></span></span>  
<span data-ttu-id="ee53a-105">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="ee53a-105">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee53a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee53a-106">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee53a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ee53a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ee53a-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ee53a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee53a-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="ee53a-109">Attributes</span></span>  
  
|<span data-ttu-id="ee53a-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="ee53a-110">Attribute</span></span>|<span data-ttu-id="ee53a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee53a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee53a-112">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="ee53a-112">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="ee53a-113">Gibt an, ob der Zustand von <xref:System.Xml.Serialization.XmlSerializer> überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="ee53a-113">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="ee53a-114">Legen Sie das Attribut auf "true" oder "false" fest.</span><span class="sxs-lookup"><span data-stu-id="ee53a-114">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="ee53a-115">Der Standardwert ist "true".</span><span class="sxs-lookup"><span data-stu-id="ee53a-115">The default is "true".</span></span>|  
|<span data-ttu-id="ee53a-116">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="ee53a-116">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="ee53a-117">Gibt an, ob <xref:System.Xml.Serialization.XmlSerializer> eine Vorgänger-Serialisierungsgenerierung verwendet, die Assemblys generiert, indem C#-Code in eine Datei geschrieben und anschließend in eine Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="ee53a-117">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="ee53a-118">Der Standardwert ist **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="ee53a-118">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee53a-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ee53a-119">Child Elements</span></span>  
 <span data-ttu-id="ee53a-120">Keine</span><span class="sxs-lookup"><span data-stu-id="ee53a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee53a-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ee53a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ee53a-122">Element</span><span class="sxs-lookup"><span data-stu-id="ee53a-122">Element</span></span>|<span data-ttu-id="ee53a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee53a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee53a-124">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="ee53a-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="ee53a-125">Enthält Konfigurationseinstellungen für die <xref:System.Xml.Serialization.XmlSerializer>-Klasse und die <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="ee53a-125">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee53a-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee53a-126">Remarks</span></span>  
 <span data-ttu-id="ee53a-127">Standardmäßig bietet <xref:System.Xml.Serialization.XmlSerializer> eine zusätzliche Sicherheitsebene, um mögliche Denial-of-Service-Angriffe beim Serialisieren nicht vertrauenswürdiger Daten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ee53a-127">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="ee53a-128">Hierzu wird während der Deserialisierung versucht, Endlosschleifen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ee53a-128">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="ee53a-129">Wenn eine solche Bedingung erkannt wird, wird eine Ausnahme mit der folgenden Meldung ausgelöst: "Interner Fehler: Fehler bei der Deserialisierung, fahren Sie fort, über die zugrunde liegenden Stream."</span><span class="sxs-lookup"><span data-stu-id="ee53a-129">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="ee53a-130">Diese Meldung bedeutet nicht unbedingt, dass gerade ein Denial-of-Service-Angriff ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ee53a-130">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="ee53a-131">In einigen seltenen Fällen erzeugt der Erkennungsmechanismus für Endlosschleifen einen falschen positiven Wert und die Ausnahme wird aufgrund einer zulässigen eingehenden Meldung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ee53a-131">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="ee53a-132">Wenn in Ihrer Anwendung zulässige Meldungen durch diese zusätzliche Sicherheitsebene verweigert werden, legen Sie das **checkDeserializeAdvances**-Attribut auf FALSE fest.</span><span class="sxs-lookup"><span data-stu-id="ee53a-132">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee53a-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee53a-133">Example</span></span>  
 <span data-ttu-id="ee53a-134">Im folgenden Codebeispiel wird das **checkDeserializeAdvances**-Attribut auf FALSE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ee53a-134">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee53a-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee53a-135">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="ee53a-136">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="ee53a-136">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="ee53a-137">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="ee53a-137">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
