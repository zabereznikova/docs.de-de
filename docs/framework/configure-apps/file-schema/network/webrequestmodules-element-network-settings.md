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
ms.openlocfilehash: 7f2805283f89e6165d336b3e593d34054e02115d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154542"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="5dc81-102">\<webRequestModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5dc81-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="5dc81-103">Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5dc81-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a><span data-ttu-id="5dc81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dc81-104">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dc81-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5dc81-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5dc81-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5dc81-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dc81-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="5dc81-107">Attributes</span></span>  
 <span data-ttu-id="5dc81-108">Keine</span><span class="sxs-lookup"><span data-stu-id="5dc81-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5dc81-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5dc81-109">Child Elements</span></span>  
  
|<span data-ttu-id="5dc81-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="5dc81-110">**Element**</span></span>|<span data-ttu-id="5dc81-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5dc81-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5dc81-112">add</span><span class="sxs-lookup"><span data-stu-id="5dc81-112">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="5dc81-113">Fügt der Anwendung ein benutzerdefiniertes Webanforderungs Modul hinzu.</span><span class="sxs-lookup"><span data-stu-id="5dc81-113">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="5dc81-114">Löschen</span><span class="sxs-lookup"><span data-stu-id="5dc81-114">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="5dc81-115">Entfernt alle registrierten Webanforderungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5dc81-115">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="5dc81-116">remove</span><span class="sxs-lookup"><span data-stu-id="5dc81-116">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="5dc81-117">Entfernt ein benutzerdefiniertes Webanforderungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5dc81-117">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5dc81-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5dc81-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5dc81-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="5dc81-119">**Element**</span></span>|<span data-ttu-id="5dc81-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5dc81-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5dc81-121">system.net</span><span class="sxs-lookup"><span data-stu-id="5dc81-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="5dc81-122">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5dc81-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dc81-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5dc81-123">Remarks</span></span>  
 <span data-ttu-id="5dc81-124">Das- `webRequestModules` Element registriert Nachfolger der- <xref:System.Net.WebRequest> Klasse, um Informationsanforderungen an Netzwerk Hosts zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5dc81-124">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="5dc81-125">Webanforderungs Module müssen die- <xref:System.Net.IWebRequestCreate> Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="5dc81-125">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="5dc81-126">Die .NET Framework enthält Webanforderungs Module für URIs, die mit `http://` , `https://` und beginnen `file://` .</span><span class="sxs-lookup"><span data-stu-id="5dc81-126">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="5dc81-127">Sie können die Standardmodule nur überschreiben, indem Sie ein benutzerdefiniertes Modul in der Konfigurationsdatei registrieren.</span><span class="sxs-lookup"><span data-stu-id="5dc81-127">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5dc81-128">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="5dc81-128">Configuration Files</span></span>  
 <span data-ttu-id="5dc81-129">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5dc81-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dc81-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5dc81-130">Example</span></span>  
 <span data-ttu-id="5dc81-131">Im folgenden Beispiel wird das http-Standardmodul registriert.</span><span class="sxs-lookup"><span data-stu-id="5dc81-131">The following example registers the default HTTP module.</span></span> <span data-ttu-id="5dc81-132">Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="5dc81-132">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5dc81-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5dc81-133">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="5dc81-134">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="5dc81-134">Network Settings Schema</span></span>](index.md)
