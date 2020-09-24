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
ms.openlocfilehash: 6ac2287ba9b17727835d43a3e3b8876f210fb5c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167326"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="3a846-102">\<clear>-Element für authenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3a846-102">\<clear> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="3a846-103">Löscht alle Authentifizierungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3a846-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="3a846-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a846-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a846-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a846-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3a846-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a846-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a846-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a846-107">Attributes</span></span>  

 <span data-ttu-id="3a846-108">Keine</span><span class="sxs-lookup"><span data-stu-id="3a846-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a846-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a846-109">Child Elements</span></span>  

 <span data-ttu-id="3a846-110">Keine</span><span class="sxs-lookup"><span data-stu-id="3a846-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a846-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a846-111">Parent Elements</span></span>  
  
|<span data-ttu-id="3a846-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="3a846-112">**Element**</span></span>|<span data-ttu-id="3a846-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3a846-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3a846-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="3a846-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="3a846-115">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a846-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a846-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3a846-116">Remarks</span></span>  

 <span data-ttu-id="3a846-117">Das- `clear` Element entfernt alle Authentifizierungs Module, die zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3a846-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3a846-118">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="3a846-118">Configuration Files</span></span>  

 <span data-ttu-id="3a846-119">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a846-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a846-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a846-120">Example</span></span>  

 <span data-ttu-id="3a846-121">Im folgenden Beispiel werden alle konfigurierten Authentifizierungs Module entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a846-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a846-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a846-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="3a846-123">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3a846-123">Network Settings Schema</span></span>](index.md)
