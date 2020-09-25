---
title: <add>-Element für webRequestModules (Netzwerkeinstellungen)
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
ms.openlocfilehash: 8d792b967d967540469dca7c090e0f905ecb2e6b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201758"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="95197-102">\<add>-Element für webRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="95197-102">\<add> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="95197-103">Fügt der Anwendung ein benutzerdefiniertes Webanforderungs Modul hinzu.</span><span class="sxs-lookup"><span data-stu-id="95197-103">Adds a custom Web request module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="95197-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95197-104">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95197-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="95197-105">Attributes and Elements</span></span>  

 <span data-ttu-id="95197-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95197-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95197-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="95197-107">Attributes</span></span>  
  
|<span data-ttu-id="95197-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="95197-108">**Attribute**</span></span>|<span data-ttu-id="95197-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="95197-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="95197-110">Das URI-Präfix für Anforderungen, die von diesem Webanforderungs Modul behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="95197-110">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="95197-111">Der voll qualifizierte Typname (angegeben durch die- <xref:System.Type.FullName%2A> Eigenschaft) und der AssemblyName (angegeben durch die- <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, das dieses Webanforderungs Modul implementiert.</span><span class="sxs-lookup"><span data-stu-id="95197-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95197-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95197-112">Child Elements</span></span>  

 <span data-ttu-id="95197-113">Keine</span><span class="sxs-lookup"><span data-stu-id="95197-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95197-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95197-114">Parent Elements</span></span>  
  
|<span data-ttu-id="95197-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="95197-115">**Element**</span></span>|<span data-ttu-id="95197-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="95197-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="95197-117">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="95197-117">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="95197-118">Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="95197-118">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95197-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="95197-119">Remarks</span></span>  

 <span data-ttu-id="95197-120">Das- `prefix` Attribut definiert das URI-Präfix, das das angegebene Webanforderungs Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="95197-120">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="95197-121">Webanforderungs Module sind in der Regel für die Verarbeitung eines bestimmten Protokolls registriert, z. b. http oder FTP, können jedoch registriert werden, um eine Anforderung an einen bestimmten Server oder Pfad auf einem Server zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="95197-121">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="95197-122">Das Webanforderungs Modul wird erstellt, wenn ein URI-übereinstimmendes Präfix an die Methode übermittelt wird <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="95197-122">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="95197-123">Der Wert für das- `prefix` Attribut muss die führenden Zeichen eines gültigen URI sein.</span><span class="sxs-lookup"><span data-stu-id="95197-123">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="95197-124">Zum Beispiel: `http` oder `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="95197-124">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="95197-125">Der Wert für das `type` -Attribut muss ein gültiger Typname und der zugehörige AssemblyName sein, getrennt durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="95197-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="95197-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="95197-126">Configuration Files</span></span>  

 <span data-ttu-id="95197-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95197-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="95197-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="95197-128">Example</span></span>  

 <span data-ttu-id="95197-129">Im folgenden Beispiel wird ein benutzerdefiniertes Webanforderungs Modul für http registriert.</span><span class="sxs-lookup"><span data-stu-id="95197-129">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="95197-130">Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="95197-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="95197-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95197-131">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="95197-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="95197-132">Network Settings Schema</span></span>](index.md)
