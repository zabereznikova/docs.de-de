---
title: '&lt;Deaktivieren Sie&gt; -Element für SchemeSettings (Uri-Einstellungen)'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 931ec37dde0e083991f1db016a2788bd5c41c29e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589931"
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="454f6-102">&lt;Deaktivieren Sie&gt; -Element für SchemeSettings (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="454f6-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="454f6-103">Löscht alle vorhandenen Schema-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="454f6-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="454f6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="454f6-104">\<configuration></span></span>  
<span data-ttu-id="454f6-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="454f6-105">\<uri></span></span>  
<span data-ttu-id="454f6-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="454f6-106">\<schemeSettings></span></span>  
<span data-ttu-id="454f6-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="454f6-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="454f6-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="454f6-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="454f6-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="454f6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="454f6-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="454f6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="454f6-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="454f6-111">Attributes</span></span>  
 <span data-ttu-id="454f6-112">Keine</span><span class="sxs-lookup"><span data-stu-id="454f6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="454f6-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="454f6-113">Child Elements</span></span>  
 <span data-ttu-id="454f6-114">Keine</span><span class="sxs-lookup"><span data-stu-id="454f6-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="454f6-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="454f6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="454f6-116">Element</span><span class="sxs-lookup"><span data-stu-id="454f6-116">Element</span></span>|<span data-ttu-id="454f6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="454f6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="454f6-118">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="454f6-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="454f6-119">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="454f6-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="454f6-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="454f6-120">Remarks</span></span>  
 <span data-ttu-id="454f6-121">In der Standardeinstellung die <xref:System.Uri?displayProperty=nameWithType> Klasse un-Escapezeichen % codiert Pfadtrennzeichen vor dem Ausführen der Path-Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="454f6-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="454f6-122">Dies wurde als Sicherheitsmechanismus vor Angriffen wie folgt implementiert:</span><span class="sxs-lookup"><span data-stu-id="454f6-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="454f6-123">Wenn dieser URI übergeben wird auf Module nicht verarbeiten % codierten Zeichen richtig, kann dies dazu führen den folgenden Befehl, der vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="454f6-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="454f6-124">Aus diesem Grund <xref:System.Uri?displayProperty=nameWithType> erste un-Escapezeichen Pfadtrennzeichen Klasse aus, und wendet dann pfadkomprimierung.</span><span class="sxs-lookup"><span data-stu-id="454f6-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="454f6-125">Das Ergebnis der Übergabe der böswilligen URL oben zum <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt in den folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="454f6-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="454f6-126">Dieses Standardverhalten kann auf keine Escapezeichen Prozentzeichen codierten Pfadtrennzeichen mithilfe der Konfigurationsoption SchemeSettings für ein bestimmtes Schema geändert werden.</span><span class="sxs-lookup"><span data-stu-id="454f6-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="454f6-127">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="454f6-127">Configuration Files</span></span>  
 <span data-ttu-id="454f6-128">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="454f6-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="454f6-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="454f6-129">Example</span></span>  
 <span data-ttu-id="454f6-130">Das folgende Beispiel zeigt eine Konfiguration, die von verwendet die <xref:System.Uri> -Klasse, löscht alle Einstellungen, und klicken Sie dann fügt Unterstützung für Escapezeichen für Prozentzeichen codiert Pfadtrennzeichen für das HTTP-Schema nicht.</span><span class="sxs-lookup"><span data-stu-id="454f6-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="454f6-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="454f6-131">See also</span></span>
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="454f6-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="454f6-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
