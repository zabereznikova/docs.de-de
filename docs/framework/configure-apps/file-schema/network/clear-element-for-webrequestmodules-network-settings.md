---
title: <clear>-Element für webRequestModules (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 892058dd8af8a38bd7bde868b34a2c6899d9a989
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184039"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="c6870-102">\<clear>-Element für webRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c6870-102">\<clear> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="c6870-103">Entfernt alle registrierten Webanforderungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c6870-103">Removes all registered Web request modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="c6870-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6870-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6870-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c6870-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c6870-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c6870-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6870-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="c6870-107">Attributes</span></span>  

 <span data-ttu-id="c6870-108">Keine</span><span class="sxs-lookup"><span data-stu-id="c6870-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6870-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6870-109">Child Elements</span></span>  

 <span data-ttu-id="c6870-110">Keine</span><span class="sxs-lookup"><span data-stu-id="c6870-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6870-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6870-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c6870-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="c6870-112">**Element**</span></span>|<span data-ttu-id="c6870-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c6870-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c6870-114">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="c6870-114">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="c6870-115">Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c6870-115">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6870-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c6870-116">Remarks</span></span>  

 <span data-ttu-id="c6870-117">Das- `clear` Element entfernt alle registrierten Webanforderungs Module, die zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c6870-117">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c6870-118">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="c6870-118">Configuration Files</span></span>  

 <span data-ttu-id="c6870-119">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6870-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6870-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6870-120">Example</span></span>  

 <span data-ttu-id="c6870-121">Im folgenden Beispiel werden alle Webanforderungs Module gelöscht und anschließend ein Webanforderungs Modul für http registriert.</span><span class="sxs-lookup"><span data-stu-id="c6870-121">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6870-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6870-122">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="c6870-123">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c6870-123">Network Settings Schema</span></span>](index.md)
