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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 332f8eb4fb1a5a02df76c5745522037b029a2407
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47072791"
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="bf318-102">&lt;Entfernen Sie&gt; -Element für AuthenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="bf318-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="bf318-103">Entfernt ein Authentifizierungsmodul aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="bf318-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="bf318-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bf318-104">\<configuration></span></span>  
<span data-ttu-id="bf318-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="bf318-105">\<system.net></span></span>  
<span data-ttu-id="bf318-106">\<AuthenticationModules ></span><span class="sxs-lookup"><span data-stu-id="bf318-106">\<authenticationModules></span></span>  
<span data-ttu-id="bf318-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="bf318-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf318-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf318-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf318-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bf318-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bf318-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf318-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf318-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="bf318-111">Attributes</span></span>  
  
|<span data-ttu-id="bf318-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="bf318-112">**Attribute**</span></span>|<span data-ttu-id="bf318-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bf318-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="bf318-114">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bf318-114">**type**</span></span>|<span data-ttu-id="bf318-115">Der Name des Authentifizierungsmoduls "zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="bf318-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf318-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf318-116">Child Elements</span></span>  
 <span data-ttu-id="bf318-117">Keine</span><span class="sxs-lookup"><span data-stu-id="bf318-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf318-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf318-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bf318-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="bf318-119">**Element**</span></span>|<span data-ttu-id="bf318-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bf318-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bf318-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="bf318-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="bf318-122">Gibt die Module, die zum Authentifizieren von netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="bf318-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf318-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf318-123">Remarks</span></span>  
 <span data-ttu-id="bf318-124">Die `remove` Element entfernt die Authentifizierungsmodule, die weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bf318-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="bf318-125">Der Wert für die `type` Attribut sollte ein gültiger Klassenname sein.</span><span class="sxs-lookup"><span data-stu-id="bf318-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bf318-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="bf318-126">Configuration Files</span></span>  
 <span data-ttu-id="bf318-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bf318-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf318-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf318-128">Example</span></span>  
 <span data-ttu-id="bf318-129">Im folgende Beispiel entfernt ein Authentifizierungsmodul.</span><span class="sxs-lookup"><span data-stu-id="bf318-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf318-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf318-130">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="bf318-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="bf318-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
