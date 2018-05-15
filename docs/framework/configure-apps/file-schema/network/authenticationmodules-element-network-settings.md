---
title: '&lt;AuthenticationModules&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6d7f811a5746fa07264a192efdc4c5c02323e1f4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="2fd30-102">&lt;AuthenticationModules&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2fd30-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="2fd30-103">Gibt die Module, die zum Authentifizieren von Anforderungen über das Netzwerk verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fd30-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="2fd30-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2fd30-104">\<configuration></span></span>  
<span data-ttu-id="2fd30-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2fd30-105">\<system.net></span></span>  
<span data-ttu-id="2fd30-106">\<AuthenticationModules ></span><span class="sxs-lookup"><span data-stu-id="2fd30-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd30-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fd30-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fd30-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2fd30-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2fd30-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2fd30-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fd30-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2fd30-110">Attributes</span></span>  
 <span data-ttu-id="2fd30-111">Keine</span><span class="sxs-lookup"><span data-stu-id="2fd30-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2fd30-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fd30-112">Child Elements</span></span>  
  
|<span data-ttu-id="2fd30-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="2fd30-113">**Element**</span></span>|<span data-ttu-id="2fd30-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2fd30-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2fd30-115">add</span><span class="sxs-lookup"><span data-stu-id="2fd30-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="2fd30-116">Die Anwendung hinzugefügt ein Authentifizierungsmodul.</span><span class="sxs-lookup"><span data-stu-id="2fd30-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="2fd30-117">clear</span><span class="sxs-lookup"><span data-stu-id="2fd30-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="2fd30-118">Löscht alle Authentifizierungsmodule aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="2fd30-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="2fd30-119">remove</span><span class="sxs-lookup"><span data-stu-id="2fd30-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="2fd30-120">Entfernt ein Authentifizierungsmodul aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="2fd30-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2fd30-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fd30-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2fd30-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="2fd30-122">**Element**</span></span>|<span data-ttu-id="2fd30-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2fd30-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2fd30-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="2fd30-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="2fd30-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2fd30-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fd30-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fd30-126">Remarks</span></span>  
 <span data-ttu-id="2fd30-127">Die `authenticationModule` Element gibt die Authentifizierungsmodule, die den Authentifizierungsprozess mit einem Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="2fd30-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="2fd30-128">Ein Authentifizierungsmodul implementieren muss die <xref:System.Net.IAuthenticationModule> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2fd30-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2fd30-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="2fd30-129">Configuration Files</span></span>  
 <span data-ttu-id="2fd30-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fd30-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fd30-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2fd30-131">Example</span></span>  
 <span data-ttu-id="2fd30-132">Im folgende Beispiel wird ein Authentifizierungsmodul aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2fd30-132">The following example enables an authentication module.</span></span> <span data-ttu-id="2fd30-133">Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2fd30-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2fd30-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fd30-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="2fd30-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2fd30-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
