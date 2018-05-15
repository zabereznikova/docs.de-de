---
title: '&lt;Deaktivieren Sie&gt; AuthenticationModules (Network Settings)-Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 94e0242ca685e8b0118a55ba44fb0569c13f10f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="9f7a9-102">&lt;Deaktivieren Sie&gt; AuthenticationModules (Network Settings)-Element</span><span class="sxs-lookup"><span data-stu-id="9f7a9-102">&lt;clear&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="9f7a9-103">Löscht alle Authentifizierungsmodule aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="9f7a9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9f7a9-104">\<configuration></span></span>  
<span data-ttu-id="9f7a9-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9f7a9-105">\<system.net></span></span>  
<span data-ttu-id="9f7a9-106">\<AuthenticationModules ></span><span class="sxs-lookup"><span data-stu-id="9f7a9-106">\<authenticationModules></span></span>  
<span data-ttu-id="9f7a9-107">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="9f7a9-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f7a9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f7a9-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f7a9-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9f7a9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9f7a9-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f7a9-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9f7a9-111">Attributes</span></span>  
 <span data-ttu-id="9f7a9-112">Keine</span><span class="sxs-lookup"><span data-stu-id="9f7a9-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9f7a9-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f7a9-113">Child Elements</span></span>  
 <span data-ttu-id="9f7a9-114">Keine</span><span class="sxs-lookup"><span data-stu-id="9f7a9-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f7a9-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f7a9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="9f7a9-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="9f7a9-116">**Element**</span></span>|<span data-ttu-id="9f7a9-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9f7a9-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9f7a9-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="9f7a9-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="9f7a9-119">Gibt die Module, die zum Authentifizieren von Anforderungen über das Netzwerk verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f7a9-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f7a9-120">Remarks</span></span>  
 <span data-ttu-id="9f7a9-121">Die `clear` -Element entfernt alle Authentifizierungsmodule, die weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9f7a9-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="9f7a9-122">Configuration Files</span></span>  
 <span data-ttu-id="9f7a9-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f7a9-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f7a9-124">Example</span></span>  
 <span data-ttu-id="9f7a9-125">Im folgende Beispiel entfernt alle konfigurierten Authentifizierungsmodule.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f7a9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f7a9-126">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="9f7a9-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9f7a9-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
