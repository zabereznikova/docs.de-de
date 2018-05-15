---
title: '&lt;Hinzufügen&gt; -Element für SchemeSettings (Uri-Einstellungen)'
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bd8033b07b29066633e5217645f3ee06937179da
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="6e9a8-102">&lt;Hinzufügen&gt; -Element für SchemeSettings (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="6e9a8-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="6e9a8-103">Fügt eine Schema-Einstellung für den Schemanamen eines.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="6e9a8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6e9a8-104">\<configuration></span></span>  
<span data-ttu-id="6e9a8-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="6e9a8-105">\<uri></span></span>  
<span data-ttu-id="6e9a8-106">\<SchemeSettings ></span><span class="sxs-lookup"><span data-stu-id="6e9a8-106">\<schemeSettings></span></span>  
<span data-ttu-id="6e9a8-107">\<add></span><span class="sxs-lookup"><span data-stu-id="6e9a8-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e9a8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e9a8-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e9a8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6e9a8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6e9a8-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e9a8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6e9a8-111">Attributes</span></span>  
  
|<span data-ttu-id="6e9a8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="6e9a8-112">Attribute</span></span>|<span data-ttu-id="6e9a8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e9a8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e9a8-114">Name</span><span class="sxs-lookup"><span data-stu-id="6e9a8-114">name</span></span>|<span data-ttu-id="6e9a8-115">Der Schemaname für die diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="6e9a8-116">Der nur die unterstützten Werte sind Name = "http" und Name = "Https".</span><span class="sxs-lookup"><span data-stu-id="6e9a8-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="6e9a8-117">{Attributnamen} Attribut</span><span class="sxs-lookup"><span data-stu-id="6e9a8-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="6e9a8-118">Wert</span><span class="sxs-lookup"><span data-stu-id="6e9a8-118">Value</span></span>|<span data-ttu-id="6e9a8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e9a8-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e9a8-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="6e9a8-120">genericUriParserOptions</span></span>|<span data-ttu-id="6e9a8-121">Die Parseroptionen für dieses Schema.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-121">The parser options for this scheme.</span></span> <span data-ttu-id="6e9a8-122">Der nur unterstützte Wert GenericUriParserOptions ist = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="6e9a8-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e9a8-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e9a8-123">Child Elements</span></span>  
 <span data-ttu-id="6e9a8-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="6e9a8-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e9a8-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e9a8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6e9a8-126">Element</span><span class="sxs-lookup"><span data-stu-id="6e9a8-126">Element</span></span>|<span data-ttu-id="6e9a8-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e9a8-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e9a8-128">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="6e9a8-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="6e9a8-129">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e9a8-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e9a8-130">Remarks</span></span>  
 <span data-ttu-id="6e9a8-131">Wird standardmäßig die <xref:System.Uri?displayProperty=nameWithType> Klasse un-Escapezeichen Prozent codiert Pfadtrennzeichen vor dem Pfad Komprimierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="6e9a8-132">Dies wurde als Sicherheitsmechanismus vor Angriffen wie folgt implementiert:</span><span class="sxs-lookup"><span data-stu-id="6e9a8-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="6e9a8-133">Wenn dieser URI übergeben wird auf Module nicht behandeln Prozent codierten Zeichen richtig, kann dies dazu führen den folgenden Befehl, der vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="6e9a8-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="6e9a8-134">Aus diesem Grund <xref:System.Uri?displayProperty=nameWithType> -Klasse erste un-Escapezeichen Pfadtrennzeichen und wendet dann Pfad Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="6e9a8-135">Das Ergebnis der Übergabe der böswilligen URL oben auf <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt der folgende URI:</span><span class="sxs-lookup"><span data-stu-id="6e9a8-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="6e9a8-136">Dieses Standardverhalten kann auf keine Escapezeichen Prozentzeichen codierten Pfadtrennzeichen mithilfe der Konfigurationsoption SchemeSettings für ein bestimmtes Schema geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6e9a8-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="6e9a8-137">Configuration Files</span></span>  
 <span data-ttu-id="6e9a8-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e9a8-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e9a8-139">Example</span></span>  
 <span data-ttu-id="6e9a8-140">Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> Klasse keine Escapezeichen Prozentzeichen codiert Pfadtrennzeichen für die http-Protokollschema unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e9a8-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e9a8-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e9a8-141">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="6e9a8-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6e9a8-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
