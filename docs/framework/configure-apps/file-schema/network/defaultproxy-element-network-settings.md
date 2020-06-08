---
title: <defaultProxy>-Element (Netzwerkeinstellungen)
description: <defaultProxy>Mit dem Netzwerk Einstellungs Element wird der HTTP-Proxy Server (Hypertext Transfer Protocol) im .NET Framework konfiguriert.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 915fdc96dbd4d417f9c9e6aa3ff96de3026491ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504601"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="762be-103">\<defaultProxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="762be-103">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="762be-104">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="762be-104">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="762be-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="762be-105">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="762be-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="762be-106">Attributes and Elements</span></span>  
 <span data-ttu-id="762be-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="762be-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="762be-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="762be-108">Attributes</span></span>  
  
|<span data-ttu-id="762be-109">**Element**</span><span class="sxs-lookup"><span data-stu-id="762be-109">**Element**</span></span>|<span data-ttu-id="762be-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="762be-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="762be-111">Gibt an, ob ein Webproxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="762be-111">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="762be-112">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="762be-112">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="762be-113">Gibt an, ob die Standardanmeldeinformationen für diesen Host für den Zugriff auf den Webproxy verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="762be-113">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="762be-114">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="762be-114">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="762be-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="762be-115">Child Elements</span></span>  
  
|<span data-ttu-id="762be-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="762be-116">**Element**</span></span>|<span data-ttu-id="762be-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="762be-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="762be-118">bypasslist</span><span class="sxs-lookup"><span data-stu-id="762be-118">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="762be-119">Gibt einen Satz von regulären Ausdrücken zur Beschreibung der Adressen an, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="762be-119">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="762be-120">Mond</span><span class="sxs-lookup"><span data-stu-id="762be-120">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="762be-121">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="762be-121">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="762be-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="762be-122">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="762be-123">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="762be-123">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="762be-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="762be-124">Parent Elements</span></span>  
  
|<span data-ttu-id="762be-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="762be-125">**Element**</span></span>|<span data-ttu-id="762be-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="762be-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="762be-127">system.net</span><span class="sxs-lookup"><span data-stu-id="762be-127">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="762be-128">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="762be-128">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="762be-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="762be-129">Remarks</span></span>  
 <span data-ttu-id="762be-130">Wenn das defaultProxy-Element leer ist, werden die Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="762be-130">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="762be-131">Dieses Verhalten unterscheidet sich von .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="762be-131">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="762be-132">Eine-Ausnahme wird ausgelöst, wenn das [Module](module-element-network-settings.md) -Element einen nicht öffentlichen Typ angibt, der Typ nicht von der-Klasse abgeleitet wird <xref:System.Net.IWebProxy> , eine Ausnahme vom Parameter losen Konstruktor dieses Objekts aufgetreten ist oder beim Abrufen des vom System angegebenen Standard Proxys eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="762be-132">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="762be-133">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="762be-133">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="762be-134">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="762be-134">Configuration Files</span></span>  
 <span data-ttu-id="762be-135">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="762be-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="762be-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="762be-136">Example</span></span>  
 <span data-ttu-id="762be-137">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff und contoso.com umgangen.</span><span class="sxs-lookup"><span data-stu-id="762be-137">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="762be-138">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="762be-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="762be-139">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="762be-139">Network Settings Schema</span></span>](index.md)
