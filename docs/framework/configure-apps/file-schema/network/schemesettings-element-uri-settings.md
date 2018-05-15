---
title: '&lt;SchemeSettings&gt; Element (Uri-Einstellungen)'
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 40ff62a48a3ba1f4a9b5aed28630ab70d37869fc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltschemesettingsgt-element-uri-settings"></a><span data-ttu-id="c8a1c-102">&lt;SchemeSettings&gt; Element (Uri-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="c8a1c-102">&lt;schemeSettings&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="c8a1c-103">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="c8a1c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c8a1c-104">\<configuration></span></span>  
<span data-ttu-id="c8a1c-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="c8a1c-105">\<uri></span></span>  
<span data-ttu-id="c8a1c-106">\<SchemeSettings ></span><span class="sxs-lookup"><span data-stu-id="c8a1c-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8a1c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8a1c-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8a1c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c8a1c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c8a1c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8a1c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c8a1c-110">Attributes</span></span>  
 <span data-ttu-id="c8a1c-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="c8a1c-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8a1c-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8a1c-112">Child Elements</span></span>  
  
|<span data-ttu-id="c8a1c-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="c8a1c-113">**Element**</span></span>|<span data-ttu-id="c8a1c-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c8a1c-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c8a1c-115">add</span><span class="sxs-lookup"><span data-stu-id="c8a1c-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="c8a1c-116">Fügt eine Schema-Einstellung für den Schemanamen eines.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="c8a1c-117">clear</span><span class="sxs-lookup"><span data-stu-id="c8a1c-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="c8a1c-118">Löscht alle vorhandenen Schema-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="c8a1c-119">remove</span><span class="sxs-lookup"><span data-stu-id="c8a1c-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="c8a1c-120">Entfernt eine Schema-Einstellung für den Schemanamen eines an.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8a1c-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8a1c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c8a1c-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="c8a1c-122">**Element**</span></span>|<span data-ttu-id="c8a1c-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c8a1c-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c8a1c-124">URI</span><span class="sxs-lookup"><span data-stu-id="c8a1c-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="c8a1c-125">Enthält Einstellungen, die angeben, wie .NET Framework Webadressen ausgedrückt mit uniform Resource Identifier (URIs) behandelt.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8a1c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8a1c-126">Remarks</span></span>  
 <span data-ttu-id="c8a1c-127">Wird standardmäßig die <xref:System.Uri?displayProperty=nameWithType> Klasse un-Escapezeichen Prozent codiert Pfadtrennzeichen vor dem Pfad Komprimierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="c8a1c-128">Dies wurde als Sicherheitsmechanismus vor Angriffen wie folgt implementiert:</span><span class="sxs-lookup"><span data-stu-id="c8a1c-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="c8a1c-129">Wenn dieser URI übergeben wird auf Module nicht behandeln Prozent codierten Zeichen richtig, kann dies dazu führen den folgenden Befehl, der vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="c8a1c-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="c8a1c-130">Aus diesem Grund <xref:System.Uri?displayProperty=nameWithType> -Klasse erste un-Escapezeichen Pfadtrennzeichen und wendet dann Pfad Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="c8a1c-131">Das Ergebnis der Übergabe der böswilligen URL oben auf <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt der folgende URI:</span><span class="sxs-lookup"><span data-stu-id="c8a1c-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="c8a1c-132">Dieses Standardverhalten kann auf keine Escapezeichen Prozentzeichen codierten Pfadtrennzeichen mithilfe der Konfigurationsoption SchemeSettings für ein bestimmtes Schema geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c8a1c-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="c8a1c-133">Configuration Files</span></span>  
 <span data-ttu-id="c8a1c-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8a1c-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8a1c-135">Example</span></span>  
 <span data-ttu-id="c8a1c-136">Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> Klasse keine Escapezeichen Prozentzeichen codiert Pfadtrennzeichen für die http-Protokollschema unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="c8a1c-137">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="c8a1c-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="c8a1c-138">Namespace</span><span class="sxs-lookup"><span data-stu-id="c8a1c-138">Namespace</span></span>|<span data-ttu-id="c8a1c-139">System</span><span class="sxs-lookup"><span data-stu-id="c8a1c-139">System</span></span>|  
|<span data-ttu-id="c8a1c-140">Schemaname</span><span class="sxs-lookup"><span data-stu-id="c8a1c-140">Schema Name</span></span>||  
|<span data-ttu-id="c8a1c-141">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c8a1c-141">Validation File</span></span>||  
|<span data-ttu-id="c8a1c-142">Leer kann sein</span><span class="sxs-lookup"><span data-stu-id="c8a1c-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="c8a1c-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8a1c-143">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="c8a1c-144">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c8a1c-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
