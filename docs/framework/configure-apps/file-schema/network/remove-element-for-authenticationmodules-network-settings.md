---
title: <remove>-Element für authenticationModules (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: d171fea193bbae068e69b8976abb8e56a5623f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154776"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="dde1d-102">\<Entfernen> Element für authentifizierungModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="dde1d-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="dde1d-103">Entfernt ein Authentifizierungsmodul aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="dde1d-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="dde1d-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dde1d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dde1d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dde1d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="dde1d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authentifizierungModule>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dde1d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="dde1d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entfernen sie>**</span><span class="sxs-lookup"><span data-stu-id="dde1d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="dde1d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="dde1d-108">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dde1d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dde1d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dde1d-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dde1d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dde1d-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="dde1d-111">Attributes</span></span>  
  
|<span data-ttu-id="dde1d-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="dde1d-112">**Attribute**</span></span>|<span data-ttu-id="dde1d-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dde1d-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="dde1d-114">**Typ**</span><span class="sxs-lookup"><span data-stu-id="dde1d-114">**type**</span></span>|<span data-ttu-id="dde1d-115">Der Name des zu entfernenden Authentifizierungsmoduls.</span><span class="sxs-lookup"><span data-stu-id="dde1d-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dde1d-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dde1d-116">Child Elements</span></span>  
 <span data-ttu-id="dde1d-117">Keine.</span><span class="sxs-lookup"><span data-stu-id="dde1d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dde1d-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dde1d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dde1d-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="dde1d-119">**Element**</span></span>|<span data-ttu-id="dde1d-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dde1d-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dde1d-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="dde1d-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="dde1d-122">Gibt Module an, die zum Authentifizieren von Netzwerkanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dde1d-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dde1d-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dde1d-123">Remarks</span></span>  
 <span data-ttu-id="dde1d-124">Das `remove` Element entfernt Authentifizierungsmodule, die zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dde1d-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="dde1d-125">Der Wert `type` für das Attribut sollte ein gültiger Klassenname sein.</span><span class="sxs-lookup"><span data-stu-id="dde1d-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="dde1d-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="dde1d-126">Configuration Files</span></span>  
 <span data-ttu-id="dde1d-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dde1d-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dde1d-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dde1d-128">Example</span></span>  
 <span data-ttu-id="dde1d-129">Im folgenden Beispiel wird ein Authentifizierungsmodul entfernt.</span><span class="sxs-lookup"><span data-stu-id="dde1d-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dde1d-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dde1d-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="dde1d-131">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="dde1d-131">Network Settings Schema</span></span>](index.md)
