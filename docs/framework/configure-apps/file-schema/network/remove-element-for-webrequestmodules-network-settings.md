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
ms.openlocfilehash: 65e8b1f2088015b86d4f981f07875d236a11a617
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176187"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="e29ec-102">\<remove>-Element für webRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e29ec-102">\<remove> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="e29ec-103">Entfernt ein benutzerdefiniertes Webanforderungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e29ec-103">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="e29ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e29ec-104">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e29ec-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e29ec-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e29ec-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e29ec-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e29ec-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e29ec-107">Attributes</span></span>  
  
|<span data-ttu-id="e29ec-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="e29ec-108">**Attribute**</span></span>|<span data-ttu-id="e29ec-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e29ec-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="e29ec-110">Das URI-Präfix für Anforderungen, die von diesem Webanforderungs Modul behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e29ec-110">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e29ec-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e29ec-111">Child Elements</span></span>  

 <span data-ttu-id="e29ec-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e29ec-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e29ec-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e29ec-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e29ec-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="e29ec-114">**Element**</span></span>|<span data-ttu-id="e29ec-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e29ec-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e29ec-116">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="e29ec-116">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="e29ec-117">Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e29ec-117">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e29ec-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e29ec-118">Remarks</span></span>  

 <span data-ttu-id="e29ec-119">Das- `remove` Element entfernt das registrierte Webanforderungs Modul für das angegebene URI-Präfix.</span><span class="sxs-lookup"><span data-stu-id="e29ec-119">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="e29ec-120">Der Wert für das- `prefix` Attribut muss die führenden Zeichen eines gültigen URIs sein, z. b. " `http` " oder " `http://www.contoso.com` ".</span><span class="sxs-lookup"><span data-stu-id="e29ec-120">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e29ec-121">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="e29ec-121">Configuration Files</span></span>  

 <span data-ttu-id="e29ec-122">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e29ec-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e29ec-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e29ec-123">Example</span></span>  

<span data-ttu-id="e29ec-124">Im folgenden Beispiel wird das vorhandene Webanforderungs Modul für http entfernt und dann ein neues benutzerdefiniertes Webanforderungs Modul für HTTP-Anforderungen an registriert `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="e29ec-124">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="e29ec-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e29ec-125">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="e29ec-126">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e29ec-126">Network Settings Schema</span></span>](index.md)
