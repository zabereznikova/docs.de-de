---
title: <Uri>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 80d71da5ca680872e4948fa8ff135fbbdf08cffe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663966"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="69d3b-102">\<URI-> Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="69d3b-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="69d3b-103">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="69d3b-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="69d3b-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="69d3b-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="69d3b-105">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="69d3b-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="69d3b-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="69d3b-106">\<uri></span></span>](uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="69d3b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="69d3b-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69d3b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69d3b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="69d3b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69d3b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69d3b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="69d3b-110">Attributes</span></span>  
 <span data-ttu-id="69d3b-111">Keine</span><span class="sxs-lookup"><span data-stu-id="69d3b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="69d3b-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69d3b-112">Child Elements</span></span>  
  
|<span data-ttu-id="69d3b-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="69d3b-113">**Element**</span></span>|<span data-ttu-id="69d3b-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="69d3b-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="69d3b-115">idn</span><span class="sxs-lookup"><span data-stu-id="69d3b-115">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="69d3b-116">Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="69d3b-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="69d3b-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="69d3b-117">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="69d3b-118">Gibt an, ob die IRI-Verarbeitung (International Resource Identifier) <xref:System.Uri> auf angewendet wird und ob IRI-Erteilungs Regeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="69d3b-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="69d3b-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="69d3b-119">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="69d3b-120">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="69d3b-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69d3b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69d3b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="69d3b-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="69d3b-122">**Element**</span></span>|<span data-ttu-id="69d3b-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="69d3b-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="69d3b-124">configuration</span><span class="sxs-lookup"><span data-stu-id="69d3b-124">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="69d3b-125">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="69d3b-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69d3b-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69d3b-126">Remarks</span></span>  
 <span data-ttu-id="69d3b-127">Das `uri` -Element enthält Einstellungen für Member <xref:System.Uri> der-Klasse, die von Klassen <xref:System.Net> im-Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69d3b-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="69d3b-128">Die Einstellungen konfigurieren die Unterstützung für IRI und IDN.</span><span class="sxs-lookup"><span data-stu-id="69d3b-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69d3b-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69d3b-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="69d3b-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69d3b-130">Description</span></span>  
 <span data-ttu-id="69d3b-131">Das folgende Beispiel zeigt eine Konfiguration, die von <xref:System.Uri> der-Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69d3b-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="69d3b-132">Das Beispiel löscht außerdem alle Schema Einstellungen und fügt dann Unterstützung für die nicht-Escapezeichen für Prozent codierte Pfade für das http-Schema hinzu.</span><span class="sxs-lookup"><span data-stu-id="69d3b-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="69d3b-133">Code</span><span class="sxs-lookup"><span data-stu-id="69d3b-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69d3b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69d3b-134">See also</span></span>

- [<span data-ttu-id="69d3b-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="69d3b-135">Network Settings Schema</span></span>](index.md)
