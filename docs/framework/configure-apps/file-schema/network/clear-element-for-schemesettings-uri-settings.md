---
title: <clear>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 51c669aff767948523172aa075677ad3fb6478a2
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664182"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="38ae8-102">\<> Element für SchemeSettings löschen (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="38ae8-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="38ae8-103">Löscht alle vorhandenen Schema Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="38ae8-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="38ae8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="38ae8-104">\<configuration></span></span>  
<span data-ttu-id="38ae8-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="38ae8-105">\<uri></span></span>  
<span data-ttu-id="38ae8-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="38ae8-106">\<schemeSettings></span></span>  
<span data-ttu-id="38ae8-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="38ae8-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ae8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="38ae8-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38ae8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="38ae8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="38ae8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="38ae8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38ae8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="38ae8-111">Attributes</span></span>  
 <span data-ttu-id="38ae8-112">Keine</span><span class="sxs-lookup"><span data-stu-id="38ae8-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="38ae8-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38ae8-113">Child Elements</span></span>  
 <span data-ttu-id="38ae8-114">Keine</span><span class="sxs-lookup"><span data-stu-id="38ae8-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38ae8-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38ae8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="38ae8-116">Element</span><span class="sxs-lookup"><span data-stu-id="38ae8-116">Element</span></span>|<span data-ttu-id="38ae8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38ae8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38ae8-118">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="38ae8-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="38ae8-119">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="38ae8-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38ae8-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38ae8-120">Remarks</span></span>  
 <span data-ttu-id="38ae8-121">Standardmäßig werden von <xref:System.Uri?displayProperty=nameWithType> der-Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="38ae8-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="38ae8-122">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="38ae8-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="38ae8-123">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="38ae8-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="38ae8-124">Aus diesem Grund werden <xref:System.Uri?displayProperty=nameWithType> von der-Klasse zuerst Pfad Trennzeichen aufgehoben, und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="38ae8-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="38ae8-125">Das Ergebnis der Übergabe der obigen bösartigen URL an <xref:System.Uri?displayProperty=nameWithType> den Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="38ae8-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="38ae8-126">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="38ae8-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="38ae8-127">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="38ae8-127">Configuration Files</span></span>  
 <span data-ttu-id="38ae8-128">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="38ae8-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38ae8-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38ae8-129">Example</span></span>  
 <span data-ttu-id="38ae8-130">Das folgende Beispiel zeigt eine Konfiguration, die von <xref:System.Uri> der-Klasse verwendet wird, mit der alle Schema Einstellungen gelöscht werden. Anschließend wird die Unterstützung für die nicht-Escapezeichen für Prozent codierte Pfade für das http-Schema</span><span class="sxs-lookup"><span data-stu-id="38ae8-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="38ae8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38ae8-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="38ae8-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="38ae8-132">Network Settings Schema</span></span>](index.md)
