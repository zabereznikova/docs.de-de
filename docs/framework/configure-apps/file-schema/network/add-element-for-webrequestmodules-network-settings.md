---
title: "&lt;Hinzufügen&gt; WebRequestModules (Network Settings)-Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9b7d2c0f52ea42fcb98be149ab005cd67c2db46a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="27b17-102">&lt;Hinzufügen&gt; WebRequestModules (Network Settings)-Element</span><span class="sxs-lookup"><span data-stu-id="27b17-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="27b17-103">Fügt eine benutzerdefinierte Webmodul der Anforderung an die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="27b17-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="27b17-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="27b17-104">\<configuration></span></span>  
<span data-ttu-id="27b17-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="27b17-105">\<system.net></span></span>  
<span data-ttu-id="27b17-106">\<WebRequestModules ></span><span class="sxs-lookup"><span data-stu-id="27b17-106">\<webRequestModules></span></span>  
<span data-ttu-id="27b17-107">\<add></span><span class="sxs-lookup"><span data-stu-id="27b17-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27b17-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="27b17-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27b17-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="27b17-109">Attributes and Elements</span></span>  
 <span data-ttu-id="27b17-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27b17-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27b17-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="27b17-111">Attributes</span></span>  
  
|<span data-ttu-id="27b17-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="27b17-112">**Attribute**</span></span>|<span data-ttu-id="27b17-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="27b17-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="27b17-114">Das URI-Präfix für Anforderungen, die von dieser Anforderung Webmodul behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="27b17-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="27b17-115">Den vollqualifizierten Typnamen (erkennbar die <xref:System.Type.FullName%2A> Eigenschaft) und der Name der Assembly (angegeben durch die <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, die diese Web-Request-Modul implementiert.</span><span class="sxs-lookup"><span data-stu-id="27b17-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27b17-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="27b17-116">Child Elements</span></span>  
 <span data-ttu-id="27b17-117">Keine</span><span class="sxs-lookup"><span data-stu-id="27b17-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27b17-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="27b17-118">Parent Elements</span></span>  
  
|<span data-ttu-id="27b17-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="27b17-119">**Element**</span></span>|<span data-ttu-id="27b17-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="27b17-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="27b17-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="27b17-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="27b17-122">Gibt die Module zu verwenden, um Informationen von Netzwerkhosts anfordern.</span><span class="sxs-lookup"><span data-stu-id="27b17-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27b17-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27b17-123">Remarks</span></span>  
 <span data-ttu-id="27b17-124">Die `prefix` Attribut definiert die URI-Präfix, das das angegebene Modul der Web-Anforderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="27b17-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="27b17-125">Anforderung Webmodule werden in der Regel zum Behandeln eines bestimmten Protokolls, z. B. HTTP oder FTP, registriert, jedoch können registriert werden, um eine Anforderung für einen bestimmten Server oder einen Pfad auf einem Server zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="27b17-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="27b17-126">Die Anforderung Webmodul wird erstellt, wenn ein übereinstimmendes URI-Präfix an übergeben wird die <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="27b17-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="27b17-127">Der Wert für die `prefix` Attribut muss die ersten Zeichen ein gültiger URI – z. B. "http" oder "http://www.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="27b17-127">The value for the `prefix` attribute should be the leading characters of a valid URI --for example, "http", or "http://www.contoso.com".</span></span>  
  
 <span data-ttu-id="27b17-128">Der Wert für die `type` Attribut muss eine gültige Typnamen und die entsprechenden Assemblynamen an, die durch ein Komma getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="27b17-128">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma .</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="27b17-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="27b17-129">Configuration Files</span></span>  
 <span data-ttu-id="27b17-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27b17-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27b17-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27b17-131">Example</span></span>  
 <span data-ttu-id="27b17-132">Das folgende Beispiel registriert ein benutzerdefiniertes Web-Request-Modul für HTTP.</span><span class="sxs-lookup"><span data-stu-id="27b17-132">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="27b17-133">Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="27b17-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27b17-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27b17-134">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="27b17-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="27b17-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
