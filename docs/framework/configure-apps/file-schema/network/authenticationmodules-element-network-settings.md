---
title: <authenticationModules>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: b502cc4a0958f074018d4b0ce6b3fb118b811c2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154971"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="45cf5-102">\<authenticationModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="45cf5-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="45cf5-103">Gibt Module an, die zum Authentifizieren von Netzwerkanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45cf5-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="45cf5-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="45cf5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="45cf5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="45cf5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="45cf5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authentifizierungModule>**</span><span class="sxs-lookup"><span data-stu-id="45cf5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="45cf5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="45cf5-107">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45cf5-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="45cf5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="45cf5-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="45cf5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45cf5-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="45cf5-110">Attributes</span></span>  
 <span data-ttu-id="45cf5-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="45cf5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="45cf5-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45cf5-112">Child Elements</span></span>  
  
|<span data-ttu-id="45cf5-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="45cf5-113">**Element**</span></span>|<span data-ttu-id="45cf5-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="45cf5-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="45cf5-115">Hinzufügen</span><span class="sxs-lookup"><span data-stu-id="45cf5-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="45cf5-116">Fügt der Anwendung ein Authentifizierungsmodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="45cf5-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="45cf5-117">Klar</span><span class="sxs-lookup"><span data-stu-id="45cf5-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="45cf5-118">Löscht alle Authentifizierungsmodule aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="45cf5-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="45cf5-119">Entfernen</span><span class="sxs-lookup"><span data-stu-id="45cf5-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="45cf5-120">Entfernt ein Authentifizierungsmodul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="45cf5-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45cf5-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45cf5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="45cf5-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="45cf5-122">**Element**</span></span>|<span data-ttu-id="45cf5-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="45cf5-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="45cf5-124">system.net</span><span class="sxs-lookup"><span data-stu-id="45cf5-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="45cf5-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="45cf5-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45cf5-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45cf5-126">Remarks</span></span>  
 <span data-ttu-id="45cf5-127">Das `authenticationModule` Element gibt die Authentifizierungsmodule an, die den Authentifizierungsprozess mit einem Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="45cf5-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="45cf5-128">Ein Authentifizierungsmodul <xref:System.Net.IAuthenticationModule> muss die Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="45cf5-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="45cf5-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="45cf5-129">Configuration Files</span></span>  
 <span data-ttu-id="45cf5-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45cf5-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45cf5-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45cf5-131">Example</span></span>  
 <span data-ttu-id="45cf5-132">Im folgenden Beispiel wird ein Authentifizierungsmodul aktiviert.</span><span class="sxs-lookup"><span data-stu-id="45cf5-132">The following example enables an authentication module.</span></span> <span data-ttu-id="45cf5-133">Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="45cf5-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45cf5-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45cf5-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="45cf5-135">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="45cf5-135">Network Settings Schema</span></span>](index.md)
