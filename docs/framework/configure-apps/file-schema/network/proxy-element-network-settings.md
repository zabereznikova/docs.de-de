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
manager: markl
ms.openlocfilehash: 5fba4bfa14642092dbb7c0153bcd92160a62b12b
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754628"
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="e89bd-102">&lt;Proxy&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e89bd-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e89bd-103">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="e89bd-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="e89bd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e89bd-104">\<configuration></span></span>  
<span data-ttu-id="e89bd-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e89bd-105">\<system.net></span></span>  
<span data-ttu-id="e89bd-106">\<DefaultProxy ></span><span class="sxs-lookup"><span data-stu-id="e89bd-106">\<defaultProxy></span></span>  
<span data-ttu-id="e89bd-107">\<Proxy ></span><span class="sxs-lookup"><span data-stu-id="e89bd-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e89bd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e89bd-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e89bd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e89bd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e89bd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e89bd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e89bd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e89bd-111">Attributes</span></span>  
  
|<span data-ttu-id="e89bd-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="e89bd-112">**Attribute**</span></span>|<span data-ttu-id="e89bd-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e89bd-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="e89bd-114">Gibt an, ob der Proxy automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="e89bd-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="e89bd-115">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="e89bd-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="e89bd-116">Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="e89bd-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="e89bd-117">Lokale Ressourcen schließen Sie den lokalen Server (`http://localhost`, `http://loopback`, oder `http://127.0.0.1`) und einen URI ohne einen Punkt (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="e89bd-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="e89bd-118">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="e89bd-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="e89bd-119">Gibt an, den Proxy-URI verwenden.</span><span class="sxs-lookup"><span data-stu-id="e89bd-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="e89bd-120">Gibt den Speicherort des Konfigurationsskripts.</span><span class="sxs-lookup"><span data-stu-id="e89bd-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="e89bd-121">Verwenden Sie nicht die `bypassonlocal` Attribut mit diesem Attribut.</span><span class="sxs-lookup"><span data-stu-id="e89bd-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="e89bd-122">Gibt an, ob Internet Explorer-Proxyeinstellungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e89bd-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="e89bd-123">Wenn auf festgelegt `true`, aufeinanderfolgenden Attributen werden Internet Explorer-Proxy-Einstellungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="e89bd-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="e89bd-124">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="e89bd-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e89bd-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e89bd-125">Child Elements</span></span>  
 <span data-ttu-id="e89bd-126">Keine</span><span class="sxs-lookup"><span data-stu-id="e89bd-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e89bd-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e89bd-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e89bd-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="e89bd-128">**Element**</span></span>|<span data-ttu-id="e89bd-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e89bd-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e89bd-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="e89bd-130">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="e89bd-131">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="e89bd-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="e89bd-132">Textwert</span><span class="sxs-lookup"><span data-stu-id="e89bd-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e89bd-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e89bd-133">Remarks</span></span>  
 <span data-ttu-id="e89bd-134">Die `proxy` -Element definiert einen Proxyserver für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e89bd-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="e89bd-135">Wenn dieses Element aus der Konfigurationsdatei fehlt, wird .NET Framework die Proxyeinstellungen in Internet Explorer verwenden.</span><span class="sxs-lookup"><span data-stu-id="e89bd-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="e89bd-136">Der Wert für die `proxyaddress` Attribut sollte eine wohlgeformte Uniform Resource Indicator (URI) sein.</span><span class="sxs-lookup"><span data-stu-id="e89bd-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="e89bd-137">Die `scriptLocation` -Attribut verweist auf die automatische Erkennung von Proxy-Konfigurationsskripts.</span><span class="sxs-lookup"><span data-stu-id="e89bd-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="e89bd-138">Die <xref:System.Net.WebProxy> -Klasse versucht, ein Konfigurationsskript (üblicherweise Wpad.dat) beim Suchen der **Automatisches Konfigurationsskript verwenden** in Internet Explorer die Option ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e89bd-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="e89bd-139">Wenn `bypassonlocal` festgelegt ist, auf einen beliebigen Wert, `scriptLocation` wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e89bd-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="e89bd-140">Verwenden der `usesystemdefault` -Attribut für .NET Framework Version 1.1-Anwendungen, die auf Version 2.0 migrieren.</span><span class="sxs-lookup"><span data-stu-id="e89bd-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="e89bd-141">Eine Ausnahme wird ausgelöst, wenn die `proxyaddress` -Attribut gibt einen ungültigen Standardproxy an.</span><span class="sxs-lookup"><span data-stu-id="e89bd-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="e89bd-142">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="e89bd-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e89bd-143">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="e89bd-143">Configuration Files</span></span>  
 <span data-ttu-id="e89bd-144">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e89bd-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e89bd-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e89bd-145">Example</span></span>  
 <span data-ttu-id="e89bd-146">Das folgende Beispiel verwendet die Standardeinstellungen des Internet Explorer-Proxys, gibt die Proxyadresse und umgeht den Proxy für den lokalen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="e89bd-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e89bd-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e89bd-147">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="e89bd-148">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e89bd-148">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
