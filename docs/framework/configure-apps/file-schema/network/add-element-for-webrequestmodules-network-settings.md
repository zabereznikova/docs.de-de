---
title: '&lt;Hinzufügen&gt; -Element für WebRequestModules (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: 4c823f366baf51b35c15a87c2a9f6c9c4d3102d0
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188532"
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="75b73-102">&lt;Hinzufügen&gt; -Element für WebRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="75b73-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="75b73-103">Die Anwendung hinzugefügt ein benutzerdefinierte Webanforderungsmodul.</span><span class="sxs-lookup"><span data-stu-id="75b73-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="75b73-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="75b73-104">\<configuration></span></span>  
<span data-ttu-id="75b73-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="75b73-105">\<system.net></span></span>  
<span data-ttu-id="75b73-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="75b73-106">\<webRequestModules></span></span>  
<span data-ttu-id="75b73-107">\<add></span><span class="sxs-lookup"><span data-stu-id="75b73-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b73-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="75b73-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75b73-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="75b73-109">Attributes and Elements</span></span>  
 <span data-ttu-id="75b73-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75b73-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75b73-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="75b73-111">Attributes</span></span>  
  
|<span data-ttu-id="75b73-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="75b73-112">**Attribute**</span></span>|<span data-ttu-id="75b73-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="75b73-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="75b73-114">Das URI-Präfix für Anforderungen, die von diesem Webanforderungsmodul behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="75b73-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="75b73-115">Der vollqualifizierte Name (erkennbar die <xref:System.Type.FullName%2A> Eigenschaft) und den Assemblynamen (erkennbar die <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, die diese Webanforderungsmodul implementiert.</span><span class="sxs-lookup"><span data-stu-id="75b73-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75b73-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75b73-116">Child Elements</span></span>  
 <span data-ttu-id="75b73-117">Keine</span><span class="sxs-lookup"><span data-stu-id="75b73-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75b73-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75b73-118">Parent Elements</span></span>  
  
|<span data-ttu-id="75b73-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="75b73-119">**Element**</span></span>|<span data-ttu-id="75b73-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="75b73-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="75b73-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="75b73-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="75b73-122">Gibt die Module zu verwenden, um Informationen aus der Hosts im Netzwerk anzufordern.</span><span class="sxs-lookup"><span data-stu-id="75b73-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75b73-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75b73-123">Remarks</span></span>  
 <span data-ttu-id="75b73-124">Die `prefix` Attribut definiert die URI-Präfix, das das angegebene Webanforderungsmodul verwendet.</span><span class="sxs-lookup"><span data-stu-id="75b73-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="75b73-125">Webanforderungsmodule sind in der Regel registriert ein bestimmtes Protokoll wie HTTP oder FTP, jedoch können registriert werden, um eine Anforderung an einen bestimmten Server oder den Pfad auf einem Server zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="75b73-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="75b73-126">Die Webanforderungsmodul wird erstellt, wenn ein übereinstimmendes URI-Präfix zu übergeben, wird die <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="75b73-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="75b73-127">Der Wert für die `prefix` Attribut sollte die ersten Zeichen ein gültiger URI sein.</span><span class="sxs-lookup"><span data-stu-id="75b73-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="75b73-128">Beispielsweise `http` oder `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="75b73-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="75b73-129">Der Wert für die `type` Attribut sollte einen gültigen Typnamen und den entsprechenden Assemblynamen, die durch ein Komma getrennt sein.</span><span class="sxs-lookup"><span data-stu-id="75b73-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="75b73-130">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="75b73-130">Configuration Files</span></span>  
 <span data-ttu-id="75b73-131">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75b73-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75b73-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75b73-132">Example</span></span>  
 <span data-ttu-id="75b73-133">Das folgende Beispiel registriert ein benutzerdefinierte Webanforderungsmodul für HTTP an.</span><span class="sxs-lookup"><span data-stu-id="75b73-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="75b73-134">Sie sollten die Werte für die Version und ' PublicKeyToken ' machen durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="75b73-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75b73-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75b73-135">See Also</span></span>  
- <xref:System.Net.WebRequest>  
- [<span data-ttu-id="75b73-136">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="75b73-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
