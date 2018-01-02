---
title: '&lt;SchemeSettings&gt; Element (Uri-Einstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 19bcb64beb7b022d20bbde1210ae6d844690d891
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltschemesettingsgt-element-uri-settings"></a><span data-ttu-id="4ee42-102">&lt;SchemeSettings&gt; Element (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="4ee42-102">&lt;schemeSettings&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="4ee42-103">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="4ee42-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="4ee42-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4ee42-104">\<configuration></span></span>  
<span data-ttu-id="4ee42-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="4ee42-105">\<uri></span></span>  
<span data-ttu-id="4ee42-106">\<SchemeSettings ></span><span class="sxs-lookup"><span data-stu-id="4ee42-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee42-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ee42-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ee42-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4ee42-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4ee42-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ee42-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ee42-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ee42-110">Attributes</span></span>  
 <span data-ttu-id="4ee42-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="4ee42-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4ee42-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ee42-112">Child Elements</span></span>  
  
|<span data-ttu-id="4ee42-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="4ee42-113">**Element**</span></span>|<span data-ttu-id="4ee42-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4ee42-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4ee42-115">add</span><span class="sxs-lookup"><span data-stu-id="4ee42-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="4ee42-116">Fügt eine Schema-Einstellung für den Schemanamen eines.</span><span class="sxs-lookup"><span data-stu-id="4ee42-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="4ee42-117">clear</span><span class="sxs-lookup"><span data-stu-id="4ee42-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="4ee42-118">Löscht alle vorhandenen Schema-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="4ee42-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="4ee42-119">remove</span><span class="sxs-lookup"><span data-stu-id="4ee42-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="4ee42-120">Entfernt eine Schema-Einstellung für den Schemanamen eines an.</span><span class="sxs-lookup"><span data-stu-id="4ee42-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4ee42-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ee42-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4ee42-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="4ee42-122">**Element**</span></span>|<span data-ttu-id="4ee42-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4ee42-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4ee42-124">URI</span><span class="sxs-lookup"><span data-stu-id="4ee42-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="4ee42-125">Enthält Einstellungen, die angeben, wie .NET Framework Webadressen ausgedrückt mit uniform Resource Identifier (URIs) behandelt.</span><span class="sxs-lookup"><span data-stu-id="4ee42-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ee42-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ee42-126">Remarks</span></span>  
 <span data-ttu-id="4ee42-127">Wird standardmäßig die <xref:System.Uri?displayProperty=nameWithType> Klasse un-Escapezeichen Prozent codiert Pfadtrennzeichen vor dem Pfad Komprimierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="4ee42-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="4ee42-128">Dies wurde als Sicherheitsmechanismus vor Angriffen wie folgt implementiert:</span><span class="sxs-lookup"><span data-stu-id="4ee42-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="4ee42-129">Wenn dieser URI übergeben wird auf Module nicht behandeln Prozent codierten Zeichen richtig, kann dies dazu führen den folgenden Befehl, der vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="4ee42-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="4ee42-130">Aus diesem Grund <xref:System.Uri?displayProperty=nameWithType> -Klasse erste un-Escapezeichen Pfadtrennzeichen und wendet dann Pfad Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="4ee42-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="4ee42-131">Das Ergebnis der Übergabe der böswilligen URL oben auf <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt der folgende URI:</span><span class="sxs-lookup"><span data-stu-id="4ee42-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="4ee42-132">Dieses Standardverhalten kann auf keine Escapezeichen Prozentzeichen codierten Pfadtrennzeichen mithilfe der Konfigurationsoption SchemeSettings für ein bestimmtes Schema geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4ee42-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4ee42-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="4ee42-133">Configuration Files</span></span>  
 <span data-ttu-id="4ee42-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4ee42-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ee42-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ee42-135">Example</span></span>  
 <span data-ttu-id="4ee42-136">Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> Klasse keine Escapezeichen Prozentzeichen codiert Pfadtrennzeichen für die http-Protokollschema unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ee42-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="4ee42-137">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="4ee42-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="4ee42-138">Namespace</span><span class="sxs-lookup"><span data-stu-id="4ee42-138">Namespace</span></span>|<span data-ttu-id="4ee42-139">System</span><span class="sxs-lookup"><span data-stu-id="4ee42-139">System</span></span>|  
|<span data-ttu-id="4ee42-140">Schemaname</span><span class="sxs-lookup"><span data-stu-id="4ee42-140">Schema Name</span></span>||  
|<span data-ttu-id="4ee42-141">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="4ee42-141">Validation File</span></span>||  
|<span data-ttu-id="4ee42-142">Leer kann sein</span><span class="sxs-lookup"><span data-stu-id="4ee42-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="4ee42-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ee42-143">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="4ee42-144">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4ee42-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
