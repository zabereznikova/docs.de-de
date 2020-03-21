---
title: <add>-Element für webRequestModules (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155023"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="02715-102">\<Hinzufügen> Elements für webRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="02715-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="02715-103">Fügt der Anwendung ein benutzerdefiniertes Webanforderungsmodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="02715-103">Adds a custom Web request module to the application.</span></span>  

<span data-ttu-id="02715-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02715-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02715-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="02715-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="02715-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="02715-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="02715-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="02715-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="02715-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="02715-108">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02715-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02715-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02715-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02715-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02715-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="02715-111">Attributes</span></span>  
  
|<span data-ttu-id="02715-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="02715-112">**Attribute**</span></span>|<span data-ttu-id="02715-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="02715-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="02715-114">Das URI-Präfix für Anforderungen, die von diesem Webanforderungsmodul verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="02715-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="02715-115">Der vollqualifizierte Typname (durch die <xref:System.Type.FullName%2A> Eigenschaft angegeben) und <xref:System.Reflection.Assembly.FullName%2A> der Assemblyname (durch die Eigenschaft angegeben), getrennt durch ein Komma, das dieses Webanforderungsmodul implementiert.</span><span class="sxs-lookup"><span data-stu-id="02715-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02715-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02715-116">Child Elements</span></span>  
 <span data-ttu-id="02715-117">Keine.</span><span class="sxs-lookup"><span data-stu-id="02715-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02715-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02715-118">Parent Elements</span></span>  
  
|<span data-ttu-id="02715-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="02715-119">**Element**</span></span>|<span data-ttu-id="02715-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="02715-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="02715-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="02715-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="02715-122">Gibt Module an, die zum Anfordern von Informationen von Netzwerkhosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="02715-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02715-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="02715-123">Remarks</span></span>  
 <span data-ttu-id="02715-124">Das `prefix` Attribut definiert das URI-Präfix, das das angegebene Webanforderungsmodul verwendet.</span><span class="sxs-lookup"><span data-stu-id="02715-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="02715-125">Webanforderungsmodule werden in der Regel für die Verarbeitung eines bestimmten Protokolls, z. B. HTTP oder FTP, registriert, können jedoch registriert werden, um eine Anforderung an einen bestimmten Server oder Pfad auf einem Server zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="02715-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="02715-126">Das Webanforderungsmodul wird erstellt, wenn ein <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> URI-Abgleichspräfix an die Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="02715-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="02715-127">Der Wert `prefix` für das Attribut sollte die führenden Zeichen eines gültigen URI sein.</span><span class="sxs-lookup"><span data-stu-id="02715-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="02715-128">Zum Beispiel: `http` oder `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="02715-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="02715-129">Der Wert `type` für das Attribut sollte ein gültiger Typname und ein entsprechender Assemblyname sein, der durch ein Komma getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="02715-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="02715-130">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="02715-130">Configuration Files</span></span>  
 <span data-ttu-id="02715-131">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02715-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02715-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02715-132">Example</span></span>  
 <span data-ttu-id="02715-133">Im folgenden Beispiel wird ein benutzerdefiniertes Webanforderungsmodul für HTTP registriert.</span><span class="sxs-lookup"><span data-stu-id="02715-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="02715-134">Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="02715-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02715-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02715-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="02715-136">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="02715-136">Network Settings Schema</span></span>](index.md)
