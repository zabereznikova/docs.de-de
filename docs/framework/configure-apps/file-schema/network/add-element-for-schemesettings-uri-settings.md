---
title: <add>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: ed40098e8d4c2d1298771e67a618b8d04f59c912
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087720"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="37c2d-102">\<add>-Element für schemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="37c2d-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="37c2d-103">Fügt eine Schema Einstellung für einen Schema Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="37c2d-103">Adds a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="37c2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37c2d-104">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37c2d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="37c2d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="37c2d-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="37c2d-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37c2d-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="37c2d-107">Attributes</span></span>  
  
|<span data-ttu-id="37c2d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="37c2d-108">Attribute</span></span>|<span data-ttu-id="37c2d-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="37c2d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37c2d-110">name</span><span class="sxs-lookup"><span data-stu-id="37c2d-110">name</span></span>|<span data-ttu-id="37c2d-111">Der Name des Schemas, für das diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="37c2d-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="37c2d-112">Die einzigen unterstützten Werte sind Name = "http" und Name = "https".</span><span class="sxs-lookup"><span data-stu-id="37c2d-112">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="37c2d-113">{Attribut Name} Versehen</span><span class="sxs-lookup"><span data-stu-id="37c2d-113">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="37c2d-114">Wert</span><span class="sxs-lookup"><span data-stu-id="37c2d-114">Value</span></span>|<span data-ttu-id="37c2d-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="37c2d-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37c2d-116">genericuriparameseroptions</span><span class="sxs-lookup"><span data-stu-id="37c2d-116">genericUriParserOptions</span></span>|<span data-ttu-id="37c2d-117">Die Parseroptionen für dieses Schema.</span><span class="sxs-lookup"><span data-stu-id="37c2d-117">The parser options for this scheme.</span></span> <span data-ttu-id="37c2d-118">Der einzige unterstützte Wert ist genericuriparameseroptions = "dontunescapepathdotandslashes".</span><span class="sxs-lookup"><span data-stu-id="37c2d-118">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37c2d-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="37c2d-119">Child Elements</span></span>  
 <span data-ttu-id="37c2d-120">Keine</span><span class="sxs-lookup"><span data-stu-id="37c2d-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37c2d-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="37c2d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="37c2d-122">Element</span><span class="sxs-lookup"><span data-stu-id="37c2d-122">Element</span></span>|<span data-ttu-id="37c2d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37c2d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37c2d-124">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="37c2d-124">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="37c2d-125">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="37c2d-125">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37c2d-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="37c2d-126">Remarks</span></span>  
 <span data-ttu-id="37c2d-127">Standardmäßig werden von der- <xref:System.Uri?displayProperty=nameWithType> Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="37c2d-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="37c2d-128">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="37c2d-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="37c2d-129">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="37c2d-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="37c2d-130">Aus diesem Grund werden von der-Klasse zuerst Pfad Trennzeichen aufgehoben, <xref:System.Uri?displayProperty=nameWithType> und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="37c2d-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="37c2d-131">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="37c2d-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="37c2d-132">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="37c2d-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="37c2d-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="37c2d-133">Configuration Files</span></span>  
 <span data-ttu-id="37c2d-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37c2d-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37c2d-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37c2d-135">Example</span></span>  
 <span data-ttu-id="37c2d-136">Das folgende Beispiel zeigt eine Konfiguration, die von der-Klasse verwendet wird <xref:System.Uri> , um das Escapezeichen für Prozent codierte Pfade für das http-Schema zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="37c2d-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="37c2d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37c2d-137">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="37c2d-138">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="37c2d-138">Network Settings Schema</span></span>](index.md)
