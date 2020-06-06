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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698206"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="a67be-102">\<defaultProxy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a67be-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="a67be-103">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="a67be-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="a67be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a67be-104">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a67be-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a67be-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a67be-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a67be-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a67be-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="a67be-107">Attributes</span></span>  
  
|<span data-ttu-id="a67be-108">**Element**</span><span class="sxs-lookup"><span data-stu-id="a67be-108">**Element**</span></span>|<span data-ttu-id="a67be-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a67be-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="a67be-110">Gibt an, ob ein Webproxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a67be-110">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="a67be-111">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="a67be-111">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="a67be-112">Gibt an, ob die Standardanmeldeinformationen für diesen Host für den Zugriff auf den Webproxy verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a67be-112">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="a67be-113">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a67be-113">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a67be-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a67be-114">Child Elements</span></span>  
  
|<span data-ttu-id="a67be-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="a67be-115">**Element**</span></span>|<span data-ttu-id="a67be-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a67be-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a67be-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="a67be-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="a67be-118">Gibt einen Satz von regulären Ausdrücken zur Beschreibung der Adressen an, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="a67be-118">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="a67be-119">Mond</span><span class="sxs-lookup"><span data-stu-id="a67be-119">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="a67be-120">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="a67be-120">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="a67be-121">Proxy</span><span class="sxs-lookup"><span data-stu-id="a67be-121">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="a67be-122">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="a67be-122">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a67be-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a67be-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a67be-124">**Element**</span><span class="sxs-lookup"><span data-stu-id="a67be-124">**Element**</span></span>|<span data-ttu-id="a67be-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a67be-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a67be-126">system.net</span><span class="sxs-lookup"><span data-stu-id="a67be-126">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a67be-127">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a67be-127">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a67be-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a67be-128">Remarks</span></span>  
 <span data-ttu-id="a67be-129">Wenn das defaultProxy-Element leer ist, werden die Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="a67be-129">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="a67be-130">Dieses Verhalten unterscheidet sich von .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="a67be-130">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a67be-131">Eine-Ausnahme wird ausgelöst, wenn das [Module](module-element-network-settings.md) -Element einen nicht öffentlichen Typ angibt, der Typ nicht von der-Klasse abgeleitet wird <xref:System.Net.IWebProxy> , eine Ausnahme vom Parameter losen Konstruktor dieses Objekts aufgetreten ist oder beim Abrufen des vom System angegebenen Standard Proxys eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a67be-131">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="a67be-132">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="a67be-132">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a67be-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a67be-133">Configuration Files</span></span>  
 <span data-ttu-id="a67be-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a67be-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a67be-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a67be-135">Example</span></span>  
 <span data-ttu-id="a67be-136">Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff und contoso.com umgangen.</span><span class="sxs-lookup"><span data-stu-id="a67be-136">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a67be-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a67be-137">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="a67be-138">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="a67be-138">Network Settings Schema</span></span>](index.md)
