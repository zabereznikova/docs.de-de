---
title: <clear>-Element für authenticationModules (Netzwerkeinstellungen)
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
ms.openlocfilehash: 12ac146926103b40073d34f48895b0645c8a8ed2
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659468"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="0d9e1-102">\<Löschen von >-Element für authenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0d9e1-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="0d9e1-103">Löscht alle Authentifizierungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="0d9e1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0d9e1-104">\<configuration></span></span>  
<span data-ttu-id="0d9e1-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="0d9e1-105">\<system.net></span></span>  
<span data-ttu-id="0d9e1-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="0d9e1-106">\<authenticationModules></span></span>  
<span data-ttu-id="0d9e1-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="0d9e1-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d9e1-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d9e1-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d9e1-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0d9e1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0d9e1-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d9e1-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="0d9e1-111">Attributes</span></span>  
 <span data-ttu-id="0d9e1-112">Keine</span><span class="sxs-lookup"><span data-stu-id="0d9e1-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d9e1-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d9e1-113">Child Elements</span></span>  
 <span data-ttu-id="0d9e1-114">Keine</span><span class="sxs-lookup"><span data-stu-id="0d9e1-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d9e1-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d9e1-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0d9e1-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="0d9e1-116">**Element**</span></span>|<span data-ttu-id="0d9e1-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0d9e1-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0d9e1-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="0d9e1-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="0d9e1-119">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d9e1-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d9e1-120">Remarks</span></span>  
 <span data-ttu-id="0d9e1-121">Das `clear` -Element entfernt alle Authentifizierungs Module, die zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0d9e1-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="0d9e1-122">Configuration Files</span></span>  
 <span data-ttu-id="0d9e1-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d9e1-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d9e1-124">Example</span></span>  
 <span data-ttu-id="0d9e1-125">Im folgenden Beispiel werden alle konfigurierten Authentifizierungs Module entfernt.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d9e1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d9e1-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="0d9e1-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0d9e1-127">Network Settings Schema</span></span>](index.md)
