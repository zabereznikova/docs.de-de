---
title: '&lt;Hinzufügen&gt; -Element für SchemeSettings (Uri-Einstellungen)'
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9cca5e35bfc0aef448d2d515f5ac55ed9e2e2258
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48781241"
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="ecf58-102">&lt;Hinzufügen&gt; -Element für SchemeSettings (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="ecf58-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="ecf58-103">Fügt eine Schema-Einstellung für ein Schemaname.</span><span class="sxs-lookup"><span data-stu-id="ecf58-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="ecf58-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ecf58-104">\<configuration></span></span>  
<span data-ttu-id="ecf58-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="ecf58-105">\<uri></span></span>  
<span data-ttu-id="ecf58-106">\<SchemeSettings ></span><span class="sxs-lookup"><span data-stu-id="ecf58-106">\<schemeSettings></span></span>  
<span data-ttu-id="ecf58-107">\<add></span><span class="sxs-lookup"><span data-stu-id="ecf58-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecf58-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecf58-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecf58-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ecf58-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ecf58-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ecf58-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecf58-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ecf58-111">Attributes</span></span>  
  
|<span data-ttu-id="ecf58-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ecf58-112">Attribute</span></span>|<span data-ttu-id="ecf58-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecf58-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ecf58-114">Name</span><span class="sxs-lookup"><span data-stu-id="ecf58-114">name</span></span>|<span data-ttu-id="ecf58-115">Der Schemaname, der für die diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="ecf58-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="ecf58-116">Die nur die unterstützten Werte sind Name = "http" und Name = "Https".</span><span class="sxs-lookup"><span data-stu-id="ecf58-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="ecf58-117">{Attributname} Attribut</span><span class="sxs-lookup"><span data-stu-id="ecf58-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="ecf58-118">Wert</span><span class="sxs-lookup"><span data-stu-id="ecf58-118">Value</span></span>|<span data-ttu-id="ecf58-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecf58-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ecf58-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="ecf58-120">genericUriParserOptions</span></span>|<span data-ttu-id="ecf58-121">Die Parseroptionen für dieses Schema.</span><span class="sxs-lookup"><span data-stu-id="ecf58-121">The parser options for this scheme.</span></span> <span data-ttu-id="ecf58-122">Der nur unterstützte Wert GenericUriParserOptions ist = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="ecf58-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecf58-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ecf58-123">Child Elements</span></span>  
 <span data-ttu-id="ecf58-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="ecf58-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ecf58-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ecf58-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ecf58-126">Element</span><span class="sxs-lookup"><span data-stu-id="ecf58-126">Element</span></span>|<span data-ttu-id="ecf58-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecf58-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecf58-128">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="ecf58-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="ecf58-129">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="ecf58-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecf58-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecf58-130">Remarks</span></span>  
 <span data-ttu-id="ecf58-131">In der Standardeinstellung die <xref:System.Uri?displayProperty=nameWithType> Klasse un-Escapezeichen % codiert Pfadtrennzeichen vor dem Ausführen der Path-Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="ecf58-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="ecf58-132">Dies wurde als Sicherheitsmechanismus vor Angriffen wie folgt implementiert:</span><span class="sxs-lookup"><span data-stu-id="ecf58-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="ecf58-133">Wenn dieser URI übergeben wird auf Module nicht verarbeiten % codierten Zeichen richtig, kann dies dazu führen den folgenden Befehl, der vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="ecf58-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="ecf58-134">Aus diesem Grund <xref:System.Uri?displayProperty=nameWithType> erste un-Escapezeichen Pfadtrennzeichen Klasse aus, und wendet dann pfadkomprimierung.</span><span class="sxs-lookup"><span data-stu-id="ecf58-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="ecf58-135">Das Ergebnis der Übergabe der böswilligen URL oben zum <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt in den folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="ecf58-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="ecf58-136">Dieses Standardverhalten kann auf keine Escapezeichen Prozentzeichen codierten Pfadtrennzeichen mithilfe der Konfigurationsoption SchemeSettings für ein bestimmtes Schema geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ecf58-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ecf58-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="ecf58-137">Configuration Files</span></span>  
 <span data-ttu-id="ecf58-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecf58-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecf58-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ecf58-139">Example</span></span>  
 <span data-ttu-id="ecf58-140">Das folgende Beispiel zeigt eine Konfiguration, die von verwendet die <xref:System.Uri> Klasse Nichthinzufügen prozentcodiert Pfadtrennzeichen für die http-Protokollschema unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecf58-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecf58-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecf58-141">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="ecf58-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ecf58-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
