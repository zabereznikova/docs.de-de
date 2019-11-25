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
ms.openlocfilehash: 5f327a2bb4fe316497614f14669907d514c20654
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089189"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="a15cc-102">\<Proxy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a15cc-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="a15cc-103">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="a15cc-103">Defines a proxy server.</span></span>  

<span data-ttu-id="a15cc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a15cc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a15cc-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a15cc-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="a15cc-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a15cc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="a15cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Proxy >**</span><span class="sxs-lookup"><span data-stu-id="a15cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a15cc-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a15cc-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a15cc-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a15cc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a15cc-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a15cc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a15cc-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a15cc-111">Attributes</span></span>  
  
|<span data-ttu-id="a15cc-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="a15cc-112">**Attribute**</span></span>|<span data-ttu-id="a15cc-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a15cc-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="a15cc-114">Gibt an, ob der Proxy automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="a15cc-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="a15cc-115">Der Standardwert ist `unspecified`sein.</span><span class="sxs-lookup"><span data-stu-id="a15cc-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="a15cc-116">Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="a15cc-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="a15cc-117">Lokale Ressourcen umfassen den lokalen Server (`http://localhost`, `http://loopback`oder `http://127.0.0.1`) und einen URI ohne einen Punkt (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="a15cc-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="a15cc-118">Der Standardwert ist `unspecified`sein.</span><span class="sxs-lookup"><span data-stu-id="a15cc-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="a15cc-119">Gibt den zu verwendenden Proxy-URI an.</span><span class="sxs-lookup"><span data-stu-id="a15cc-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="a15cc-120">Gibt den Speicherort des Konfigurations Skripts an.</span><span class="sxs-lookup"><span data-stu-id="a15cc-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="a15cc-121">Verwenden Sie das `bypassonlocal`-Attribut nicht mit diesem Attribut.</span><span class="sxs-lookup"><span data-stu-id="a15cc-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="a15cc-122">Gibt an, ob Internet Explorer-Proxy Einstellungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a15cc-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="a15cc-123">Wenn `true`festgelegt ist, überschreiben nachfolgende Attribute die Internet Explorer-Proxy Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a15cc-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="a15cc-124">Der Standardwert ist `unspecified`sein.</span><span class="sxs-lookup"><span data-stu-id="a15cc-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a15cc-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a15cc-125">Child Elements</span></span>  
 <span data-ttu-id="a15cc-126">Keine</span><span class="sxs-lookup"><span data-stu-id="a15cc-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a15cc-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a15cc-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a15cc-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="a15cc-128">**Element**</span></span>|<span data-ttu-id="a15cc-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a15cc-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a15cc-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="a15cc-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="a15cc-131">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="a15cc-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="a15cc-132">Textwert</span><span class="sxs-lookup"><span data-stu-id="a15cc-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a15cc-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a15cc-133">Remarks</span></span>  
 <span data-ttu-id="a15cc-134">Das `proxy`-Element definiert einen Proxy Server für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a15cc-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="a15cc-135">Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet das .NET Framework die Proxy Einstellungen in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a15cc-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="a15cc-136">Der Wert für das `proxyaddress`-Attribut sollte ein wohlgeformter URI (Uniform Resource Indicator) sein.</span><span class="sxs-lookup"><span data-stu-id="a15cc-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="a15cc-137">Das `scriptLocation`-Attribut verweist auf die automatische Erkennung von Proxy Konfigurations Skripts.</span><span class="sxs-lookup"><span data-stu-id="a15cc-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="a15cc-138">Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (in der Regel mit dem Namen "WPAD. dat") zu suchen, wenn die Option " **Automatisches Konfigurationsskript verwenden** " in Internet Explorer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a15cc-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="a15cc-139">Wenn `bypassonlocal` auf einen beliebigen Wert festgelegt ist, wird `scriptLocation` ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a15cc-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="a15cc-140">Verwenden Sie das `usesystemdefault`-Attribut für Anwendungen .NET Framework Version 1,1, die zu Version 2,0 migrieren.</span><span class="sxs-lookup"><span data-stu-id="a15cc-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="a15cc-141">Eine Ausnahme wird ausgelöst, wenn das `proxyaddress`-Attribut einen ungültigen Standard Proxy angibt.</span><span class="sxs-lookup"><span data-stu-id="a15cc-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="a15cc-142">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="a15cc-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a15cc-143">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a15cc-143">Configuration Files</span></span>  
 <span data-ttu-id="a15cc-144">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a15cc-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a15cc-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a15cc-145">Example</span></span>  
 <span data-ttu-id="a15cc-146">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff umgangen.</span><span class="sxs-lookup"><span data-stu-id="a15cc-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a15cc-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a15cc-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="a15cc-148">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a15cc-148">Network Settings Schema</span></span>](index.md)
