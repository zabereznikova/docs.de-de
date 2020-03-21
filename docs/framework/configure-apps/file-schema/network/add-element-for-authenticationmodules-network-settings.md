---
title: <add>-Element für authenticationModules (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: 4181a045079bdb455a63ebda722dd6b0daf33c4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155114"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="6f05d-102">\<Hinzufügen> Elements für authentifizierungModule (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6f05d-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="6f05d-103">Fügt der Anwendung ein Authentifizierungsmodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f05d-103">Adds an authentication module to the application.</span></span>  

<span data-ttu-id="6f05d-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6f05d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6f05d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6f05d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="6f05d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authentifizierungModule>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6f05d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="6f05d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="6f05d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6f05d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f05d-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f05d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6f05d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6f05d-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6f05d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f05d-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="6f05d-111">Attributes</span></span>  
  
|<span data-ttu-id="6f05d-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="6f05d-112">**Attribute**</span></span>|<span data-ttu-id="6f05d-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6f05d-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="6f05d-114">Der vollqualifizierte Typname (durch die <xref:System.Type.FullName%2A> Eigenschaft angegeben) und <xref:System.Reflection.Assembly.FullName%2A> der Assemblyname (durch die Eigenschaft angegeben), getrennt durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="6f05d-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f05d-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f05d-115">Child Elements</span></span>  
 <span data-ttu-id="6f05d-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="6f05d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f05d-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f05d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6f05d-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="6f05d-118">**Element**</span></span>|<span data-ttu-id="6f05d-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6f05d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6f05d-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="6f05d-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="6f05d-121">Gibt Module an, die zum Authentifizieren von Netzwerkanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f05d-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f05d-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6f05d-122">Remarks</span></span>  
 <span data-ttu-id="6f05d-123">Das `add` Element fügt am Ende der Liste der registrierten Authentifizierungsmodule ein Authentifizierungsmodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f05d-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="6f05d-124">Authentifizierungsmodule werden in der Reihenfolge aufgerufen, in der sie der Liste hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="6f05d-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="6f05d-125">Der Wert `type` für das Attribut sollte ein gültiger Typname und ein entsprechender Assemblyname sein, der durch ein Komma getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="6f05d-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6f05d-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="6f05d-126">Configuration Files</span></span>  
 <span data-ttu-id="6f05d-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f05d-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f05d-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f05d-128">Example</span></span>  
 <span data-ttu-id="6f05d-129">Im folgenden Beispiel werden die Standardauthentifizierungsmodule aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f05d-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="6f05d-130">Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="6f05d-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f05d-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f05d-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="6f05d-132">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="6f05d-132">Network Settings Schema</span></span>](index.md)
