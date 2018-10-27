---
title: '&lt;Entfernen Sie&gt; -Element für AuthenticationModules (Netzwerkeinstellungen)'
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
ms.openlocfilehash: 65b5b7f717912ecaee73a5b24e65d22b902a4e44
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180704"
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="69dc2-102">&lt;Entfernen Sie&gt; -Element für AuthenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="69dc2-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="69dc2-103">Entfernt ein Authentifizierungsmodul aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="69dc2-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="69dc2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="69dc2-104">\<configuration></span></span>  
<span data-ttu-id="69dc2-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="69dc2-105">\<system.net></span></span>  
<span data-ttu-id="69dc2-106">\<AuthenticationModules ></span><span class="sxs-lookup"><span data-stu-id="69dc2-106">\<authenticationModules></span></span>  
<span data-ttu-id="69dc2-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="69dc2-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69dc2-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="69dc2-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69dc2-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69dc2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="69dc2-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69dc2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69dc2-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="69dc2-111">Attributes</span></span>  
  
|<span data-ttu-id="69dc2-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="69dc2-112">**Attribute**</span></span>|<span data-ttu-id="69dc2-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="69dc2-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="69dc2-114">**Typ**</span><span class="sxs-lookup"><span data-stu-id="69dc2-114">**type**</span></span>|<span data-ttu-id="69dc2-115">Der Name des Authentifizierungsmoduls "zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="69dc2-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69dc2-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69dc2-116">Child Elements</span></span>  
 <span data-ttu-id="69dc2-117">Keine</span><span class="sxs-lookup"><span data-stu-id="69dc2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69dc2-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69dc2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="69dc2-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="69dc2-119">**Element**</span></span>|<span data-ttu-id="69dc2-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="69dc2-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="69dc2-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="69dc2-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="69dc2-122">Gibt die Module, die zum Authentifizieren von netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="69dc2-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69dc2-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69dc2-123">Remarks</span></span>  
 <span data-ttu-id="69dc2-124">Die `remove` Element entfernt die Authentifizierungsmodule, die weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="69dc2-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="69dc2-125">Der Wert für die `type` Attribut sollte ein gültiger Klassenname sein.</span><span class="sxs-lookup"><span data-stu-id="69dc2-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="69dc2-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="69dc2-126">Configuration Files</span></span>  
 <span data-ttu-id="69dc2-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69dc2-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69dc2-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69dc2-128">Example</span></span>  
 <span data-ttu-id="69dc2-129">Im folgende Beispiel entfernt ein Authentifizierungsmodul.</span><span class="sxs-lookup"><span data-stu-id="69dc2-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="69dc2-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69dc2-130">See Also</span></span>  
- <xref:System.Net.IAuthenticationModule>  
- <xref:System.Net.AuthenticationManager>  
- [<span data-ttu-id="69dc2-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="69dc2-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
