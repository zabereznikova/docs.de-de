---
title: "&lt;Entfernen Sie&gt; -Element für SchemeSettings (Uri-Einstellungen)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6d587dced4660774b67a8e884bf6c25df3b6e400
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="c5133-102">&lt;Entfernen Sie&gt; -Element für SchemeSettings (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="c5133-102">&lt;remove&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="c5133-103">Entfernt eine Schema-Einstellung für den Schemanamen eines an.</span><span class="sxs-lookup"><span data-stu-id="c5133-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="c5133-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c5133-104">\<configuration></span></span>  
<span data-ttu-id="c5133-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="c5133-105">\<uri></span></span>  
<span data-ttu-id="c5133-106">\<SchemeSettings ></span><span class="sxs-lookup"><span data-stu-id="c5133-106">\<schemeSettings></span></span>  
<span data-ttu-id="c5133-107">\<Entfernen ></span><span class="sxs-lookup"><span data-stu-id="c5133-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5133-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5133-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5133-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c5133-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c5133-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5133-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5133-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c5133-111">Attributes</span></span>  
  
|<span data-ttu-id="c5133-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c5133-112">Attribute</span></span>|<span data-ttu-id="c5133-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5133-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5133-114">Name</span><span class="sxs-lookup"><span data-stu-id="c5133-114">name</span></span>|<span data-ttu-id="c5133-115">Der Schemaname für die diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="c5133-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="c5133-116">Der nur die unterstützten Werte sind Name = "http" und Name = "Https".</span><span class="sxs-lookup"><span data-stu-id="c5133-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5133-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5133-117">Child Elements</span></span>  
 <span data-ttu-id="c5133-118">Keine</span><span class="sxs-lookup"><span data-stu-id="c5133-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5133-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5133-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c5133-120">Element</span><span class="sxs-lookup"><span data-stu-id="c5133-120">Element</span></span>|<span data-ttu-id="c5133-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5133-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5133-122">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="c5133-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="c5133-123">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="c5133-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5133-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5133-124">Remarks</span></span>  
 <span data-ttu-id="c5133-125">Wird standardmäßig die <xref:System.Uri?displayProperty=nameWithType> Klasse un-Escapezeichen Prozent codiert Pfadtrennzeichen vor dem Pfad Komprimierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="c5133-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="c5133-126">Dies wurde als Sicherheitsmechanismus vor Angriffen wie folgt implementiert:</span><span class="sxs-lookup"><span data-stu-id="c5133-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="c5133-127">Wenn dieser URI übergeben wird auf Module nicht behandeln Prozent codierten Zeichen richtig, kann dies dazu führen den folgenden Befehl, der vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="c5133-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="c5133-128">Aus diesem Grund <xref:System.Uri?displayProperty=nameWithType> -Klasse erste un-Escapezeichen Pfadtrennzeichen und wendet dann Pfad Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="c5133-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="c5133-129">Das Ergebnis der Übergabe der böswilligen URL oben auf <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt der folgende URI:</span><span class="sxs-lookup"><span data-stu-id="c5133-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="c5133-130">Dieses Standardverhalten kann auf keine Escapezeichen Prozentzeichen codierten Pfadtrennzeichen mithilfe der Konfigurationsoption SchemeSettings für ein bestimmtes Schema geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c5133-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c5133-131">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="c5133-131">Configuration Files</span></span>  
 <span data-ttu-id="c5133-132">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c5133-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5133-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5133-133">Example</span></span>  
 <span data-ttu-id="c5133-134">Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> -Klasse, die alle Schema-Einstellungen für die http-Protokollschema entfernt.</span><span class="sxs-lookup"><span data-stu-id="c5133-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5133-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5133-135">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="c5133-136">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c5133-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
