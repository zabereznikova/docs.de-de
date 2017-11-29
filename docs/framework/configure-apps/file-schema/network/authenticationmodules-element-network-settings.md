---
title: '&lt;AuthenticationModules&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fe2e1757a3e2da5c2aa6084c0eb21164de3ece0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="aa20f-102">&lt;AuthenticationModules&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="aa20f-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="aa20f-103">Gibt die Module, die zum Authentifizieren von Anforderungen über das Netzwerk verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa20f-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="aa20f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="aa20f-104">\<configuration></span></span>  
<span data-ttu-id="aa20f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="aa20f-105">\<system.net></span></span>  
<span data-ttu-id="aa20f-106">\<AuthenticationModules ></span><span class="sxs-lookup"><span data-stu-id="aa20f-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa20f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa20f-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa20f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa20f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aa20f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa20f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa20f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa20f-110">Attributes</span></span>  
 <span data-ttu-id="aa20f-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="aa20f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa20f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa20f-112">Child Elements</span></span>  
  
|<span data-ttu-id="aa20f-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="aa20f-113">**Element**</span></span>|<span data-ttu-id="aa20f-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="aa20f-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="aa20f-115">add</span><span class="sxs-lookup"><span data-stu-id="aa20f-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="aa20f-116">Die Anwendung hinzugefügt ein Authentifizierungsmodul.</span><span class="sxs-lookup"><span data-stu-id="aa20f-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="aa20f-117">clear</span><span class="sxs-lookup"><span data-stu-id="aa20f-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="aa20f-118">Löscht alle Authentifizierungsmodule aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="aa20f-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="aa20f-119">remove</span><span class="sxs-lookup"><span data-stu-id="aa20f-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="aa20f-120">Entfernt ein Authentifizierungsmodul aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="aa20f-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa20f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa20f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="aa20f-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="aa20f-122">**Element**</span></span>|<span data-ttu-id="aa20f-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="aa20f-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="aa20f-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="aa20f-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="aa20f-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aa20f-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa20f-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa20f-126">Remarks</span></span>  
 <span data-ttu-id="aa20f-127">Die `authenticationModule` Element gibt die Authentifizierungsmodule, die den Authentifizierungsprozess mit einem Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="aa20f-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="aa20f-128">Ein Authentifizierungsmodul implementieren muss die <xref:System.Net.IAuthenticationModule> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="aa20f-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="aa20f-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="aa20f-129">Configuration Files</span></span>  
 <span data-ttu-id="aa20f-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa20f-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa20f-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa20f-131">Example</span></span>  
 <span data-ttu-id="aa20f-132">Im folgende Beispiel wird ein Authentifizierungsmodul aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa20f-132">The following example enables an authentication module.</span></span> <span data-ttu-id="aa20f-133">Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="aa20f-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa20f-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa20f-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="aa20f-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="aa20f-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
