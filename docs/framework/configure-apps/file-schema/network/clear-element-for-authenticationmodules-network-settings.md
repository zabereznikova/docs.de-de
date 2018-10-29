---
title: '&lt;Deaktivieren Sie&gt; -Element für AuthenticationModules (Netzwerkeinstellungen)'
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
ms.openlocfilehash: 42fa6a44891e012300f61f1a11a47537c6739e2c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205190"
---
# <a name="ltcleargt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="6b02e-102">&lt;Deaktivieren Sie&gt; -Element für AuthenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6b02e-102">&lt;clear&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="6b02e-103">Löscht alle Authentifizierungsmodule aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="6b02e-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="6b02e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6b02e-104">\<configuration></span></span>  
<span data-ttu-id="6b02e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6b02e-105">\<system.net></span></span>  
<span data-ttu-id="6b02e-106">\<AuthenticationModules ></span><span class="sxs-lookup"><span data-stu-id="6b02e-106">\<authenticationModules></span></span>  
<span data-ttu-id="6b02e-107">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="6b02e-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b02e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b02e-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b02e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b02e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6b02e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b02e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b02e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b02e-111">Attributes</span></span>  
 <span data-ttu-id="6b02e-112">Keine</span><span class="sxs-lookup"><span data-stu-id="6b02e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6b02e-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b02e-113">Child Elements</span></span>  
 <span data-ttu-id="6b02e-114">Keine</span><span class="sxs-lookup"><span data-stu-id="6b02e-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b02e-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b02e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6b02e-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="6b02e-116">**Element**</span></span>|<span data-ttu-id="6b02e-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6b02e-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6b02e-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="6b02e-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="6b02e-119">Gibt die Module, die zum Authentifizieren von netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6b02e-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b02e-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b02e-120">Remarks</span></span>  
 <span data-ttu-id="6b02e-121">Die `clear` -Element entfernt alle Authentifizierungsmodule, die weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6b02e-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6b02e-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="6b02e-122">Configuration Files</span></span>  
 <span data-ttu-id="6b02e-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b02e-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b02e-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b02e-124">Example</span></span>  
 <span data-ttu-id="6b02e-125">Im folgende Beispiel werden alle konfigurierten Authentifizierung-Module entfernt.</span><span class="sxs-lookup"><span data-stu-id="6b02e-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b02e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b02e-126">See Also</span></span>  
- <xref:System.Net.IAuthenticationModule>  
- <xref:System.Net.AuthenticationManager>  
- [<span data-ttu-id="6b02e-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6b02e-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
