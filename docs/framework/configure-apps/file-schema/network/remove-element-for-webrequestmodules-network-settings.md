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
ms.openlocfilehash: 20a586e945a889d1fd8a8d4c5c09c8b790c56fc3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664016"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="2820a-102">\<Remove >-Element für webRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2820a-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="2820a-103">Entfernt ein benutzerdefiniertes Webanforderungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2820a-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="2820a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2820a-104">\<configuration></span></span>  
<span data-ttu-id="2820a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2820a-105">\<system.net></span></span>  
<span data-ttu-id="2820a-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="2820a-106">\<webRequestModules></span></span>  
<span data-ttu-id="2820a-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="2820a-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2820a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2820a-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2820a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2820a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2820a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2820a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2820a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2820a-111">Attributes</span></span>  
  
|<span data-ttu-id="2820a-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="2820a-112">**Attribute**</span></span>|<span data-ttu-id="2820a-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2820a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="2820a-114">Das URI-Präfix für Anforderungen, die von diesem Webanforderungs Modul behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="2820a-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2820a-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2820a-115">Child Elements</span></span>  
 <span data-ttu-id="2820a-116">Keine</span><span class="sxs-lookup"><span data-stu-id="2820a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2820a-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2820a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2820a-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="2820a-118">**Element**</span></span>|<span data-ttu-id="2820a-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2820a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2820a-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="2820a-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="2820a-121">Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2820a-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2820a-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2820a-122">Remarks</span></span>  
 <span data-ttu-id="2820a-123">Das `remove` -Element entfernt das registrierte Webanforderungs Modul für das angegebene URI-Präfix.</span><span class="sxs-lookup"><span data-stu-id="2820a-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="2820a-124">Der Wert für das `prefix` -Attribut muss die führenden Zeichen eines gültigen URIs sein, z. b. "`http`" oder "`http://www.contoso.com`".</span><span class="sxs-lookup"><span data-stu-id="2820a-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2820a-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="2820a-125">Configuration Files</span></span>  
 <span data-ttu-id="2820a-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2820a-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2820a-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2820a-127">Example</span></span>  

<span data-ttu-id="2820a-128">Im folgenden Beispiel wird das vorhandene Webanforderungs Modul für http entfernt und dann ein neues benutzerdefiniertes Webanforderungs Modul `www.contoso.com`für HTTP-Anforderungen an registriert.</span><span class="sxs-lookup"><span data-stu-id="2820a-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="2820a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2820a-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="2820a-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2820a-130">Network Settings Schema</span></span>](index.md)
