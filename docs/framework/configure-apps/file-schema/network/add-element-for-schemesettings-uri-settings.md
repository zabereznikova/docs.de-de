---
title: <add>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 55fcba41d4dabf8937ebaa11235e9309bcb57952
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149460"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="9148a-102">\<add>-Element für schemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="9148a-102">\<add> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="9148a-103">Fügt eine Schema Einstellung für einen Schema Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="9148a-103">Adds a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="9148a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9148a-104">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9148a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9148a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9148a-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9148a-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9148a-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="9148a-107">Attributes</span></span>  
  
|<span data-ttu-id="9148a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9148a-108">Attribute</span></span>|<span data-ttu-id="9148a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9148a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9148a-110">name</span><span class="sxs-lookup"><span data-stu-id="9148a-110">name</span></span>|<span data-ttu-id="9148a-111">Der Name des Schemas, für das diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="9148a-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="9148a-112">Die einzigen unterstützten Werte sind Name = "http" und Name = "https".</span><span class="sxs-lookup"><span data-stu-id="9148a-112">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="9148a-113">{Attribut Name} Versehen</span><span class="sxs-lookup"><span data-stu-id="9148a-113">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="9148a-114">Wert</span><span class="sxs-lookup"><span data-stu-id="9148a-114">Value</span></span>|<span data-ttu-id="9148a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9148a-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9148a-116">genericuriparameseroptions</span><span class="sxs-lookup"><span data-stu-id="9148a-116">genericUriParserOptions</span></span>|<span data-ttu-id="9148a-117">Die Parseroptionen für dieses Schema.</span><span class="sxs-lookup"><span data-stu-id="9148a-117">The parser options for this scheme.</span></span> <span data-ttu-id="9148a-118">Der einzige unterstützte Wert ist genericuriparameseroptions = "dontunescapepathdotandslashes".</span><span class="sxs-lookup"><span data-stu-id="9148a-118">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9148a-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9148a-119">Child Elements</span></span>  

 <span data-ttu-id="9148a-120">Keine</span><span class="sxs-lookup"><span data-stu-id="9148a-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9148a-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9148a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9148a-122">Element</span><span class="sxs-lookup"><span data-stu-id="9148a-122">Element</span></span>|<span data-ttu-id="9148a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9148a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9148a-124">\<schemeSettings> -Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="9148a-124">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="9148a-125">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="9148a-125">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9148a-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9148a-126">Remarks</span></span>  

 <span data-ttu-id="9148a-127">Standardmäßig werden von der- <xref:System.Uri?displayProperty=nameWithType> Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="9148a-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="9148a-128">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="9148a-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9148a-129">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="9148a-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="9148a-130">Aus diesem Grund werden von der-Klasse zuerst Pfad Trennzeichen aufgehoben, <xref:System.Uri?displayProperty=nameWithType> und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="9148a-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="9148a-131">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="9148a-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9148a-132">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9148a-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9148a-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="9148a-133">Configuration Files</span></span>  

 <span data-ttu-id="9148a-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9148a-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9148a-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9148a-135">Example</span></span>  

 <span data-ttu-id="9148a-136">Das folgende Beispiel zeigt eine Konfiguration, die von der-Klasse verwendet wird <xref:System.Uri> , um das Escapezeichen für Prozent codierte Pfade für das http-Schema zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9148a-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9148a-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9148a-137">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="9148a-138">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9148a-138">Network Settings Schema</span></span>](index.md)
