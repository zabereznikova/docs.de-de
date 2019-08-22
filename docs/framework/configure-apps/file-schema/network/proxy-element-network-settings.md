---
title: <proxy>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: a183c4160c4cd55b05c5c23f7a10e3a1d1c74ea4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659291"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="fe289-102">\<Proxy > Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="fe289-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="fe289-103">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="fe289-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="fe289-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fe289-104">\<configuration></span></span>  
<span data-ttu-id="fe289-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="fe289-105">\<system.net></span></span>  
<span data-ttu-id="fe289-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="fe289-106">\<defaultProxy></span></span>  
<span data-ttu-id="fe289-107">\<proxy></span><span class="sxs-lookup"><span data-stu-id="fe289-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe289-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe289-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe289-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe289-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fe289-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe289-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe289-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe289-111">Attributes</span></span>  
  
|<span data-ttu-id="fe289-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="fe289-112">**Attribute**</span></span>|<span data-ttu-id="fe289-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fe289-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="fe289-114">Gibt an, ob der Proxy automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="fe289-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="fe289-115">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="fe289-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="fe289-116">Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="fe289-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="fe289-117">Lokale Ressourcen umfassen den lokalen Server (`http://localhost`, `http://loopback`oder `http://127.0.0.1`) und einen URI ohne einen Punkt (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="fe289-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="fe289-118">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="fe289-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="fe289-119">Gibt den zu verwendenden Proxy-URI an.</span><span class="sxs-lookup"><span data-stu-id="fe289-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="fe289-120">Gibt den Speicherort des Konfigurations Skripts an.</span><span class="sxs-lookup"><span data-stu-id="fe289-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="fe289-121">Verwenden Sie das `bypassonlocal` -Attribut nicht mit diesem Attribut.</span><span class="sxs-lookup"><span data-stu-id="fe289-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="fe289-122">Gibt an, ob Internet Explorer-Proxy Einstellungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fe289-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="fe289-123">Wenn diese Einstellung `true`auf festgelegt ist, überschreiben nachfolgende Attribute Internet Explorer-Proxy Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="fe289-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="fe289-124">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="fe289-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe289-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe289-125">Child Elements</span></span>  
 <span data-ttu-id="fe289-126">Keine</span><span class="sxs-lookup"><span data-stu-id="fe289-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe289-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe289-127">Parent Elements</span></span>  
  
|<span data-ttu-id="fe289-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="fe289-128">**Element**</span></span>|<span data-ttu-id="fe289-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fe289-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fe289-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="fe289-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="fe289-131">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="fe289-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="fe289-132">Textwert</span><span class="sxs-lookup"><span data-stu-id="fe289-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe289-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe289-133">Remarks</span></span>  
 <span data-ttu-id="fe289-134">Das `proxy` -Element definiert einen Proxy Server für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fe289-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="fe289-135">Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet das .NET Framework die Proxy Einstellungen in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="fe289-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="fe289-136">Der Wert für das `proxyaddress` -Attribut muss ein wohlgeformter URI (Uniform Resource Indicator) sein.</span><span class="sxs-lookup"><span data-stu-id="fe289-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="fe289-137">Das `scriptLocation` -Attribut verweist auf die automatische Erkennung von Proxy Konfigurations Skripts.</span><span class="sxs-lookup"><span data-stu-id="fe289-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="fe289-138">Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (in der Regel mit dem Namen "WPAD. dat") zu suchen, wenn die Option " **Automatisches Konfigurationsskript verwenden** " in Internet Explorer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="fe289-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="fe289-139">Wenn `bypassonlocal` auf einen beliebigen Wert festgelegt `scriptLocation` ist, wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fe289-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="fe289-140">Verwenden Sie `usesystemdefault` das-Attribut für .NET Framework Anwendungen der Version 1,1, die zu Version 2,0 migrieren.</span><span class="sxs-lookup"><span data-stu-id="fe289-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="fe289-141">Eine-Ausnahme wird ausgelöst, `proxyaddress` wenn das-Attribut einen ungültigen Standard Proxy angibt.</span><span class="sxs-lookup"><span data-stu-id="fe289-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="fe289-142">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="fe289-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fe289-143">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="fe289-143">Configuration Files</span></span>  
 <span data-ttu-id="fe289-144">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe289-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe289-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe289-145">Example</span></span>  
 <span data-ttu-id="fe289-146">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff umgangen.</span><span class="sxs-lookup"><span data-stu-id="fe289-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe289-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe289-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="fe289-148">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="fe289-148">Network Settings Schema</span></span>](index.md)
