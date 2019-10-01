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
ms.openlocfilehash: 4fe44deba951e5302518ed855589ad1b0ca75343
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699533"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="a17d8-102">\<authenticationmodules >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a17d8-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="a17d8-103">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a17d8-103">Specifies modules used to authenticate network requests.</span></span>  
  
[<span data-ttu-id="a17d8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a17d8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a17d8-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a17d8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="a17d8-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<authenticationmodules >**</span><span class="sxs-lookup"><span data-stu-id="a17d8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a17d8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a17d8-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a17d8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a17d8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a17d8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a17d8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a17d8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a17d8-110">Attributes</span></span>  
 <span data-ttu-id="a17d8-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a17d8-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a17d8-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a17d8-112">Child Elements</span></span>  
  
|<span data-ttu-id="a17d8-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="a17d8-113">**Element**</span></span>|<span data-ttu-id="a17d8-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a17d8-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a17d8-115">add</span><span class="sxs-lookup"><span data-stu-id="a17d8-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a17d8-116">Fügt der Anwendung ein Authentifizierungs Modul hinzu.</span><span class="sxs-lookup"><span data-stu-id="a17d8-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="a17d8-117">clear</span><span class="sxs-lookup"><span data-stu-id="a17d8-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a17d8-118">Löscht alle Authentifizierungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a17d8-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="a17d8-119">remove</span><span class="sxs-lookup"><span data-stu-id="a17d8-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a17d8-120">Entfernt ein Authentifizierungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a17d8-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a17d8-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a17d8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a17d8-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="a17d8-122">**Element**</span></span>|<span data-ttu-id="a17d8-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a17d8-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a17d8-124">system.net</span><span class="sxs-lookup"><span data-stu-id="a17d8-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a17d8-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a17d8-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a17d8-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a17d8-126">Remarks</span></span>  
 <span data-ttu-id="a17d8-127">Das `authenticationModule`-Element gibt die Authentifizierungs Module an, die den Authentifizierungsprozess mit einem Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="a17d8-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="a17d8-128">Ein Authentifizierungs Modul muss die <xref:System.Net.IAuthenticationModule>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="a17d8-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a17d8-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a17d8-129">Configuration Files</span></span>  
 <span data-ttu-id="a17d8-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a17d8-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a17d8-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a17d8-131">Example</span></span>  
 <span data-ttu-id="a17d8-132">Im folgenden Beispiel wird ein Authentifizierungs Modul aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a17d8-132">The following example enables an authentication module.</span></span> <span data-ttu-id="a17d8-133">Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a17d8-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a17d8-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a17d8-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="a17d8-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a17d8-135">Network Settings Schema</span></span>](index.md)
