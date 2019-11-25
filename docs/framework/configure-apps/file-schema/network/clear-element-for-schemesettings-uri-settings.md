---
title: <clear>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087445"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="b9eaa-102">\<Clear >-Element für SchemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="b9eaa-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="b9eaa-103">Löscht alle vorhandenen Schema Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b9eaa-103">Clears all existing scheme settings.</span></span>  

<span data-ttu-id="b9eaa-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9eaa-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b9eaa-105">&nbsp;&nbsp;[ **\<URI->** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b9eaa-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="b9eaa-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<SchemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b9eaa-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="b9eaa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Löschen** ></span><span class="sxs-lookup"><span data-stu-id="b9eaa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b9eaa-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9eaa-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9eaa-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b9eaa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b9eaa-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9eaa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9eaa-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b9eaa-111">Attributes</span></span>  
 <span data-ttu-id="b9eaa-112">Keine</span><span class="sxs-lookup"><span data-stu-id="b9eaa-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b9eaa-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9eaa-113">Child Elements</span></span>  
 <span data-ttu-id="b9eaa-114">Keine</span><span class="sxs-lookup"><span data-stu-id="b9eaa-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9eaa-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9eaa-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b9eaa-116">Element</span><span class="sxs-lookup"><span data-stu-id="b9eaa-116">Element</span></span>|<span data-ttu-id="b9eaa-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9eaa-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9eaa-118">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="b9eaa-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="b9eaa-119">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="b9eaa-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9eaa-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9eaa-120">Remarks</span></span>  
 <span data-ttu-id="b9eaa-121">Standardmäßig wird die <xref:System.Uri?displayProperty=nameWithType>-Klasse vor dem Ausführen der Pfad Komprimierung in Prozent codierte Pfad Trennzeichen aufheben.</span><span class="sxs-lookup"><span data-stu-id="b9eaa-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="b9eaa-122">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="b9eaa-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b9eaa-123">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="b9eaa-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="b9eaa-124">Aus diesem Grund werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse zunächst Pfad Trennzeichen aufgehoben, und dann wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="b9eaa-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="b9eaa-125">Das Ergebnis der Übergabe der obigen bösartigen URL an <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="b9eaa-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b9eaa-126">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9eaa-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b9eaa-127">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b9eaa-127">Configuration Files</span></span>  
 <span data-ttu-id="b9eaa-128">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9eaa-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9eaa-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9eaa-129">Example</span></span>  
 <span data-ttu-id="b9eaa-130">Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse verwendet wird, die alle Schema Einstellungen löscht und dann Unterstützung für das Aufheben der Escapezeichen für Prozent codierte Pfad Trennzeichen für das http-Schema hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b9eaa-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9eaa-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9eaa-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="b9eaa-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b9eaa-132">Network Settings Schema</span></span>](index.md)
