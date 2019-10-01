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
ms.openlocfilehash: 052f7eef30500d37389585956728250a46b718a3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698396"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="631ec-102">\<clear >-Element für authenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="631ec-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="631ec-103">Löscht alle Authentifizierungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="631ec-103">Clears all authentication modules from the application.</span></span>  
  
[<span data-ttu-id="631ec-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="631ec-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="631ec-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="631ec-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="631ec-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<authenticationmodules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="631ec-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="631ec-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="631ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="631ec-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="631ec-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="631ec-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="631ec-109">Attributes and Elements</span></span>  
 <span data-ttu-id="631ec-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="631ec-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="631ec-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="631ec-111">Attributes</span></span>  
 <span data-ttu-id="631ec-112">Keine</span><span class="sxs-lookup"><span data-stu-id="631ec-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="631ec-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="631ec-113">Child Elements</span></span>  
 <span data-ttu-id="631ec-114">Keine</span><span class="sxs-lookup"><span data-stu-id="631ec-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="631ec-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="631ec-115">Parent Elements</span></span>  
  
|<span data-ttu-id="631ec-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="631ec-116">**Element**</span></span>|<span data-ttu-id="631ec-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="631ec-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="631ec-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="631ec-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="631ec-119">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="631ec-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="631ec-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="631ec-120">Remarks</span></span>  
 <span data-ttu-id="631ec-121">Das `clear`-Element entfernt alle Authentifizierungs Module, die zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="631ec-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="631ec-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="631ec-122">Configuration Files</span></span>  
 <span data-ttu-id="631ec-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="631ec-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="631ec-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="631ec-124">Example</span></span>  
 <span data-ttu-id="631ec-125">Im folgenden Beispiel werden alle konfigurierten Authentifizierungs Module entfernt.</span><span class="sxs-lookup"><span data-stu-id="631ec-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="631ec-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="631ec-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="631ec-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="631ec-127">Network Settings Schema</span></span>](index.md)
