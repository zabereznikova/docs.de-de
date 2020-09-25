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
ms.openlocfilehash: 806a30a52219ef9185f84a650d6a8eef8fb0dc8c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190305"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="ba586-103">\<defaultProxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ba586-103">\<defaultProxy> Element (Network Settings)</span></span>

<span data-ttu-id="ba586-104">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="ba586-104">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="ba586-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba586-105">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="True|False"  
  useDefaultCredentials="True|False">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba586-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba586-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ba586-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba586-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba586-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba586-108">Attributes</span></span>  
  
|<span data-ttu-id="ba586-109">**Element**</span><span class="sxs-lookup"><span data-stu-id="ba586-109">**Element**</span></span>|<span data-ttu-id="ba586-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ba586-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="ba586-111">Gibt an, ob ein Webproxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba586-111">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="ba586-112">Standardwert: `True`.</span><span class="sxs-lookup"><span data-stu-id="ba586-112">The default value is `True`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="ba586-113">Gibt an, ob die Standardanmeldeinformationen für diesen Host für den Zugriff auf den Webproxy verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba586-113">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="ba586-114">Standardwert: `False`.</span><span class="sxs-lookup"><span data-stu-id="ba586-114">The default value is `False`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba586-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba586-115">Child Elements</span></span>  
  
|<span data-ttu-id="ba586-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="ba586-116">**Element**</span></span>|<span data-ttu-id="ba586-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ba586-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba586-118">bypasslist</span><span class="sxs-lookup"><span data-stu-id="ba586-118">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="ba586-119">Gibt einen Satz von regulären Ausdrücken zur Beschreibung der Adressen an, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba586-119">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="ba586-120">Mond</span><span class="sxs-lookup"><span data-stu-id="ba586-120">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="ba586-121">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="ba586-121">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="ba586-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="ba586-122">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="ba586-123">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="ba586-123">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba586-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba586-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ba586-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="ba586-125">**Element**</span></span>|<span data-ttu-id="ba586-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ba586-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba586-127">system.net</span><span class="sxs-lookup"><span data-stu-id="ba586-127">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="ba586-128">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ba586-128">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba586-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ba586-129">Remarks</span></span>  

 <span data-ttu-id="ba586-130">Wenn das defaultProxy-Element leer ist, werden die Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba586-130">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="ba586-131">Dieses Verhalten unterscheidet sich von .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="ba586-131">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ba586-132">Eine-Ausnahme wird ausgelöst, wenn das [Module](module-element-network-settings.md) -Element einen nicht öffentlichen Typ angibt, der Typ nicht von der-Klasse abgeleitet wird <xref:System.Net.IWebProxy> , eine Ausnahme vom Parameter losen Konstruktor dieses Objekts aufgetreten ist oder beim Abrufen des vom System angegebenen Standard Proxys eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ba586-132">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="ba586-133">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="ba586-133">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ba586-134">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="ba586-134">Configuration Files</span></span>  

 <span data-ttu-id="ba586-135">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba586-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba586-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba586-136">Example</span></span>  

 <span data-ttu-id="ba586-137">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff und contoso.com umgangen.</span><span class="sxs-lookup"><span data-stu-id="ba586-137">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba586-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba586-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="ba586-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ba586-139">Network Settings Schema</span></span>](index.md)
