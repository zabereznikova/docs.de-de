---
title: '&lt;URI&gt; -Elements (Netzwerkeinstellungen)'
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 48769298246dd71e040aac1c682e0fddfb5de89b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655542"
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="97c43-102">&lt;URI&gt; -Elements (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="97c43-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="97c43-103">Enthält Einstellungen, die angeben, wie .NET Framework Webadressen, die mithilfe von uniform Resource Identifier (URIs) ausgedrückt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="97c43-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="97c43-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="97c43-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="97c43-105">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="97c43-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="97c43-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="97c43-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="97c43-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="97c43-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97c43-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="97c43-108">Attributes and Elements</span></span>  
 <span data-ttu-id="97c43-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="97c43-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97c43-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="97c43-110">Attributes</span></span>  
 <span data-ttu-id="97c43-111">Keine</span><span class="sxs-lookup"><span data-stu-id="97c43-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97c43-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97c43-112">Child Elements</span></span>  
  
|<span data-ttu-id="97c43-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="97c43-113">**Element**</span></span>|<span data-ttu-id="97c43-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="97c43-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="97c43-115">idn</span><span class="sxs-lookup"><span data-stu-id="97c43-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="97c43-116">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="97c43-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="97c43-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="97c43-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="97c43-118">Gibt an, ob die Analyse von International Resource Identifier (IRI) gilt <xref:System.Uri> und gibt an, ob die IRI-Analyseregeln angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="97c43-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="97c43-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="97c43-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="97c43-120">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="97c43-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97c43-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97c43-121">Parent Elements</span></span>  
  
|<span data-ttu-id="97c43-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="97c43-122">**Element**</span></span>|<span data-ttu-id="97c43-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="97c43-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="97c43-124">configuration</span><span class="sxs-lookup"><span data-stu-id="97c43-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="97c43-125">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="97c43-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97c43-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97c43-126">Remarks</span></span>  
 <span data-ttu-id="97c43-127">Die `uri` Element enthält Einstellungen für Mitglieder der <xref:System.Uri> Klasse, die vom Klassen in der <xref:System.Net> Namespace.</span><span class="sxs-lookup"><span data-stu-id="97c43-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="97c43-128">Die Einstellungen Konfigurieren der Unterstützung für IRI und IDN.</span><span class="sxs-lookup"><span data-stu-id="97c43-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97c43-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97c43-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="97c43-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97c43-130">Description</span></span>  
 <span data-ttu-id="97c43-131">Das folgende Beispiel zeigt eine Konfiguration, die von verwendet die <xref:System.Uri> Klasse Analysieren von IRI und IDN-Namen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97c43-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="97c43-132">Im Beispiel löscht auch alle Einstellungen und klicken Sie dann fügt Unterstützung für Escapezeichen für Prozentzeichen codiert Pfadtrennzeichen für das HTTP-Schema nicht.</span><span class="sxs-lookup"><span data-stu-id="97c43-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="97c43-133">Code</span><span class="sxs-lookup"><span data-stu-id="97c43-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="97c43-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97c43-134">See also</span></span>
- [<span data-ttu-id="97c43-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="97c43-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
