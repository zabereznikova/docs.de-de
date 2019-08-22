---
title: <add>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 027c7aaffea7950739f532309255d77afa031ada
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659554"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="2ec3d-102">\<Add >-Element für SchemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="2ec3d-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="2ec3d-103">Fügt eine Schema Einstellung für einen Schema Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="2ec3d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2ec3d-104">\<configuration></span></span>  
<span data-ttu-id="2ec3d-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="2ec3d-105">\<uri></span></span>  
<span data-ttu-id="2ec3d-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="2ec3d-106">\<schemeSettings></span></span>  
<span data-ttu-id="2ec3d-107">\<add></span><span class="sxs-lookup"><span data-stu-id="2ec3d-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec3d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ec3d-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ec3d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2ec3d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ec3d-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ec3d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2ec3d-111">Attributes</span></span>  
  
|<span data-ttu-id="2ec3d-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2ec3d-112">Attribute</span></span>|<span data-ttu-id="2ec3d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ec3d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ec3d-114">Name</span><span class="sxs-lookup"><span data-stu-id="2ec3d-114">name</span></span>|<span data-ttu-id="2ec3d-115">Der Name des Schemas, für das diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="2ec3d-116">Die einzigen unterstützten Werte sind Name = "http" und Name = "https".</span><span class="sxs-lookup"><span data-stu-id="2ec3d-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="2ec3d-117">{Attribut Name} Versehen</span><span class="sxs-lookup"><span data-stu-id="2ec3d-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="2ec3d-118">Wert</span><span class="sxs-lookup"><span data-stu-id="2ec3d-118">Value</span></span>|<span data-ttu-id="2ec3d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ec3d-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ec3d-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="2ec3d-120">genericUriParserOptions</span></span>|<span data-ttu-id="2ec3d-121">Die Parseroptionen für dieses Schema.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-121">The parser options for this scheme.</span></span> <span data-ttu-id="2ec3d-122">Der einzige unterstützte Wert ist genericuriparameseroptions = "dontunescapepathdotandslashes".</span><span class="sxs-lookup"><span data-stu-id="2ec3d-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ec3d-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ec3d-123">Child Elements</span></span>  
 <span data-ttu-id="2ec3d-124">None</span><span class="sxs-lookup"><span data-stu-id="2ec3d-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ec3d-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ec3d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2ec3d-126">Element</span><span class="sxs-lookup"><span data-stu-id="2ec3d-126">Element</span></span>|<span data-ttu-id="2ec3d-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ec3d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ec3d-128">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="2ec3d-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="2ec3d-129">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ec3d-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ec3d-130">Remarks</span></span>  
 <span data-ttu-id="2ec3d-131">Standardmäßig werden von <xref:System.Uri?displayProperty=nameWithType> der-Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="2ec3d-132">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="2ec3d-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="2ec3d-133">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="2ec3d-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="2ec3d-134">Aus diesem Grund werden <xref:System.Uri?displayProperty=nameWithType> von der-Klasse zuerst Pfad Trennzeichen aufgehoben, und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="2ec3d-135">Das Ergebnis der Übergabe der obigen bösartigen URL an <xref:System.Uri?displayProperty=nameWithType> den Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="2ec3d-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="2ec3d-136">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2ec3d-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="2ec3d-137">Configuration Files</span></span>  
 <span data-ttu-id="2ec3d-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ec3d-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ec3d-139">Example</span></span>  
 <span data-ttu-id="2ec3d-140">Das folgende Beispiel zeigt eine Konfiguration, die von <xref:System.Uri> der-Klasse verwendet wird, um das Escapezeichen für Prozent codierte Pfade für das http-Schema zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2ec3d-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ec3d-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ec3d-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="2ec3d-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2ec3d-142">Network Settings Schema</span></span>](index.md)
