---
title: '&lt;IriParsing&gt; Element (Uri-Einstellungen)'
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f05f7e35d69f789d3ebb371689aafbc84004b732
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltiriparsinggt-element-uri-settings"></a><span data-ttu-id="6b604-102">&lt;IriParsing&gt; Element (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="6b604-102">&lt;iriParsing&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="6b604-103">Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6b604-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="6b604-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="6b604-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="6b604-105">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="6b604-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="6b604-106">\<URI >-Element (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="6b604-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="6b604-107">\<IriParsing ></span><span class="sxs-lookup"><span data-stu-id="6b604-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="6b604-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b604-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b604-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b604-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6b604-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b604-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b604-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b604-111">Attributes</span></span>  
  
|<span data-ttu-id="6b604-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="6b604-112">**Element**</span></span>|<span data-ttu-id="6b604-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6b604-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="6b604-114">Gibt an, ob IRI-Analyse aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6b604-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="6b604-115">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="6b604-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b604-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b604-116">Child Elements</span></span>  
 <span data-ttu-id="6b604-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="6b604-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b604-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b604-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6b604-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="6b604-119">**Element**</span></span>|<span data-ttu-id="6b604-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6b604-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6b604-121">URI</span><span class="sxs-lookup"><span data-stu-id="6b604-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="6b604-122">Enthält Einstellungen, die angeben, wie .NET Framework Webadressen ausgedrückt mit uniform Resource Identifier (URIs) behandelt.</span><span class="sxs-lookup"><span data-stu-id="6b604-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b604-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b604-123">Remarks</span></span>  
 <span data-ttu-id="6b604-124">Die vorhandene <xref:System.Uri> Klasse in .NET Framework 3.5 erweitert wurde.</span><span class="sxs-lookup"><span data-stu-id="6b604-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="6b604-125">3.0 SP1 und 2.0 SP1 zur Unterstützung von International Resource Identifiers (IRI) und internationale Domänennamen (IDN).</span><span class="sxs-lookup"><span data-stu-id="6b604-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="6b604-126">Aktuellen Benutzer sehen keine Änderungen des Verhaltens gegenüber den .NET Framework 2.0, es sei denn, sie explizit IRI und IDN aktivieren unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6b604-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="6b604-127">Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.</span><span class="sxs-lookup"><span data-stu-id="6b604-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="6b604-128">Um die Unterstützung für IRI aktivieren, sind die folgenden zwei Änderungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6b604-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="6b604-129">Fügen Sie die folgende Zeile auf die Datei "Machine.config" im .NET Framework 2.0-Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="6b604-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="6b604-130">Geben Sie an, ob die IRI-Analyse Regeln angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b604-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="6b604-131">Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6b604-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="6b604-132">Aktivieren die IRI-Analyse (IriParsing aktiviert = `true`) ist dies der Normalisierung und zeichenüberprüfung entsprechend der neuesten IRI Regeln in RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="6b604-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="6b604-133">Der Standardwert ist `false` und führen Sie die Normalisierung und Überprüfung gemäß RFC 2396 und RFC 3986 mit Escapezeichen (für IPv6-Literale) Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6b604-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="6b604-134">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="6b604-134">Configuration Files</span></span>  
 <span data-ttu-id="6b604-135">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b604-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b604-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b604-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6b604-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b604-137">Description</span></span>  
 <span data-ttu-id="6b604-138">Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> Klasse IRI-Analyse und IDN-Namen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b604-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6b604-139">Code</span><span class="sxs-lookup"><span data-stu-id="6b604-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b604-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b604-140">See Also</span></span>  
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="6b604-141">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6b604-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
