---
title: <remove>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 4a891eb8a2fd2d66b6435e2ae774ecd4a157c0f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659223"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="01083-102">\<Entfernen von >-Element für SchemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="01083-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="01083-103">Entfernt eine Schema Einstellung für einen Schema Namen.</span><span class="sxs-lookup"><span data-stu-id="01083-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="01083-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="01083-104">\<configuration></span></span>  
<span data-ttu-id="01083-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="01083-105">\<uri></span></span>  
<span data-ttu-id="01083-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="01083-106">\<schemeSettings></span></span>  
<span data-ttu-id="01083-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="01083-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01083-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="01083-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01083-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="01083-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01083-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="01083-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01083-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="01083-111">Attributes</span></span>  
  
|<span data-ttu-id="01083-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="01083-112">Attribute</span></span>|<span data-ttu-id="01083-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01083-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01083-114">Name</span><span class="sxs-lookup"><span data-stu-id="01083-114">name</span></span>|<span data-ttu-id="01083-115">Der Name des Schemas, für das diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="01083-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="01083-116">Die einzigen unterstützten Werte sind Name = "http" und Name = "https".</span><span class="sxs-lookup"><span data-stu-id="01083-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01083-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01083-117">Child Elements</span></span>  
 <span data-ttu-id="01083-118">Keine</span><span class="sxs-lookup"><span data-stu-id="01083-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01083-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01083-119">Parent Elements</span></span>  
  
|<span data-ttu-id="01083-120">Element</span><span class="sxs-lookup"><span data-stu-id="01083-120">Element</span></span>|<span data-ttu-id="01083-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01083-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01083-122">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="01083-122">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="01083-123">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="01083-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01083-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01083-124">Remarks</span></span>  
 <span data-ttu-id="01083-125">Standardmäßig werden von <xref:System.Uri?displayProperty=nameWithType> der-Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="01083-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="01083-126">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="01083-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="01083-127">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="01083-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="01083-128">Aus diesem Grund werden <xref:System.Uri?displayProperty=nameWithType> von der-Klasse zuerst Pfad Trennzeichen aufgehoben, und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="01083-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="01083-129">Das Ergebnis der Übergabe der obigen bösartigen URL an <xref:System.Uri?displayProperty=nameWithType> den Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="01083-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="01083-130">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="01083-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="01083-131">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="01083-131">Configuration Files</span></span>  
 <span data-ttu-id="01083-132">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01083-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01083-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01083-133">Example</span></span>  
 <span data-ttu-id="01083-134">Das folgende Beispiel zeigt eine Konfiguration, die von <xref:System.Uri> der-Klasse verwendet wird, mit der alle Schema Einstellungen für das http-Schema entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="01083-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01083-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01083-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="01083-136">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="01083-136">Network Settings Schema</span></span>](index.md)
