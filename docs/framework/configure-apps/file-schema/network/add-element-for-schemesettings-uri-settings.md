---
title: <add>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: efd52557ea8b617a39e685ff8ad69bab01322a7a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699593"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="8a902-102">\<add >-Element für SchemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a902-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="8a902-103">Fügt eine Schema Einstellung für einen Schema Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a902-103">Adds a scheme setting for a scheme name.</span></span>  
  
[<span data-ttu-id="8a902-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="8a902-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="8a902-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8a902-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="8a902-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<schemesettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8a902-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="8a902-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="8a902-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a902-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a902-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a902-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8a902-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8a902-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8a902-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a902-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8a902-111">Attributes</span></span>  
  
|<span data-ttu-id="8a902-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="8a902-112">Attribute</span></span>|<span data-ttu-id="8a902-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a902-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a902-114">NAME</span><span class="sxs-lookup"><span data-stu-id="8a902-114">name</span></span>|<span data-ttu-id="8a902-115">Der Name des Schemas, für das diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="8a902-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="8a902-116">Die einzigen unterstützten Werte sind Name = "http" und Name = "https".</span><span class="sxs-lookup"><span data-stu-id="8a902-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="8a902-117">{Attribut Name} Versehen</span><span class="sxs-lookup"><span data-stu-id="8a902-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="8a902-118">Wert</span><span class="sxs-lookup"><span data-stu-id="8a902-118">Value</span></span>|<span data-ttu-id="8a902-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a902-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a902-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="8a902-120">genericUriParserOptions</span></span>|<span data-ttu-id="8a902-121">Die Parseroptionen für dieses Schema.</span><span class="sxs-lookup"><span data-stu-id="8a902-121">The parser options for this scheme.</span></span> <span data-ttu-id="8a902-122">Der einzige unterstützte Wert ist genericuriparameseroptions = "dontunescapepathdotandslashes".</span><span class="sxs-lookup"><span data-stu-id="8a902-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a902-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a902-123">Child Elements</span></span>  
 <span data-ttu-id="8a902-124">None</span><span class="sxs-lookup"><span data-stu-id="8a902-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a902-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a902-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8a902-126">Element</span><span class="sxs-lookup"><span data-stu-id="8a902-126">Element</span></span>|<span data-ttu-id="8a902-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a902-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a902-128">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a902-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="8a902-129">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="8a902-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a902-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a902-130">Remarks</span></span>  
 <span data-ttu-id="8a902-131">Standardmäßig werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse vor dem Ausführen der Pfad Komprimierung die Prozentwerte für Prozent codierte Pfad Trennzeichen aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="8a902-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="8a902-132">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="8a902-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="8a902-133">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="8a902-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="8a902-134">Aus diesem Grund werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse zunächst Pfad Trennzeichen aufgehoben, und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="8a902-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="8a902-135">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType>-Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="8a902-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="8a902-136">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8a902-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8a902-137">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8a902-137">Configuration Files</span></span>  
 <span data-ttu-id="8a902-138">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a902-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a902-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a902-139">Example</span></span>  
 <span data-ttu-id="8a902-140">Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse verwendet wird, um das Escapezeichen für Prozent codierte Pfad Trennzeichen für das http-Schema zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8a902-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a902-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a902-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="8a902-142">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a902-142">Network Settings Schema</span></span>](index.md)
