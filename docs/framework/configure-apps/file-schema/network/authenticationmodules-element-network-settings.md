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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154971"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="a69fd-102">\<authenticationModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a69fd-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="a69fd-103">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a69fd-103">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="a69fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a69fd-104">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a69fd-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a69fd-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a69fd-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a69fd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a69fd-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="a69fd-107">Attributes</span></span>  
 <span data-ttu-id="a69fd-108">Keine</span><span class="sxs-lookup"><span data-stu-id="a69fd-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a69fd-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a69fd-109">Child Elements</span></span>  
  
|<span data-ttu-id="a69fd-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="a69fd-110">**Element**</span></span>|<span data-ttu-id="a69fd-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a69fd-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a69fd-112">add</span><span class="sxs-lookup"><span data-stu-id="a69fd-112">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a69fd-113">Fügt der Anwendung ein Authentifizierungs Modul hinzu.</span><span class="sxs-lookup"><span data-stu-id="a69fd-113">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="a69fd-114">Löschen</span><span class="sxs-lookup"><span data-stu-id="a69fd-114">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a69fd-115">Löscht alle Authentifizierungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a69fd-115">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="a69fd-116">remove</span><span class="sxs-lookup"><span data-stu-id="a69fd-116">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a69fd-117">Entfernt ein Authentifizierungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a69fd-117">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a69fd-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a69fd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a69fd-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="a69fd-119">**Element**</span></span>|<span data-ttu-id="a69fd-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a69fd-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a69fd-121">system.net</span><span class="sxs-lookup"><span data-stu-id="a69fd-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a69fd-122">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a69fd-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a69fd-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a69fd-123">Remarks</span></span>  
 <span data-ttu-id="a69fd-124">Das- `authenticationModule` Element gibt die Authentifizierungs Module an, die den Authentifizierungsprozess mit einem-Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="a69fd-124">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="a69fd-125">Ein Authentifizierungs Modul muss die- <xref:System.Net.IAuthenticationModule> Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="a69fd-125">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a69fd-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a69fd-126">Configuration Files</span></span>  
 <span data-ttu-id="a69fd-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a69fd-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a69fd-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a69fd-128">Example</span></span>  
 <span data-ttu-id="a69fd-129">Im folgenden Beispiel wird ein Authentifizierungs Modul aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a69fd-129">The following example enables an authentication module.</span></span> <span data-ttu-id="a69fd-130">Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a69fd-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a69fd-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a69fd-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="a69fd-132">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="a69fd-132">Network Settings Schema</span></span>](index.md)
