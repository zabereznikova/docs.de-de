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
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154724"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="3f28a-102">\<Entfernen> Element für webRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3f28a-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="3f28a-103">Entfernt ein benutzerdefiniertes Webanforderungsmodul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3f28a-103">Removes a custom Web request module from the application.</span></span>  
  
<span data-ttu-id="3f28a-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f28a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3f28a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3f28a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="3f28a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3f28a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="3f28a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entfernen sie>**</span><span class="sxs-lookup"><span data-stu-id="3f28a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3f28a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f28a-108">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f28a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3f28a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3f28a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3f28a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f28a-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="3f28a-111">Attributes</span></span>  
  
|<span data-ttu-id="3f28a-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="3f28a-112">**Attribute**</span></span>|<span data-ttu-id="3f28a-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3f28a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="3f28a-114">Das URI-Präfix für Anforderungen, die von diesem Webanforderungsmodul verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3f28a-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f28a-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3f28a-115">Child Elements</span></span>  
 <span data-ttu-id="3f28a-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="3f28a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f28a-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3f28a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3f28a-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="3f28a-118">**Element**</span></span>|<span data-ttu-id="3f28a-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3f28a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3f28a-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="3f28a-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="3f28a-121">Gibt Module an, die zum Anfordern von Informationen von Netzwerkhosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3f28a-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f28a-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3f28a-122">Remarks</span></span>  
 <span data-ttu-id="3f28a-123">Das `remove` Element entfernt das registrierte Webanforderungsmodul für das angegebene URI-Präfix.</span><span class="sxs-lookup"><span data-stu-id="3f28a-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="3f28a-124">Der Wert `prefix` für das Attribut sollte die führenden Zeichen eines`http`gültigen URI`http://www.contoso.com`sein , z. B. " ", oder " ".</span><span class="sxs-lookup"><span data-stu-id="3f28a-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3f28a-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="3f28a-125">Configuration Files</span></span>  
 <span data-ttu-id="3f28a-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f28a-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f28a-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f28a-127">Example</span></span>  

<span data-ttu-id="3f28a-128">Im folgenden Beispiel wird das vorhandene Webanforderungsmodul für HTTP entfernt und anschließend `www.contoso.com`ein neues benutzerdefiniertes Webanforderungsmodul für HTTP-Anforderungen an registriert.</span><span class="sxs-lookup"><span data-stu-id="3f28a-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="3f28a-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f28a-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="3f28a-130">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="3f28a-130">Network Settings Schema</span></span>](index.md)
