---
title: <schemeSettings>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 5a146b854239fd516125e66e05312e27b90c73ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187016"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="792cd-102">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="792cd-102">\<schemeSettings> Element (Uri Settings)</span></span>

<span data-ttu-id="792cd-103">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="792cd-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="792cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="792cd-104">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="792cd-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="792cd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="792cd-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="792cd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="792cd-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="792cd-107">Attributes</span></span>  

 <span data-ttu-id="792cd-108">Keine</span><span class="sxs-lookup"><span data-stu-id="792cd-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="792cd-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="792cd-109">Child Elements</span></span>  
  
|<span data-ttu-id="792cd-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="792cd-110">**Element**</span></span>|<span data-ttu-id="792cd-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="792cd-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="792cd-112">add</span><span class="sxs-lookup"><span data-stu-id="792cd-112">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="792cd-113">Fügt eine Schema Einstellung für einen Schema Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="792cd-113">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="792cd-114">Löschen</span><span class="sxs-lookup"><span data-stu-id="792cd-114">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="792cd-115">Löscht alle vorhandenen Schema Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="792cd-115">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="792cd-116">remove</span><span class="sxs-lookup"><span data-stu-id="792cd-116">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="792cd-117">Entfernt eine Schema Einstellung für einen Schema Namen.</span><span class="sxs-lookup"><span data-stu-id="792cd-117">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="792cd-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="792cd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="792cd-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="792cd-119">**Element**</span></span>|<span data-ttu-id="792cd-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="792cd-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="792cd-121">uri</span><span class="sxs-lookup"><span data-stu-id="792cd-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="792cd-122">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="792cd-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="792cd-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="792cd-123">Remarks</span></span>  

 <span data-ttu-id="792cd-124">Standardmäßig werden von der- <xref:System.Uri?displayProperty=nameWithType> Klasse in Prozent codierte Pfad Trennzeichen vor dem Ausführen der Pfad Komprimierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="792cd-124">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="792cd-125">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="792cd-125">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="792cd-126">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="792cd-126">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="792cd-127">Aus diesem Grund werden von der-Klasse zuerst Pfad Trennzeichen aufgehoben, <xref:System.Uri?displayProperty=nameWithType> und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="792cd-127">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="792cd-128">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="792cd-128">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="792cd-129">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="792cd-129">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="792cd-130">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="792cd-130">Configuration Files</span></span>  

 <span data-ttu-id="792cd-131">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="792cd-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="792cd-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="792cd-132">Example</span></span>  

 <span data-ttu-id="792cd-133">Das folgende Beispiel zeigt eine Konfiguration, die von der-Klasse verwendet wird <xref:System.Uri> , um das Escapezeichen für Prozent codierte Pfade für das http-Schema zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="792cd-133">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="792cd-134">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="792cd-134">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="792cd-135">Namespace</span><span class="sxs-lookup"><span data-stu-id="792cd-135">Namespace</span></span>|<span data-ttu-id="792cd-136">System</span><span class="sxs-lookup"><span data-stu-id="792cd-136">System</span></span>|  
|<span data-ttu-id="792cd-137">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="792cd-137">Schema Name</span></span>||  
|<span data-ttu-id="792cd-138">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="792cd-138">Validation File</span></span>||  
|<span data-ttu-id="792cd-139">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="792cd-139">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="792cd-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="792cd-140">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="792cd-141">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="792cd-141">Network Settings Schema</span></span>](index.md)
