---
title: '&lt;Proxy&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7178527f369c698b0ab53aa41cb28dd0126436b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="04a49-102">&lt;Proxy&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="04a49-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="04a49-103">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="04a49-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="04a49-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="04a49-104">\<configuration></span></span>  
<span data-ttu-id="04a49-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="04a49-105">\<system.net></span></span>  
<span data-ttu-id="04a49-106">\<DefaultProxy ></span><span class="sxs-lookup"><span data-stu-id="04a49-106">\<defaultProxy></span></span>  
<span data-ttu-id="04a49-107">\<Proxy ></span><span class="sxs-lookup"><span data-stu-id="04a49-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04a49-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="04a49-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04a49-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="04a49-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04a49-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="04a49-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04a49-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="04a49-111">Attributes</span></span>  
  
|<span data-ttu-id="04a49-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="04a49-112">**Attribute**</span></span>|<span data-ttu-id="04a49-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="04a49-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="04a49-114">Gibt an, ob der Proxy automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="04a49-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="04a49-115">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="04a49-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="04a49-116">Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="04a49-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="04a49-117">Lokale Ressourcen umfassen den lokalen Server (http://localhost, http://loopback oder http://127.0.0.1) und einen URI ohne einen Punkt (http://webserver).</span><span class="sxs-lookup"><span data-stu-id="04a49-117">Local resources include the local server (http://localhost, http://loopback, or http://127.0.0.1) and a URI without a period (http://webserver).</span></span> <span data-ttu-id="04a49-118">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="04a49-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="04a49-119">Gibt den Proxy-URI verwendet.</span><span class="sxs-lookup"><span data-stu-id="04a49-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="04a49-120">Gibt den Speicherort des Konfigurationsskripts.</span><span class="sxs-lookup"><span data-stu-id="04a49-120">Specifies the location of the configuration script.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="04a49-121">Gibt an, ob Internet Explorer-Proxyeinstellungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="04a49-121">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="04a49-122">Wenn auf festgelegt `true`, überschreiben nachfolgende Attribute die Proxyeinstellungen in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="04a49-122">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="04a49-123">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="04a49-123">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04a49-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04a49-124">Child Elements</span></span>  
 <span data-ttu-id="04a49-125">Keine</span><span class="sxs-lookup"><span data-stu-id="04a49-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04a49-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04a49-126">Parent Elements</span></span>  
  
|<span data-ttu-id="04a49-127">**Element**</span><span class="sxs-lookup"><span data-stu-id="04a49-127">**Element**</span></span>|<span data-ttu-id="04a49-128">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="04a49-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="04a49-129">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="04a49-129">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="04a49-130">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="04a49-130">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="04a49-131">Textwert</span><span class="sxs-lookup"><span data-stu-id="04a49-131">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04a49-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04a49-132">Remarks</span></span>  
 <span data-ttu-id="04a49-133">Die `proxy` -Element definiert einen Proxyserver für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="04a49-133">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="04a49-134">Wenn dieses Element aus der Konfigurationsdatei nicht vorhanden ist, wird .NET Framework die Proxyeinstellungen in Internet Explorer verwenden.</span><span class="sxs-lookup"><span data-stu-id="04a49-134">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="04a49-135">Der Wert für die `proxyaddress` Attribut muss eine wohlgeformte Uniform Resource Indicator (URI).</span><span class="sxs-lookup"><span data-stu-id="04a49-135">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="04a49-136">Die `scriptLocation` Attribut bezieht sich auf die automatische Erkennung von Proxy-Konfigurationsskripts.</span><span class="sxs-lookup"><span data-stu-id="04a49-136">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="04a49-137">Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (üblicherweise Wpad.dat) beim Suchen der **Automatisches Konfigurationsskript verwenden** in Internet Explorer die Option ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="04a49-137">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span>  
  
 <span data-ttu-id="04a49-138">Verwenden der `usesystemdefault` Attribut für .NET Framework Version 1.1-Clientanwendungen, die für Version 2.0 migrieren.</span><span class="sxs-lookup"><span data-stu-id="04a49-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="04a49-139">Eine Ausnahme wird ausgelöst, wenn die `proxyaddress` Attribut gibt eine ungültige Standardproxy an.</span><span class="sxs-lookup"><span data-stu-id="04a49-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="04a49-140">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="04a49-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="04a49-141">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="04a49-141">Configuration Files</span></span>  
 <span data-ttu-id="04a49-142">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04a49-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04a49-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04a49-143">Example</span></span>  
 <span data-ttu-id="04a49-144">Das folgende Beispiel verwendet die Standardeinstellungen des Internet Explorer-Proxys, gibt die Adresse des Proxyservers an und umgeht den Proxy für den lokalen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="04a49-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="04a49-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04a49-145">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="04a49-146">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="04a49-146">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
