---
title: <add>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: ed40098e8d4c2d1298771e67a618b8d04f59c912
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087720"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="79124-102">\<Add >-Element für SchemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="79124-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="79124-103">Fügt eine Schema Einstellung für einen Schema Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="79124-103">Adds a scheme setting for a scheme name.</span></span>  

<span data-ttu-id="79124-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="79124-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="79124-105">&nbsp;&nbsp;[ **\<URI->** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="79124-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="79124-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<SchemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="79124-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="79124-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="79124-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="79124-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="79124-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79124-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="79124-109">Attributes and Elements</span></span>  
 <span data-ttu-id="79124-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79124-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79124-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="79124-111">Attributes</span></span>  
  
|<span data-ttu-id="79124-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="79124-112">Attribute</span></span>|<span data-ttu-id="79124-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79124-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79124-114">Name</span><span class="sxs-lookup"><span data-stu-id="79124-114">name</span></span>|<span data-ttu-id="79124-115">Der Name des Schemas, für das diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="79124-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="79124-116">Die einzigen unterstützten Werte sind Name = "http" und Name = "https".</span><span class="sxs-lookup"><span data-stu-id="79124-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="79124-117">{Attribut Name} Versehen</span><span class="sxs-lookup"><span data-stu-id="79124-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="79124-118">Wert</span><span class="sxs-lookup"><span data-stu-id="79124-118">Value</span></span>|<span data-ttu-id="79124-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79124-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="79124-120">genericuriparameseroptions</span><span class="sxs-lookup"><span data-stu-id="79124-120">genericUriParserOptions</span></span>|<span data-ttu-id="79124-121">Die Parseroptionen für dieses Schema.</span><span class="sxs-lookup"><span data-stu-id="79124-121">The parser options for this scheme.</span></span> <span data-ttu-id="79124-122">Der einzige unterstützte Wert ist genericuriparameseroptions = "dontunescapepathdotandslashes".</span><span class="sxs-lookup"><span data-stu-id="79124-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79124-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79124-123">Child Elements</span></span>  
 <span data-ttu-id="79124-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="79124-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79124-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79124-125">Parent Elements</span></span>  
  
|<span data-ttu-id="79124-126">Element</span><span class="sxs-lookup"><span data-stu-id="79124-126">Element</span></span>|<span data-ttu-id="79124-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79124-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79124-128">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="79124-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="79124-129">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="79124-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79124-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79124-130">Remarks</span></span>  
 <span data-ttu-id="79124-131">Standardmäßig wird die <xref:System.Uri?displayProperty=nameWithType>-Klasse vor dem Ausführen der Pfad Komprimierung in Prozent codierte Pfad Trennzeichen aufheben.</span><span class="sxs-lookup"><span data-stu-id="79124-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="79124-132">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="79124-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="79124-133">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="79124-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="79124-134">Aus diesem Grund werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse zunächst Pfad Trennzeichen aufgehoben, und dann wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="79124-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="79124-135">Das Ergebnis der Übergabe der obigen bösartigen URL an <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="79124-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="79124-136">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79124-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="79124-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="79124-137">Configuration Files</span></span>  
 <span data-ttu-id="79124-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79124-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79124-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79124-139">Example</span></span>  
 <span data-ttu-id="79124-140">Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse verwendet wird, um das Escapezeichen für Prozent codierte Pfade für das http-Schema zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="79124-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79124-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79124-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="79124-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="79124-142">Network Settings Schema</span></span>](index.md)
