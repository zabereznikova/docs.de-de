---
title: '&lt;Proxy&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f4ab3d4e7ce6686a43e4c5258a56e72203c38ebd
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033388"
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="00eff-102">&lt;Proxy&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="00eff-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="00eff-103">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="00eff-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="00eff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="00eff-104">\<configuration></span></span>  
<span data-ttu-id="00eff-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="00eff-105">\<system.net></span></span>  
<span data-ttu-id="00eff-106">\<DefaultProxy ></span><span class="sxs-lookup"><span data-stu-id="00eff-106">\<defaultProxy></span></span>  
<span data-ttu-id="00eff-107">\<Proxy ></span><span class="sxs-lookup"><span data-stu-id="00eff-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00eff-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="00eff-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00eff-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00eff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="00eff-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00eff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00eff-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="00eff-111">Attributes</span></span>  
  
|<span data-ttu-id="00eff-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="00eff-112">**Attribute**</span></span>|<span data-ttu-id="00eff-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="00eff-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="00eff-114">Gibt an, ob der Proxy automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="00eff-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="00eff-115">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="00eff-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="00eff-116">Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="00eff-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="00eff-117">Lokale Ressourcen schließen Sie den lokalen Server (`http://localhost`, `http://loopback`, oder `http://127.0.0.1`) und einen URI ohne einen Punkt (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="00eff-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="00eff-118">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="00eff-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="00eff-119">Gibt an, den Proxy-URI verwenden.</span><span class="sxs-lookup"><span data-stu-id="00eff-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="00eff-120">Gibt den Speicherort des Konfigurationsskripts.</span><span class="sxs-lookup"><span data-stu-id="00eff-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="00eff-121">Verwenden Sie nicht die `bypassonlocal` Attribut mit diesem Attribut.</span><span class="sxs-lookup"><span data-stu-id="00eff-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="00eff-122">Gibt an, ob Internet Explorer-Proxyeinstellungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="00eff-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="00eff-123">Wenn auf festgelegt `true`, aufeinanderfolgenden Attributen werden Internet Explorer-Proxy-Einstellungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="00eff-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="00eff-124">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="00eff-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00eff-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00eff-125">Child Elements</span></span>  
 <span data-ttu-id="00eff-126">Keine</span><span class="sxs-lookup"><span data-stu-id="00eff-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00eff-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00eff-127">Parent Elements</span></span>  
  
|<span data-ttu-id="00eff-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="00eff-128">**Element**</span></span>|<span data-ttu-id="00eff-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="00eff-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="00eff-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="00eff-130">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="00eff-131">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="00eff-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="00eff-132">Textwert</span><span class="sxs-lookup"><span data-stu-id="00eff-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00eff-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00eff-133">Remarks</span></span>  
 <span data-ttu-id="00eff-134">Die `proxy` -Element definiert einen Proxyserver für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="00eff-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="00eff-135">Wenn dieses Element aus der Konfigurationsdatei fehlt, wird .NET Framework die Proxyeinstellungen in Internet Explorer verwenden.</span><span class="sxs-lookup"><span data-stu-id="00eff-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="00eff-136">Der Wert für die `proxyaddress` Attribut sollte eine wohlgeformte Uniform Resource Indicator (URI) sein.</span><span class="sxs-lookup"><span data-stu-id="00eff-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="00eff-137">Die `scriptLocation` -Attribut verweist auf die automatische Erkennung von Proxy-Konfigurationsskripts.</span><span class="sxs-lookup"><span data-stu-id="00eff-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="00eff-138">Die <xref:System.Net.WebProxy> -Klasse versucht, ein Konfigurationsskript (üblicherweise Wpad.dat) beim Suchen der **Automatisches Konfigurationsskript verwenden** in Internet Explorer die Option ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="00eff-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="00eff-139">Wenn `bypassonlocal` festgelegt ist, auf einen beliebigen Wert, `scriptLocation` wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="00eff-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="00eff-140">Verwenden der `usesystemdefault` -Attribut für .NET Framework Version 1.1-Anwendungen, die auf Version 2.0 migrieren.</span><span class="sxs-lookup"><span data-stu-id="00eff-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="00eff-141">Eine Ausnahme wird ausgelöst, wenn die `proxyaddress` -Attribut gibt einen ungültigen Standardproxy an.</span><span class="sxs-lookup"><span data-stu-id="00eff-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="00eff-142">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="00eff-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="00eff-143">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="00eff-143">Configuration Files</span></span>  
 <span data-ttu-id="00eff-144">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00eff-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00eff-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00eff-145">Example</span></span>  
 <span data-ttu-id="00eff-146">Das folgende Beispiel verwendet die Standardeinstellungen des Internet Explorer-Proxys, gibt die Proxyadresse und umgeht den Proxy für den lokalen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="00eff-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00eff-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00eff-147">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="00eff-148">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="00eff-148">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
