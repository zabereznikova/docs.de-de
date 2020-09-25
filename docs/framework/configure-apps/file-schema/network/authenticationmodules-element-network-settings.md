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
ms.openlocfilehash: 154a73a5fe3fa9e2b6b1c9e5c462b76bdc1ba640
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201745"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="fc720-102">\<authenticationModules>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="fc720-102">\<authenticationModules> Element (Network Settings)</span></span>

<span data-ttu-id="fc720-103">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc720-103">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="fc720-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc720-104">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc720-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc720-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fc720-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc720-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc720-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc720-107">Attributes</span></span>  

 <span data-ttu-id="fc720-108">Keine</span><span class="sxs-lookup"><span data-stu-id="fc720-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fc720-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc720-109">Child Elements</span></span>  
  
|<span data-ttu-id="fc720-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="fc720-110">**Element**</span></span>|<span data-ttu-id="fc720-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fc720-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fc720-112">add</span><span class="sxs-lookup"><span data-stu-id="fc720-112">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fc720-113">Fügt der Anwendung ein Authentifizierungs Modul hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc720-113">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="fc720-114">Löschen</span><span class="sxs-lookup"><span data-stu-id="fc720-114">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fc720-115">Löscht alle Authentifizierungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fc720-115">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="fc720-116">remove</span><span class="sxs-lookup"><span data-stu-id="fc720-116">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fc720-117">Entfernt ein Authentifizierungs Modul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fc720-117">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc720-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc720-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fc720-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="fc720-119">**Element**</span></span>|<span data-ttu-id="fc720-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fc720-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fc720-121">system.net</span><span class="sxs-lookup"><span data-stu-id="fc720-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="fc720-122">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fc720-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc720-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fc720-123">Remarks</span></span>  

 <span data-ttu-id="fc720-124">Das- `authenticationModule` Element gibt die Authentifizierungs Module an, die den Authentifizierungsprozess mit einem-Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="fc720-124">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="fc720-125">Ein Authentifizierungs Modul muss die- <xref:System.Net.IAuthenticationModule> Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="fc720-125">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fc720-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="fc720-126">Configuration Files</span></span>  

 <span data-ttu-id="fc720-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc720-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc720-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc720-128">Example</span></span>  

 <span data-ttu-id="fc720-129">Im folgenden Beispiel wird ein Authentifizierungs Modul aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fc720-129">The following example enables an authentication module.</span></span> <span data-ttu-id="fc720-130">Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="fc720-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc720-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc720-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="fc720-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="fc720-132">Network Settings Schema</span></span>](index.md)
