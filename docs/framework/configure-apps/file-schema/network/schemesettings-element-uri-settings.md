---
title: <schemeSettings>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154646"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="a3cab-102">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="a3cab-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="a3cab-103">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="a3cab-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="a3cab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3cab-104">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3cab-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a3cab-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a3cab-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3cab-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3cab-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="a3cab-107">Attributes</span></span>  
 <span data-ttu-id="a3cab-108">Keine</span><span class="sxs-lookup"><span data-stu-id="a3cab-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3cab-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3cab-109">Child Elements</span></span>  
  
|<span data-ttu-id="a3cab-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="a3cab-110">**Element**</span></span>|<span data-ttu-id="a3cab-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a3cab-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a3cab-112">add</span><span class="sxs-lookup"><span data-stu-id="a3cab-112">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a3cab-113">Fügt eine Schema Einstellung für einen Schema Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="a3cab-113">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="a3cab-114">Löschen</span><span class="sxs-lookup"><span data-stu-id="a3cab-114">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a3cab-115">Löscht alle vorhandenen Schema Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a3cab-115">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="a3cab-116">remove</span><span class="sxs-lookup"><span data-stu-id="a3cab-116">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a3cab-117">Entfernt eine Schema Einstellung für einen Schema Namen.</span><span class="sxs-lookup"><span data-stu-id="a3cab-117">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3cab-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3cab-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a3cab-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="a3cab-119">**Element**</span></span>|<span data-ttu-id="a3cab-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a3cab-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a3cab-121">uri</span><span class="sxs-lookup"><span data-stu-id="a3cab-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="a3cab-122">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="a3cab-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3cab-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a3cab-123">Remarks</span></span>  
 <span data-ttu-id="a3cab-124">Standardmäßig werden von der- <xref:System.Uri?displayProperty=nameWithType> Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="a3cab-124">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="a3cab-125">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="a3cab-125">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a3cab-126">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a3cab-126">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="a3cab-127">Aus diesem Grund werden von der-Klasse zuerst Pfad Trennzeichen aufgehoben, <xref:System.Uri?displayProperty=nameWithType> und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="a3cab-127">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="a3cab-128">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="a3cab-128">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a3cab-129">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3cab-129">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a3cab-130">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a3cab-130">Configuration Files</span></span>  
 <span data-ttu-id="a3cab-131">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3cab-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3cab-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3cab-132">Example</span></span>  
 <span data-ttu-id="a3cab-133">Das folgende Beispiel zeigt eine Konfiguration, die von der-Klasse verwendet wird <xref:System.Uri> , um das Escapezeichen für Prozent codierte Pfade für das http-Schema zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a3cab-133">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="a3cab-134">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="a3cab-134">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="a3cab-135">Namespace</span><span class="sxs-lookup"><span data-stu-id="a3cab-135">Namespace</span></span>|<span data-ttu-id="a3cab-136">System</span><span class="sxs-lookup"><span data-stu-id="a3cab-136">System</span></span>|  
|<span data-ttu-id="a3cab-137">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="a3cab-137">Schema Name</span></span>||  
|<span data-ttu-id="a3cab-138">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="a3cab-138">Validation File</span></span>||  
|<span data-ttu-id="a3cab-139">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="a3cab-139">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a3cab-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3cab-140">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="a3cab-141">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="a3cab-141">Network Settings Schema</span></span>](index.md)
