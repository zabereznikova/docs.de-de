---
title: <iriParsing>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 2c99edf2f1a03e0e510858c106cad43b0eaa27b4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664086"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="262ed-102">\<iriparamesing >-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="262ed-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="262ed-103">Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="262ed-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="262ed-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="262ed-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="262ed-105">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="262ed-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="262ed-106">\<URI-> Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="262ed-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="262ed-107">\<iriParsing></span><span class="sxs-lookup"><span data-stu-id="262ed-107">\<iriParsing></span></span>](iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="262ed-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="262ed-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="262ed-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="262ed-109">Attributes and Elements</span></span>  
 <span data-ttu-id="262ed-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="262ed-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="262ed-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="262ed-111">Attributes</span></span>  
  
|<span data-ttu-id="262ed-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="262ed-112">**Element**</span></span>|<span data-ttu-id="262ed-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="262ed-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="262ed-114">Gibt an, ob die IRI-Verarbeitung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="262ed-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="262ed-115">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="262ed-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="262ed-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="262ed-116">Child Elements</span></span>  
 <span data-ttu-id="262ed-117">None</span><span class="sxs-lookup"><span data-stu-id="262ed-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="262ed-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="262ed-118">Parent Elements</span></span>  
  
|<span data-ttu-id="262ed-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="262ed-119">**Element**</span></span>|<span data-ttu-id="262ed-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="262ed-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="262ed-121">uri</span><span class="sxs-lookup"><span data-stu-id="262ed-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="262ed-122">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="262ed-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="262ed-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="262ed-123">Remarks</span></span>  
 <span data-ttu-id="262ed-124">Die vorhandene <xref:System.Uri> Klasse wurde in .NET Framework 3,5 erweitert.</span><span class="sxs-lookup"><span data-stu-id="262ed-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="262ed-125">3,0 SP1 und 2,0 SP1 zur Unterstützung von International Resource Identifier (IRI) und internationalisierten Domänen Namen (IDN).</span><span class="sxs-lookup"><span data-stu-id="262ed-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="262ed-126">Aktuelle Benutzer sehen keine Änderung des Verhaltens von .NET Framework 2,0, es sei denn, Sie aktivieren speziell IRI-und IDN-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="262ed-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="262ed-127">Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.</span><span class="sxs-lookup"><span data-stu-id="262ed-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="262ed-128">Die folgenden beiden Änderungen sind erforderlich, um die Unterstützung für IRI zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="262ed-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="262ed-129">Fügen Sie der Datei Machine. config im Verzeichnis .NET Framework 2,0 die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="262ed-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="262ed-130">Geben Sie an, ob die IRI-Verarbeitungs Regeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="262ed-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="262ed-131">Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="262ed-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="262ed-132">Durch das Aktivieren der IRI-Verarbeitung (iriising aktiviert = `true`) erfolgt die Normalisierung und Zeichen Überprüfung gemäß den neuesten IRI-Regeln in RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="262ed-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="262ed-133">Der Standardwert ist `false` und führt normalisierungs-und Zeichen Prüfungen gemäß RFC 2396 und RFC 3986 (für IPv6-Literale) durch.</span><span class="sxs-lookup"><span data-stu-id="262ed-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="262ed-134">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="262ed-134">Configuration Files</span></span>  
 <span data-ttu-id="262ed-135">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="262ed-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="262ed-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="262ed-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="262ed-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="262ed-137">Description</span></span>  
 <span data-ttu-id="262ed-138">Das folgende Beispiel zeigt eine Konfiguration, die von <xref:System.Uri> der-Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="262ed-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="262ed-139">Code</span><span class="sxs-lookup"><span data-stu-id="262ed-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="262ed-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="262ed-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="262ed-141">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="262ed-141">Network Settings Schema</span></span>](index.md)
