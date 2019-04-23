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
ms.openlocfilehash: 0eb3ef7db422d5cbbe70bd5633798b8d3787452d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125252"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="1f86f-102">\<Entfernen Sie >-Element für AuthenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1f86f-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="1f86f-103">Entfernt ein Authentifizierungsmodul aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="1f86f-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="1f86f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1f86f-104">\<configuration></span></span>  
<span data-ttu-id="1f86f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1f86f-105">\<system.net></span></span>  
<span data-ttu-id="1f86f-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="1f86f-106">\<authenticationModules></span></span>  
<span data-ttu-id="1f86f-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="1f86f-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f86f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f86f-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f86f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1f86f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1f86f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1f86f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f86f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1f86f-111">Attributes</span></span>  
  
|<span data-ttu-id="1f86f-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="1f86f-112">**Attribute**</span></span>|<span data-ttu-id="1f86f-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1f86f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="1f86f-114">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1f86f-114">**type**</span></span>|<span data-ttu-id="1f86f-115">Der Name des Authentifizierungsmoduls "zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1f86f-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f86f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1f86f-116">Child Elements</span></span>  
 <span data-ttu-id="1f86f-117">Keine</span><span class="sxs-lookup"><span data-stu-id="1f86f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f86f-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1f86f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1f86f-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="1f86f-119">**Element**</span></span>|<span data-ttu-id="1f86f-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1f86f-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1f86f-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="1f86f-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="1f86f-122">Gibt die Module, die zum Authentifizieren von netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="1f86f-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f86f-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1f86f-123">Remarks</span></span>  
 <span data-ttu-id="1f86f-124">Die `remove` Element entfernt die Authentifizierungsmodule, die weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1f86f-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="1f86f-125">Der Wert für die `type` Attribut sollte ein gültiger Klassenname sein.</span><span class="sxs-lookup"><span data-stu-id="1f86f-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1f86f-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="1f86f-126">Configuration Files</span></span>  
 <span data-ttu-id="1f86f-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f86f-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f86f-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f86f-128">Example</span></span>  
 <span data-ttu-id="1f86f-129">Im folgende Beispiel entfernt ein Authentifizierungsmodul.</span><span class="sxs-lookup"><span data-stu-id="1f86f-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f86f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f86f-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="1f86f-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1f86f-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
