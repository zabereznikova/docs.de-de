---
title: <clear>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087445"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="69a27-102">\<clear>-Element für schemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="69a27-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="69a27-103">Löscht alle vorhandenen Schema Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="69a27-103">Clears all existing scheme settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="69a27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69a27-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69a27-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69a27-105">Attributes and Elements</span></span>  
 <span data-ttu-id="69a27-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69a27-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69a27-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="69a27-107">Attributes</span></span>  
 <span data-ttu-id="69a27-108">Keine</span><span class="sxs-lookup"><span data-stu-id="69a27-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="69a27-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69a27-109">Child Elements</span></span>  
 <span data-ttu-id="69a27-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="69a27-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69a27-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69a27-111">Parent Elements</span></span>  
  
|<span data-ttu-id="69a27-112">Element</span><span class="sxs-lookup"><span data-stu-id="69a27-112">Element</span></span>|<span data-ttu-id="69a27-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="69a27-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69a27-114">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="69a27-114">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="69a27-115">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="69a27-115">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69a27-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="69a27-116">Remarks</span></span>  
 <span data-ttu-id="69a27-117">Standardmäßig werden von der- <xref:System.Uri?displayProperty=nameWithType> Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="69a27-117">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="69a27-118">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="69a27-118">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="69a27-119">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="69a27-119">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="69a27-120">Aus diesem Grund werden von der-Klasse zuerst Pfad Trennzeichen aufgehoben, <xref:System.Uri?displayProperty=nameWithType> und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="69a27-120">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="69a27-121">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="69a27-121">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="69a27-122">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69a27-122">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="69a27-123">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="69a27-123">Configuration Files</span></span>  
 <span data-ttu-id="69a27-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69a27-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a27-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69a27-125">Example</span></span>  
 <span data-ttu-id="69a27-126">Das folgende Beispiel zeigt eine Konfiguration, die von der-Klasse verwendet wird, mit der <xref:System.Uri> alle Schema Einstellungen gelöscht werden. Anschließend wird die Unterstützung für die nicht-Escapezeichen für Prozent codierte Pfade für das http-Schema</span><span class="sxs-lookup"><span data-stu-id="69a27-126">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69a27-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69a27-127">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="69a27-128">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="69a27-128">Network Settings Schema</span></span>](index.md)
