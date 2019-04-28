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
ms.openlocfilehash: a46e6af97f37974805812fb0d19801d618eee4d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705154"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="e9c35-102">\<Hinzufügen >-Element für AuthenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e9c35-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="e9c35-103">Ein Modul für die Authentifizierung hinzugefügt der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e9c35-103">Adds an authentication module to the application.</span></span>  
  
 <span data-ttu-id="e9c35-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e9c35-104">\<configuration></span></span>  
<span data-ttu-id="e9c35-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e9c35-105">\<system.net></span></span>  
<span data-ttu-id="e9c35-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="e9c35-106">\<authenticationModules></span></span>  
<span data-ttu-id="e9c35-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e9c35-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c35-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9c35-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9c35-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9c35-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9c35-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9c35-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9c35-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9c35-111">Attributes</span></span>  
  
|<span data-ttu-id="e9c35-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="e9c35-112">**Attribute**</span></span>|<span data-ttu-id="e9c35-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e9c35-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="e9c35-114">Den vollqualifizierten Typnamen (angegeben durch die <xref:System.Type.FullName%2A> Eigenschaft) und den Assemblynamen (erkennbar der <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft) und durch ein Komma getrennt.</span><span class="sxs-lookup"><span data-stu-id="e9c35-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9c35-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9c35-115">Child Elements</span></span>  
 <span data-ttu-id="e9c35-116">Keine</span><span class="sxs-lookup"><span data-stu-id="e9c35-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9c35-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9c35-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e9c35-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="e9c35-118">**Element**</span></span>|<span data-ttu-id="e9c35-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e9c35-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e9c35-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="e9c35-120">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="e9c35-121">Gibt die Module, die zum Authentifizieren von netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="e9c35-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9c35-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9c35-122">Remarks</span></span>  
 <span data-ttu-id="e9c35-123">Die `add` -Element fügt ein Authentifizierungsmodul an das Ende der Liste der registrierten Authentifizierungsmodule.</span><span class="sxs-lookup"><span data-stu-id="e9c35-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="e9c35-124">Authentifizierungsmodule werden in der Reihenfolge aufgerufen, in denen sie zur Liste hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="e9c35-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="e9c35-125">Der Wert für die `type` Attribut sollte einen gültigen Typnamen und den entsprechenden Assemblynamen, die durch ein Komma getrennt sein.</span><span class="sxs-lookup"><span data-stu-id="e9c35-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e9c35-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="e9c35-126">Configuration Files</span></span>  
 <span data-ttu-id="e9c35-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9c35-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9c35-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9c35-128">Example</span></span>  
 <span data-ttu-id="e9c35-129">Im folgenden Beispiel wird die Standard-Authentifizierungsmodule.</span><span class="sxs-lookup"><span data-stu-id="e9c35-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="e9c35-130">Sie sollten die Werte für die Version und ' PublicKeyToken ' machen durch die richtigen Werte für das angegebene Modul ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e9c35-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9c35-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9c35-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="e9c35-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e9c35-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
