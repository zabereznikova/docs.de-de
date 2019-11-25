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
ms.openlocfilehash: 9c011cf1216b98fa20e330e185e4cf2c331b31d4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087949"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="aec29-102">\<Add >-Element für authenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="aec29-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="aec29-103">Fügt der Anwendung ein Authentifizierungs Modul hinzu.</span><span class="sxs-lookup"><span data-stu-id="aec29-103">Adds an authentication module to the application.</span></span>  

<span data-ttu-id="aec29-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aec29-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aec29-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="aec29-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="aec29-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="aec29-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="aec29-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="aec29-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="aec29-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="aec29-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aec29-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aec29-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aec29-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aec29-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aec29-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="aec29-111">Attributes</span></span>  
  
|<span data-ttu-id="aec29-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="aec29-112">**Attribute**</span></span>|<span data-ttu-id="aec29-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="aec29-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="aec29-114">Der voll qualifizierte Typname (angegeben durch die <xref:System.Type.FullName%2A>-Eigenschaft) und der AssemblyName (angegeben durch die <xref:System.Reflection.Assembly.FullName%2A>-Eigenschaft), getrennt durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="aec29-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aec29-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aec29-115">Child Elements</span></span>  
 <span data-ttu-id="aec29-116">Keine</span><span class="sxs-lookup"><span data-stu-id="aec29-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aec29-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aec29-117">Parent Elements</span></span>  
  
|<span data-ttu-id="aec29-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="aec29-118">**Element**</span></span>|<span data-ttu-id="aec29-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="aec29-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="aec29-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="aec29-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="aec29-121">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aec29-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aec29-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aec29-122">Remarks</span></span>  
 <span data-ttu-id="aec29-123">Das `add`-Element fügt ein Authentifizierungs Modul am Ende der Liste der registrierten Authentifizierungs Module hinzu.</span><span class="sxs-lookup"><span data-stu-id="aec29-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="aec29-124">Authentifizierungs Module werden in der Reihenfolge aufgerufen, in der Sie der Liste hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="aec29-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="aec29-125">Der Wert für das `type` Attribut muss ein gültiger Typname und der zugehörige AssemblyName sein, getrennt durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="aec29-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="aec29-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="aec29-126">Configuration Files</span></span>  
 <span data-ttu-id="aec29-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aec29-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aec29-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aec29-128">Example</span></span>  
 <span data-ttu-id="aec29-129">Im folgenden Beispiel werden die Standard Authentifizierungs Module aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aec29-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="aec29-130">Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="aec29-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aec29-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aec29-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="aec29-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="aec29-132">Network Settings Schema</span></span>](index.md)
