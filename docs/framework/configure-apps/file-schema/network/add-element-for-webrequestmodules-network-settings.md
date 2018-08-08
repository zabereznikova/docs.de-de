---
title: '&lt;Hinzufügen&gt; WebRequestModules (Network Settings)-Element'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 921f5f2bfda1a19d022d3f3f4131e3653fd17ea7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742789"
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="c5463-102">&lt;Hinzufügen&gt; WebRequestModules (Network Settings)-Element</span><span class="sxs-lookup"><span data-stu-id="c5463-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="c5463-103">Fügt eine benutzerdefinierte Webmodul der Anforderung an die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="c5463-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="c5463-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c5463-104">\<configuration></span></span>  
<span data-ttu-id="c5463-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c5463-105">\<system.net></span></span>  
<span data-ttu-id="c5463-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="c5463-106">\<webRequestModules></span></span>  
<span data-ttu-id="c5463-107">\<add></span><span class="sxs-lookup"><span data-stu-id="c5463-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5463-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5463-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5463-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c5463-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c5463-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5463-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5463-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c5463-111">Attributes</span></span>  
  
|<span data-ttu-id="c5463-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="c5463-112">**Attribute**</span></span>|<span data-ttu-id="c5463-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c5463-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="c5463-114">Das URI-Präfix für Anforderungen, die von dieser Anforderung Webmodul behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5463-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="c5463-115">Den vollqualifizierten Typnamen (erkennbar die <xref:System.Type.FullName%2A> Eigenschaft) und der Name der Assembly (angegeben durch die <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, die diese Web-Request-Modul implementiert.</span><span class="sxs-lookup"><span data-stu-id="c5463-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5463-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5463-116">Child Elements</span></span>  
 <span data-ttu-id="c5463-117">Keine</span><span class="sxs-lookup"><span data-stu-id="c5463-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5463-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5463-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c5463-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="c5463-119">**Element**</span></span>|<span data-ttu-id="c5463-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c5463-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c5463-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="c5463-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="c5463-122">Gibt die Module zu verwenden, um Informationen von Netzwerkhosts anfordern.</span><span class="sxs-lookup"><span data-stu-id="c5463-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5463-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5463-123">Remarks</span></span>  
 <span data-ttu-id="c5463-124">Die `prefix` Attribut definiert die URI-Präfix, das das angegebene Modul der Web-Anforderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5463-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="c5463-125">Anforderung Webmodule werden in der Regel zum Behandeln eines bestimmten Protokolls, z. B. HTTP oder FTP, registriert, jedoch können registriert werden, um eine Anforderung für einen bestimmten Server oder einen Pfad auf einem Server zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="c5463-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="c5463-126">Die Anforderung Webmodul wird erstellt, wenn ein übereinstimmendes URI-Präfix an übergeben wird die <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="c5463-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="c5463-127">Der Wert für die `prefix` Attribut muss die ersten Zeichen ein gültiger URI – z. B. "http", oder "http://www.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="c5463-127">The value for the `prefix` attribute should be the leading characters of a valid URI --for example, "http", or "http://www.contoso.com".</span></span>  
  
 <span data-ttu-id="c5463-128">Der Wert für die `type` Attribut muss eine gültige Typnamen und die entsprechenden Assemblynamen an, die durch ein Komma getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="c5463-128">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma .</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c5463-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="c5463-129">Configuration Files</span></span>  
 <span data-ttu-id="c5463-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c5463-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5463-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5463-131">Example</span></span>  
 <span data-ttu-id="c5463-132">Das folgende Beispiel registriert ein benutzerdefiniertes Web-Request-Modul für HTTP.</span><span class="sxs-lookup"><span data-stu-id="c5463-132">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="c5463-133">Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c5463-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c5463-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5463-134">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="c5463-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c5463-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
