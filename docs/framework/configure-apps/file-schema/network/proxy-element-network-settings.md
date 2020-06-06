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
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154789"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="8f5d1-102">\<proxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8f5d1-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="8f5d1-103">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-103">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="8f5d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f5d1-104">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f5d1-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8f5d1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8f5d1-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f5d1-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="8f5d1-107">Attributes</span></span>  
  
|<span data-ttu-id="8f5d1-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="8f5d1-108">**Attribute**</span></span>|<span data-ttu-id="8f5d1-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8f5d1-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="8f5d1-110">Gibt an, ob der Proxy automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-110">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="8f5d1-111">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-111">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="8f5d1-112">Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-112">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="8f5d1-113">Lokale Ressourcen umfassen den lokalen Server ( `http://localhost` , `http://loopback` oder `http://127.0.0.1` ) und einen URI ohne einen Punkt ( `http://webserver` ).</span><span class="sxs-lookup"><span data-stu-id="8f5d1-113">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="8f5d1-114">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-114">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="8f5d1-115">Gibt den zu verwendenden Proxy-URI an.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-115">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="8f5d1-116">Gibt den Speicherort des Konfigurations Skripts an.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-116">Specifies the location of the configuration script.</span></span> <span data-ttu-id="8f5d1-117">Verwenden Sie das- `bypassonlocal` Attribut nicht mit diesem Attribut.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-117">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="8f5d1-118">Gibt an, ob Internet Explorer-Proxy Einstellungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-118">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="8f5d1-119">Wenn diese Einstellung auf festgelegt `true` ist, überschreiben nachfolgende Attribute Internet Explorer-Proxy Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-119">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="8f5d1-120">Der Standardwert ist `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-120">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f5d1-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f5d1-121">Child Elements</span></span>  
 <span data-ttu-id="8f5d1-122">Keine</span><span class="sxs-lookup"><span data-stu-id="8f5d1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f5d1-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f5d1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8f5d1-124">**Element**</span><span class="sxs-lookup"><span data-stu-id="8f5d1-124">**Element**</span></span>|<span data-ttu-id="8f5d1-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8f5d1-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8f5d1-126">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="8f5d1-126">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="8f5d1-127">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="8f5d1-127">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="8f5d1-128">Textwert</span><span class="sxs-lookup"><span data-stu-id="8f5d1-128">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f5d1-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8f5d1-129">Remarks</span></span>  
 <span data-ttu-id="8f5d1-130">Das- `proxy` Element definiert einen Proxy Server für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-130">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="8f5d1-131">Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet das .NET Framework die Proxy Einstellungen in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-131">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="8f5d1-132">Der Wert für das- `proxyaddress` Attribut muss ein wohlgeformter URI (Uniform Resource Indicator) sein.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-132">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="8f5d1-133">Das- `scriptLocation` Attribut verweist auf die automatische Erkennung von Proxy Konfigurations Skripts.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-133">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="8f5d1-134">Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (in der Regel mit dem Namen "WPAD. dat") zu suchen, wenn die Option " **Automatisches Konfigurationsskript verwenden** " in Internet Explorer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-134">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="8f5d1-135">Wenn `bypassonlocal` auf einen beliebigen Wert festgelegt ist, `scriptLocation` wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-135">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="8f5d1-136">Verwenden Sie das- `usesystemdefault` Attribut für .NET Framework Anwendungen der Version 1,1, die zu Version 2,0 migrieren.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-136">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="8f5d1-137">Eine-Ausnahme wird ausgelöst, wenn das- `proxyaddress` Attribut einen ungültigen Standard Proxy angibt.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-137">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="8f5d1-138">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-138">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8f5d1-139">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8f5d1-139">Configuration Files</span></span>  
 <span data-ttu-id="8f5d1-140">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-140">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f5d1-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f5d1-141">Example</span></span>  
 <span data-ttu-id="8f5d1-142">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff umgangen.</span><span class="sxs-lookup"><span data-stu-id="8f5d1-142">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f5d1-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f5d1-143">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="8f5d1-144">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="8f5d1-144">Network Settings Schema</span></span>](index.md)
