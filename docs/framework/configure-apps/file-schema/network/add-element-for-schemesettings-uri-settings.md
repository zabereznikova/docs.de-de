---
title: <add> -Element für SchemeSettings (Uri-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: e7606a1185d406384a926ca4dcb7c42586461574
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139931"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="dba51-102">\<Hinzufügen >-Element für SchemeSettings (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="dba51-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="dba51-103">Fügt eine Schema-Einstellung für ein Schemaname.</span><span class="sxs-lookup"><span data-stu-id="dba51-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="dba51-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dba51-104">\<configuration></span></span>  
<span data-ttu-id="dba51-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="dba51-105">\<uri></span></span>  
<span data-ttu-id="dba51-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="dba51-106">\<schemeSettings></span></span>  
<span data-ttu-id="dba51-107">\<add></span><span class="sxs-lookup"><span data-stu-id="dba51-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba51-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="dba51-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dba51-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dba51-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dba51-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dba51-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dba51-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="dba51-111">Attributes</span></span>  
  
|<span data-ttu-id="dba51-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="dba51-112">Attribute</span></span>|<span data-ttu-id="dba51-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dba51-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dba51-114">Name</span><span class="sxs-lookup"><span data-stu-id="dba51-114">name</span></span>|<span data-ttu-id="dba51-115">Der Schemaname, der für die diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="dba51-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="dba51-116">Die nur die unterstützten Werte sind Name = "http" und Name = "Https".</span><span class="sxs-lookup"><span data-stu-id="dba51-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="dba51-117">{Attributname} Attribut</span><span class="sxs-lookup"><span data-stu-id="dba51-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="dba51-118">Wert</span><span class="sxs-lookup"><span data-stu-id="dba51-118">Value</span></span>|<span data-ttu-id="dba51-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dba51-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dba51-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="dba51-120">genericUriParserOptions</span></span>|<span data-ttu-id="dba51-121">Die Parseroptionen für dieses Schema.</span><span class="sxs-lookup"><span data-stu-id="dba51-121">The parser options for this scheme.</span></span> <span data-ttu-id="dba51-122">Der nur unterstützte Wert GenericUriParserOptions ist = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="dba51-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dba51-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dba51-123">Child Elements</span></span>  
 <span data-ttu-id="dba51-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="dba51-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dba51-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dba51-125">Parent Elements</span></span>  
  
|<span data-ttu-id="dba51-126">Element</span><span class="sxs-lookup"><span data-stu-id="dba51-126">Element</span></span>|<span data-ttu-id="dba51-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dba51-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dba51-128">\<SchemeSettings >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="dba51-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="dba51-129">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="dba51-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dba51-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dba51-130">Remarks</span></span>  
 <span data-ttu-id="dba51-131">In der Standardeinstellung die <xref:System.Uri?displayProperty=nameWithType> Klasse un-Escapezeichen % codiert Pfadtrennzeichen vor dem Ausführen der Path-Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="dba51-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="dba51-132">Dies wurde als Sicherheitsmechanismus vor Angriffen wie folgt implementiert:</span><span class="sxs-lookup"><span data-stu-id="dba51-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="dba51-133">Wenn dieser URI übergeben wird auf Module nicht verarbeiten % codierten Zeichen richtig, kann dies dazu führen den folgenden Befehl, der vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="dba51-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="dba51-134">Aus diesem Grund <xref:System.Uri?displayProperty=nameWithType> erste un-Escapezeichen Pfadtrennzeichen Klasse aus, und wendet dann pfadkomprimierung.</span><span class="sxs-lookup"><span data-stu-id="dba51-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="dba51-135">Das Ergebnis der Übergabe der böswilligen URL oben zum <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt in den folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="dba51-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="dba51-136">Dieses Standardverhalten kann auf keine Escapezeichen Prozentzeichen codierten Pfadtrennzeichen mithilfe der Konfigurationsoption SchemeSettings für ein bestimmtes Schema geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dba51-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="dba51-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="dba51-137">Configuration Files</span></span>  
 <span data-ttu-id="dba51-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dba51-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dba51-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dba51-139">Example</span></span>  
 <span data-ttu-id="dba51-140">Das folgende Beispiel zeigt eine Konfiguration, die von verwendet die <xref:System.Uri> Klasse Nichthinzufügen prozentcodiert Pfadtrennzeichen für die http-Protokollschema unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dba51-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dba51-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dba51-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="dba51-142">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="dba51-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
