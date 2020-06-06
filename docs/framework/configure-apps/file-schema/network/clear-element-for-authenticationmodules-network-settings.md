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
ms.openlocfilehash: e3abd1b4c76ebda885703ccf961d58657b582f19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087510"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="13010-102">\<clear>-Element für authenticationModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="13010-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="13010-103">Löscht alle Authentifizierungs Module aus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="13010-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="13010-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13010-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13010-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="13010-105">Attributes and Elements</span></span>  
 <span data-ttu-id="13010-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13010-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13010-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="13010-107">Attributes</span></span>  
 <span data-ttu-id="13010-108">Keine</span><span class="sxs-lookup"><span data-stu-id="13010-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13010-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13010-109">Child Elements</span></span>  
 <span data-ttu-id="13010-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="13010-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13010-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13010-111">Parent Elements</span></span>  
  
|<span data-ttu-id="13010-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="13010-112">**Element**</span></span>|<span data-ttu-id="13010-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="13010-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="13010-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="13010-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="13010-115">Gibt Module an, die zum Authentifizieren von Netzwerk Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13010-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13010-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="13010-116">Remarks</span></span>  
 <span data-ttu-id="13010-117">Das- `clear` Element entfernt alle Authentifizierungs Module, die zuvor in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurations Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="13010-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="13010-118">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="13010-118">Configuration Files</span></span>  
 <span data-ttu-id="13010-119">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13010-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13010-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13010-120">Example</span></span>  
 <span data-ttu-id="13010-121">Im folgenden Beispiel werden alle konfigurierten Authentifizierungs Module entfernt.</span><span class="sxs-lookup"><span data-stu-id="13010-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13010-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13010-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="13010-123">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="13010-123">Network Settings Schema</span></span>](index.md)
