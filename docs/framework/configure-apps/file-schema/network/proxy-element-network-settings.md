---
title: <proxy>-Element (Netzwerkeinstellungen)
description: Das <proxy> Netzwerk Einstellungs Element definiert die Proxy Serveroptionen in der .NET Framework. Dieser Artikel enthält ein Beispiel.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 0d462fcc92fc1be5ddbc2e76237d8436219c7295
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504536"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="76dbe-104">\<proxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="76dbe-104">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="76dbe-105">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="76dbe-105">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="76dbe-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="76dbe-106">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76dbe-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="76dbe-107">Attributes and Elements</span></span>  
 <span data-ttu-id="76dbe-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76dbe-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76dbe-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="76dbe-109">Attributes</span></span>  
  
|<span data-ttu-id="76dbe-110">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="76dbe-110">**Attribute**</span></span>|<span data-ttu-id="76dbe-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="76dbe-111">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="76dbe-112">Gibt an, ob der Proxy automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="76dbe-112">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="76dbe-113">Der Standardwert lautet `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="76dbe-113">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="76dbe-114">Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="76dbe-114">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="76dbe-115">Lokale Ressourcen umfassen den lokalen Server ( `http://localhost` , `http://loopback` oder `http://127.0.0.1` ) und einen URI ohne einen Punkt ( `http://webserver` ).</span><span class="sxs-lookup"><span data-stu-id="76dbe-115">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="76dbe-116">Der Standardwert lautet `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="76dbe-116">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="76dbe-117">Gibt den zu verwendenden Proxy-URI an.</span><span class="sxs-lookup"><span data-stu-id="76dbe-117">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="76dbe-118">Gibt den Speicherort des Konfigurations Skripts an.</span><span class="sxs-lookup"><span data-stu-id="76dbe-118">Specifies the location of the configuration script.</span></span> <span data-ttu-id="76dbe-119">Verwenden Sie das- `bypassonlocal` Attribut nicht mit diesem Attribut.</span><span class="sxs-lookup"><span data-stu-id="76dbe-119">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="76dbe-120">Gibt an, ob Internet Explorer-Proxy Einstellungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="76dbe-120">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="76dbe-121">Wenn diese Einstellung auf festgelegt `true` ist, überschreiben nachfolgende Attribute Internet Explorer-Proxy Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="76dbe-121">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="76dbe-122">Der Standardwert lautet `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="76dbe-122">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76dbe-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76dbe-123">Child Elements</span></span>  
 <span data-ttu-id="76dbe-124">Keine</span><span class="sxs-lookup"><span data-stu-id="76dbe-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76dbe-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76dbe-125">Parent Elements</span></span>  
  
|<span data-ttu-id="76dbe-126">**Element**</span><span class="sxs-lookup"><span data-stu-id="76dbe-126">**Element**</span></span>|<span data-ttu-id="76dbe-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="76dbe-127">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="76dbe-128">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="76dbe-128">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="76dbe-129">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="76dbe-129">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="76dbe-130">Textwert</span><span class="sxs-lookup"><span data-stu-id="76dbe-130">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76dbe-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="76dbe-131">Remarks</span></span>  
 <span data-ttu-id="76dbe-132">Das- `proxy` Element definiert einen Proxy Server für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="76dbe-132">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="76dbe-133">Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet das .NET Framework die Proxy Einstellungen in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="76dbe-133">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="76dbe-134">Der Wert für das- `proxyaddress` Attribut muss ein wohlgeformter URI (Uniform Resource Indicator) sein.</span><span class="sxs-lookup"><span data-stu-id="76dbe-134">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="76dbe-135">Das- `scriptLocation` Attribut verweist auf die automatische Erkennung von Proxy Konfigurations Skripts.</span><span class="sxs-lookup"><span data-stu-id="76dbe-135">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="76dbe-136">Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (in der Regel mit dem Namen "WPAD. dat") zu suchen, wenn die Option " **Automatisches Konfigurationsskript verwenden** " in Internet Explorer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="76dbe-136">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="76dbe-137">Wenn `bypassonlocal` auf einen beliebigen Wert festgelegt ist, `scriptLocation` wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="76dbe-137">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="76dbe-138">Verwenden Sie das- `usesystemdefault` Attribut für .NET Framework Anwendungen der Version 1,1, die zu Version 2,0 migrieren.</span><span class="sxs-lookup"><span data-stu-id="76dbe-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="76dbe-139">Eine-Ausnahme wird ausgelöst, wenn das- `proxyaddress` Attribut einen ungültigen Standard Proxy angibt.</span><span class="sxs-lookup"><span data-stu-id="76dbe-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="76dbe-140">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="76dbe-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="76dbe-141">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="76dbe-141">Configuration Files</span></span>  
 <span data-ttu-id="76dbe-142">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76dbe-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76dbe-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76dbe-143">Example</span></span>  
 <span data-ttu-id="76dbe-144">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff umgangen.</span><span class="sxs-lookup"><span data-stu-id="76dbe-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76dbe-145">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="76dbe-145">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="76dbe-146">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="76dbe-146">Network Settings Schema</span></span>](index.md)
