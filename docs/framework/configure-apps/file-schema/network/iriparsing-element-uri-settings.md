---
title: <iriParsing> -Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 7033f4dcda7d2fe73310ae0d36d9b05c090d13d4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299669"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="d5a68-102">\<IriParsing >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d5a68-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="d5a68-103">Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d5a68-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="d5a68-104">Schemahierarchie</span><span class="sxs-lookup"><span data-stu-id="d5a68-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="d5a68-105">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="d5a68-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="d5a68-106">\<URI >-Elements (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d5a68-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="d5a68-107">\<iriParsing></span><span class="sxs-lookup"><span data-stu-id="d5a68-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="d5a68-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5a68-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5a68-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d5a68-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d5a68-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5a68-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5a68-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d5a68-111">Attributes</span></span>  
  
|**<span data-ttu-id="d5a68-112">Element</span><span class="sxs-lookup"><span data-stu-id="d5a68-112">Element</span></span>**|**<span data-ttu-id="d5a68-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5a68-113">Description</span></span>**|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="d5a68-114">Gibt an, ob IRI-Analyse aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d5a68-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="d5a68-115">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d5a68-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5a68-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5a68-116">Child Elements</span></span>  
 <span data-ttu-id="d5a68-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="d5a68-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5a68-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5a68-118">Parent Elements</span></span>  
  
|**<span data-ttu-id="d5a68-119">Element</span><span class="sxs-lookup"><span data-stu-id="d5a68-119">Element</span></span>**|**<span data-ttu-id="d5a68-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5a68-120">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="d5a68-121">uri</span><span class="sxs-lookup"><span data-stu-id="d5a68-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="d5a68-122">Enthält Einstellungen, die angeben, wie .NET Framework Webadressen, die mithilfe von uniform Resource Identifier (URIs) ausgedrückt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d5a68-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5a68-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5a68-123">Remarks</span></span>  
 <span data-ttu-id="d5a68-124">Die vorhandene <xref:System.Uri> Klasse in .NET Framework 3.5 erweitert wurde.</span><span class="sxs-lookup"><span data-stu-id="d5a68-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="d5a68-125">3.0 SP1 und 2.0 SP1 zur Unterstützung von International Resource Identifiers (IRI) und internationale Domänennamen (IDN).</span><span class="sxs-lookup"><span data-stu-id="d5a68-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="d5a68-126">Derzeitige Benutzer werden keine Änderung gegenüber dem .NET Framework 2.0-Verhalten feststellen, es sei denn, sie IRI und IDN explizit aktivieren unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d5a68-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="d5a68-127">Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.</span><span class="sxs-lookup"><span data-stu-id="d5a68-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d5a68-128">Um die IRI-Unterstützung aktivieren, müssen die folgenden beiden Änderungen vornehmen:</span><span class="sxs-lookup"><span data-stu-id="d5a68-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="d5a68-129">Fügen Sie die folgende Zeile in die Datei "Machine.config" im .NET Framework 2.0-Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="d5a68-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="d5a68-130">Geben Sie an, ob die IRI-Analyseregeln angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5a68-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="d5a68-131">Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d5a68-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="d5a68-132">Aktivieren der IRI-Analyse (IriParsing aktiviert = `true`) wird die Normalisierung und zeichenüberprüfung gemäß den neuesten IRI-Regeln in RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="d5a68-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="d5a68-133">Der Standardwert ist `false` und wird die Normalisierung und Überprüfung gemäß RFC 2396 und RFC 3986 (für IPv6-Literale) Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d5a68-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="d5a68-134">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="d5a68-134">Configuration Files</span></span>  
 <span data-ttu-id="d5a68-135">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5a68-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5a68-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5a68-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d5a68-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5a68-137">Description</span></span>  
 <span data-ttu-id="d5a68-138">Das folgende Beispiel zeigt eine Konfiguration, die von verwendet die <xref:System.Uri> Klasse Analysieren von IRI und IDN-Namen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d5a68-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d5a68-139">Code</span><span class="sxs-lookup"><span data-stu-id="d5a68-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5a68-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5a68-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="d5a68-141">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="d5a68-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
