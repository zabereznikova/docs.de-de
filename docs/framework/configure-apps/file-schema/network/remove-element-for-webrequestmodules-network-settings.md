---
title: <remove>-Element für webRequestModules (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: f8209ea89ac8cd214389feddee8c475e10bc939a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697817"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="d00d2-102">\<remove >-Element für webRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d00d2-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="d00d2-103">Entfernt ein benutzerdefiniertes Webanforderungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d00d2-103">Removes a custom Web request module from the application.</span></span>  
  
[<span data-ttu-id="d00d2-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d00d2-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d00d2-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d00d2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="d00d2-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<webrequestmodules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d00d2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="d00d2-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="d00d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d00d2-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d00d2-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d00d2-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d00d2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d00d2-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d00d2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d00d2-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d00d2-111">Attributes</span></span>  
  
|<span data-ttu-id="d00d2-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="d00d2-112">**Attribute**</span></span>|<span data-ttu-id="d00d2-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d00d2-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="d00d2-114">Das URI-Präfix für Anforderungen, die von diesem Webanforderungs Modul behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d00d2-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d00d2-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d00d2-115">Child Elements</span></span>  
 <span data-ttu-id="d00d2-116">Keine</span><span class="sxs-lookup"><span data-stu-id="d00d2-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d00d2-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d00d2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d00d2-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="d00d2-118">**Element**</span></span>|<span data-ttu-id="d00d2-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d00d2-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d00d2-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="d00d2-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="d00d2-121">Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d00d2-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d00d2-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d00d2-122">Remarks</span></span>  
 <span data-ttu-id="d00d2-123">Das `remove`-Element entfernt das registrierte Webanforderungs Modul für das angegebene URI-Präfix.</span><span class="sxs-lookup"><span data-stu-id="d00d2-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="d00d2-124">Der Wert für das `prefix`-Attribut muss die führenden Zeichen eines gültigen URIs sein, z. b. "`http`" oder "`http://www.contoso.com`".</span><span class="sxs-lookup"><span data-stu-id="d00d2-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d00d2-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="d00d2-125">Configuration Files</span></span>  
 <span data-ttu-id="d00d2-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d00d2-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d00d2-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d00d2-127">Example</span></span>  

<span data-ttu-id="d00d2-128">Im folgenden Beispiel wird das vorhandene Webanforderungs Modul für http entfernt. Anschließend wird ein neues benutzerdefiniertes Webanforderungs Modul für HTTP-Anforderungen an `www.contoso.com` registriert.</span><span class="sxs-lookup"><span data-stu-id="d00d2-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d00d2-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d00d2-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="d00d2-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d00d2-130">Network Settings Schema</span></span>](index.md)
