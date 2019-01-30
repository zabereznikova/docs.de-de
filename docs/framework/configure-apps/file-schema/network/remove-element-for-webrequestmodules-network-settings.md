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
ms.openlocfilehash: af30fe15eab899f7a083e0feb1350fb67b1c32cd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267260"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="a218d-102">\<Entfernen Sie >-Element für WebRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a218d-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="a218d-103">Entfernt ein benutzerdefinierte Webanforderungsmodul aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="a218d-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="a218d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a218d-104">\<configuration></span></span>  
<span data-ttu-id="a218d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a218d-105">\<system.net></span></span>  
<span data-ttu-id="a218d-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="a218d-106">\<webRequestModules></span></span>  
<span data-ttu-id="a218d-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="a218d-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a218d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a218d-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a218d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a218d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a218d-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a218d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a218d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a218d-111">Attributes</span></span>  
  
|<span data-ttu-id="a218d-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="a218d-112">**Attribute**</span></span>|<span data-ttu-id="a218d-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a218d-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="a218d-114">Das URI-Präfix für Anforderungen, die von diesem Webanforderungsmodul behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a218d-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a218d-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a218d-115">Child Elements</span></span>  
 <span data-ttu-id="a218d-116">Keine</span><span class="sxs-lookup"><span data-stu-id="a218d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a218d-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a218d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a218d-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="a218d-118">**Element**</span></span>|<span data-ttu-id="a218d-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a218d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a218d-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="a218d-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="a218d-121">Gibt die Module zu verwenden, um Informationen aus der Hosts im Netzwerk anzufordern.</span><span class="sxs-lookup"><span data-stu-id="a218d-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a218d-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a218d-122">Remarks</span></span>  
 <span data-ttu-id="a218d-123">Die `remove` -Element entfernt die eingetragene Webanforderungsmodul für das angegebene URI-Präfix.</span><span class="sxs-lookup"><span data-stu-id="a218d-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="a218d-124">Der Wert für die `prefix` Attribut muss die führenden Zeichen eine gültige URI sein – z. B. "`http`", oder "`http://www.contoso.com`".</span><span class="sxs-lookup"><span data-stu-id="a218d-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a218d-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a218d-125">Configuration Files</span></span>  
 <span data-ttu-id="a218d-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a218d-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a218d-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a218d-127">Example</span></span>  

<span data-ttu-id="a218d-128">Im folgenden Beispiel wird das vorhandene Webanforderungsmodul für HTTP und registriert dann ein neues benutzerdefinierte Webanforderungsmodul für HTTP-Anforderungen an `www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="a218d-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="a218d-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a218d-129">See also</span></span>
- <xref:System.Net.WebRequest>
- [<span data-ttu-id="a218d-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a218d-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
