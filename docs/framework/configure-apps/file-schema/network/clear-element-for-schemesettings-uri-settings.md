---
title: "&lt;Deaktivieren Sie&gt; -Element für SchemeSettings (Uri-Einstellungen)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a2a4841635b5d6bcaa49d024dd92241573473036
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="535bb-102">&lt;Deaktivieren Sie&gt; -Element für SchemeSettings (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="535bb-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="535bb-103">Löscht alle vorhandenen Schema-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="535bb-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="535bb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="535bb-104">\<configuration></span></span>  
<span data-ttu-id="535bb-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="535bb-105">\<uri></span></span>  
<span data-ttu-id="535bb-106">\<SchemeSettings ></span><span class="sxs-lookup"><span data-stu-id="535bb-106">\<schemeSettings></span></span>  
<span data-ttu-id="535bb-107">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="535bb-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535bb-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="535bb-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="535bb-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="535bb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="535bb-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="535bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="535bb-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="535bb-111">Attributes</span></span>  
 <span data-ttu-id="535bb-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="535bb-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="535bb-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="535bb-113">Child Elements</span></span>  
 <span data-ttu-id="535bb-114">Keine</span><span class="sxs-lookup"><span data-stu-id="535bb-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="535bb-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="535bb-115">Parent Elements</span></span>  
  
|<span data-ttu-id="535bb-116">Element</span><span class="sxs-lookup"><span data-stu-id="535bb-116">Element</span></span>|<span data-ttu-id="535bb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="535bb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="535bb-118">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="535bb-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="535bb-119">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="535bb-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="535bb-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="535bb-120">Remarks</span></span>  
 <span data-ttu-id="535bb-121">Wird standardmäßig die <xref:System.Uri?displayProperty=nameWithType> Klasse un-Escapezeichen Prozent codiert Pfadtrennzeichen vor dem Pfad Komprimierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="535bb-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="535bb-122">Dies wurde als Sicherheitsmechanismus vor Angriffen wie folgt implementiert:</span><span class="sxs-lookup"><span data-stu-id="535bb-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="535bb-123">Wenn dieser URI übergeben wird auf Module nicht behandeln Prozent codierten Zeichen richtig, kann dies dazu führen den folgenden Befehl, der vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="535bb-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="535bb-124">Aus diesem Grund <xref:System.Uri?displayProperty=nameWithType> -Klasse erste un-Escapezeichen Pfadtrennzeichen und wendet dann Pfad Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="535bb-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="535bb-125">Das Ergebnis der Übergabe der böswilligen URL oben auf <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt der folgende URI:</span><span class="sxs-lookup"><span data-stu-id="535bb-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="535bb-126">Dieses Standardverhalten kann auf keine Escapezeichen Prozentzeichen codierten Pfadtrennzeichen mithilfe der Konfigurationsoption SchemeSettings für ein bestimmtes Schema geändert werden.</span><span class="sxs-lookup"><span data-stu-id="535bb-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="535bb-127">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="535bb-127">Configuration Files</span></span>  
 <span data-ttu-id="535bb-128">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="535bb-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="535bb-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="535bb-129">Example</span></span>  
 <span data-ttu-id="535bb-130">Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> -Klasse, die löscht alle Schema-Einstellungen, und klicken Sie dann bietet Unterstützung für Escapezeichen nicht Prozentzeichen codiert Pfadtrennzeichen für das HTTP-Schema.</span><span class="sxs-lookup"><span data-stu-id="535bb-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="535bb-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="535bb-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="535bb-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="535bb-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
