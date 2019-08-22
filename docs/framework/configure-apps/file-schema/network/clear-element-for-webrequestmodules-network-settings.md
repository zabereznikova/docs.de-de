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
ms.openlocfilehash: e175c70bd4932d6a8f9428e8cd9159a47df52558
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659426"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="a4107-102">\<Löschen von >-Element für webRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a4107-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="a4107-103">Entfernt alle registrierten Webanforderungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a4107-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="a4107-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a4107-104">\<configuration></span></span>  
<span data-ttu-id="a4107-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a4107-105">\<system.net></span></span>  
<span data-ttu-id="a4107-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="a4107-106">\<webRequestModules></span></span>  
<span data-ttu-id="a4107-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="a4107-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4107-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4107-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4107-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a4107-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a4107-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4107-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4107-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a4107-111">Attributes</span></span>  
 <span data-ttu-id="a4107-112">Keine</span><span class="sxs-lookup"><span data-stu-id="a4107-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4107-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4107-113">Child Elements</span></span>  
 <span data-ttu-id="a4107-114">Keine</span><span class="sxs-lookup"><span data-stu-id="a4107-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4107-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4107-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a4107-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="a4107-116">**Element**</span></span>|<span data-ttu-id="a4107-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a4107-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a4107-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="a4107-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="a4107-119">Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a4107-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4107-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4107-120">Remarks</span></span>  
 <span data-ttu-id="a4107-121">Das `clear` -Element entfernt alle registrierten Webanforderungs Module, die zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a4107-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a4107-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a4107-122">Configuration Files</span></span>  
 <span data-ttu-id="a4107-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4107-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4107-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4107-124">Example</span></span>  
 <span data-ttu-id="a4107-125">Im folgenden Beispiel werden alle Webanforderungs Module gelöscht und anschließend ein Webanforderungs Modul für http registriert.</span><span class="sxs-lookup"><span data-stu-id="a4107-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a4107-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4107-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="a4107-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a4107-127">Network Settings Schema</span></span>](index.md)
