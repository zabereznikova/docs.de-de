---
title: <webRequestModules>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: c30a7a0bcce62c99d7c1ec0ff17389b8c2cd2f17
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663945"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="89878-102">\<webRequestModules >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="89878-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="89878-103">Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89878-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="89878-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="89878-104">\<configuration></span></span>  
<span data-ttu-id="89878-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="89878-105">\<system.net></span></span>  
<span data-ttu-id="89878-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="89878-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89878-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="89878-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89878-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89878-108">Attributes and Elements</span></span>  
 <span data-ttu-id="89878-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89878-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89878-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="89878-110">Attributes</span></span>  
 <span data-ttu-id="89878-111">Keine</span><span class="sxs-lookup"><span data-stu-id="89878-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89878-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89878-112">Child Elements</span></span>  
  
|<span data-ttu-id="89878-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="89878-113">**Element**</span></span>|<span data-ttu-id="89878-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="89878-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="89878-115">add</span><span class="sxs-lookup"><span data-stu-id="89878-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="89878-116">Fügt der Anwendung ein benutzerdefiniertes Webanforderungs Modul hinzu.</span><span class="sxs-lookup"><span data-stu-id="89878-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="89878-117">clear</span><span class="sxs-lookup"><span data-stu-id="89878-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="89878-118">Entfernt alle registrierten Webanforderungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="89878-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="89878-119">remove</span><span class="sxs-lookup"><span data-stu-id="89878-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="89878-120">Entfernt ein benutzerdefiniertes Webanforderungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="89878-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89878-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89878-121">Parent Elements</span></span>  
  
|<span data-ttu-id="89878-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="89878-122">**Element**</span></span>|<span data-ttu-id="89878-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="89878-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="89878-124">system.net</span><span class="sxs-lookup"><span data-stu-id="89878-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="89878-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="89878-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89878-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89878-126">Remarks</span></span>  
 <span data-ttu-id="89878-127">Das `webRequestModules` -Element registriert Nachfolger <xref:System.Net.WebRequest> der-Klasse, um Informationsanforderungen an Netzwerk Hosts zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="89878-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="89878-128">Webanforderungs Module müssen die <xref:System.Net.IWebRequestCreate> -Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="89878-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="89878-129">Die .NET Framework enthält Webanforderungs Module für URIs, die `http://`mit `https://`, und `file://`beginnen.</span><span class="sxs-lookup"><span data-stu-id="89878-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="89878-130">Sie können die Standardmodule nur überschreiben, indem Sie ein benutzerdefiniertes Modul in der Konfigurationsdatei registrieren.</span><span class="sxs-lookup"><span data-stu-id="89878-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="89878-131">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="89878-131">Configuration Files</span></span>  
 <span data-ttu-id="89878-132">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89878-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89878-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89878-133">Example</span></span>  
 <span data-ttu-id="89878-134">Im folgenden Beispiel wird das http-Standardmodul registriert.</span><span class="sxs-lookup"><span data-stu-id="89878-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="89878-135">Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="89878-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89878-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89878-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="89878-137">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="89878-137">Network Settings Schema</span></span>](index.md)
