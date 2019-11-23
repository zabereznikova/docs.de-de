---
title: <defaultProxy>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 0945629c1395917bc1cf825f2ba84d20afa99957
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698206"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="179b3-102">\<defaultProxy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="179b3-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="179b3-103">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="179b3-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[<span data-ttu-id="179b3-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="179b3-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="179b3-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="179b3-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="179b3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultProxy >**</span><span class="sxs-lookup"><span data-stu-id="179b3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="179b3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="179b3-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="179b3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="179b3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="179b3-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="179b3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="179b3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="179b3-110">Attributes</span></span>  
  
|<span data-ttu-id="179b3-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="179b3-111">**Element**</span></span>|<span data-ttu-id="179b3-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="179b3-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="179b3-113">Gibt an, ob ein Webproxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="179b3-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="179b3-114">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="179b3-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="179b3-115">Gibt an, ob die Standardanmeldeinformationen für diesen Host für den Zugriff auf den Webproxy verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="179b3-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="179b3-116">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="179b3-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="179b3-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="179b3-117">Child Elements</span></span>  
  
|<span data-ttu-id="179b3-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="179b3-118">**Element**</span></span>|<span data-ttu-id="179b3-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="179b3-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="179b3-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="179b3-120">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="179b3-121">Gibt einen Satz von regulären Ausdrücken zur Beschreibung der Adressen an, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="179b3-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="179b3-122">module</span><span class="sxs-lookup"><span data-stu-id="179b3-122">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="179b3-123">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="179b3-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="179b3-124">proxy</span><span class="sxs-lookup"><span data-stu-id="179b3-124">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="179b3-125">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="179b3-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="179b3-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="179b3-126">Parent Elements</span></span>  
  
|<span data-ttu-id="179b3-127">**Element**</span><span class="sxs-lookup"><span data-stu-id="179b3-127">**Element**</span></span>|<span data-ttu-id="179b3-128">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="179b3-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="179b3-129">system.net</span><span class="sxs-lookup"><span data-stu-id="179b3-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="179b3-130">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="179b3-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="179b3-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="179b3-131">Remarks</span></span>  
 <span data-ttu-id="179b3-132">Wenn das defaultProxy-Element leer ist, werden die Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="179b3-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="179b3-133">Dieses Verhalten unterscheidet sich von .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="179b3-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="179b3-134">Eine Ausnahme wird ausgelöst, wenn das [Modul](module-element-network-settings.md) Element einen nicht öffentlichen Typ angibt, der Typ nicht von der <xref:System.Net.IWebProxy> Klasse abgeleitet wird, eine Ausnahme vom Parameter losen Konstruktor dieses Objekts aufgetreten ist oder beim Abrufen des vom System angegebenen Standard Proxys eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="179b3-134">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="179b3-135">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="179b3-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="179b3-136">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="179b3-136">Configuration Files</span></span>  
 <span data-ttu-id="179b3-137">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="179b3-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="179b3-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="179b3-138">Example</span></span>  
 <span data-ttu-id="179b3-139">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff und contoso.com umgangen.</span><span class="sxs-lookup"><span data-stu-id="179b3-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="179b3-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="179b3-140">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="179b3-141">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="179b3-141">Network Settings Schema</span></span>](index.md)
