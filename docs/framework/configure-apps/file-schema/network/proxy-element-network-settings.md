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
ms.openlocfilehash: 8ae30b8c29dcf3aaa183ff295c7ee8592322797f
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141780"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="7c763-104">\<proxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7c763-104">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="7c763-105">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="7c763-105">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="7c763-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c763-106">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="True|False|Unspecified"
  bypassonlocal="True|False|Unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="True|False|Unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c763-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7c763-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7c763-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c763-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c763-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="7c763-109">Attributes</span></span>  
  
|<span data-ttu-id="7c763-110">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="7c763-110">**Attribute**</span></span>|<span data-ttu-id="7c763-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7c763-111">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="7c763-112">Gibt an, ob der Proxy automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="7c763-112">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="7c763-113">Der Standardwert ist `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="7c763-113">The default value is `Unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="7c763-114">Gibt an, ob der Proxy für lokale Ressourcen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="7c763-114">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="7c763-115">Lokale Ressourcen umfassen den lokalen Server ( `http://localhost` , `http://loopback` oder `http://127.0.0.1` ) und einen URI ohne einen Punkt ( `http://webserver` ).</span><span class="sxs-lookup"><span data-stu-id="7c763-115">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="7c763-116">Der Standardwert ist `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="7c763-116">The default value is `Unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="7c763-117">Gibt den zu verwendenden Proxy-URI an.</span><span class="sxs-lookup"><span data-stu-id="7c763-117">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="7c763-118">Gibt den Speicherort des Konfigurations Skripts an.</span><span class="sxs-lookup"><span data-stu-id="7c763-118">Specifies the location of the configuration script.</span></span> <span data-ttu-id="7c763-119">Verwenden Sie das- `bypassonlocal` Attribut nicht mit diesem Attribut.</span><span class="sxs-lookup"><span data-stu-id="7c763-119">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="7c763-120">Gibt an, ob Internet Explorer-Proxy Einstellungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7c763-120">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="7c763-121">Wenn diese Einstellung auf festgelegt `True` ist, überschreiben nachfolgende Attribute Internet Explorer-Proxy Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7c763-121">If set to `True`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="7c763-122">Der Standardwert ist `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="7c763-122">The default value is `Unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c763-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c763-123">Child Elements</span></span>  
 <span data-ttu-id="7c763-124">Keine</span><span class="sxs-lookup"><span data-stu-id="7c763-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c763-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c763-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7c763-126">**Element**</span><span class="sxs-lookup"><span data-stu-id="7c763-126">**Element**</span></span>|<span data-ttu-id="7c763-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7c763-127">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7c763-128">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="7c763-128">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="7c763-129">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="7c763-129">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="7c763-130">Textwert</span><span class="sxs-lookup"><span data-stu-id="7c763-130">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c763-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c763-131">Remarks</span></span>  
 <span data-ttu-id="7c763-132">Das- `proxy` Element definiert einen Proxy Server für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7c763-132">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="7c763-133">Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet das .NET Framework die Proxy Einstellungen in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="7c763-133">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="7c763-134">Der Wert für das- `proxyaddress` Attribut muss ein wohlgeformter URI (Uniform Resource Indicator) sein.</span><span class="sxs-lookup"><span data-stu-id="7c763-134">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="7c763-135">Das- `scriptLocation` Attribut verweist auf die automatische Erkennung von Proxy Konfigurations Skripts.</span><span class="sxs-lookup"><span data-stu-id="7c763-135">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="7c763-136">Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (in der Regel mit dem Namen "WPAD. dat") zu suchen, wenn die Option " **Automatisches Konfigurationsskript verwenden** " in Internet Explorer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="7c763-136">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="7c763-137">Wenn `bypassonlocal` auf einen beliebigen Wert festgelegt ist, `scriptLocation` wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7c763-137">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="7c763-138">Verwenden Sie das- `usesystemdefault` Attribut für .NET Framework Anwendungen der Version 1,1, die zu Version 2,0 migrieren.</span><span class="sxs-lookup"><span data-stu-id="7c763-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="7c763-139">Eine-Ausnahme wird ausgelöst, wenn das- `proxyaddress` Attribut einen ungültigen Standard Proxy angibt.</span><span class="sxs-lookup"><span data-stu-id="7c763-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="7c763-140">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="7c763-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7c763-141">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="7c763-141">Configuration Files</span></span>  
 <span data-ttu-id="7c763-142">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c763-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c763-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c763-143">Example</span></span>  
 <span data-ttu-id="7c763-144">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff umgangen.</span><span class="sxs-lookup"><span data-stu-id="7c763-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c763-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c763-145">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="7c763-146">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="7c763-146">Network Settings Schema</span></span>](index.md)
