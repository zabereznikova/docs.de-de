---
title: '&lt;WebProxyScript&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1e1450d2df424b32aacc5c113b5936001f65915a
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862736"
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="1ac87-102">&lt;WebProxyScript&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1ac87-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="1ac87-103">Konfiguriert die Eigenschaften des Skripts zur Ermittlung von Webproxys, verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ac87-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="1ac87-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1ac87-104">\<configuration></span></span>  
<span data-ttu-id="1ac87-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1ac87-105">\<system.net></span></span>  
<span data-ttu-id="1ac87-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="1ac87-106">\<settings></span></span>  
<span data-ttu-id="1ac87-107">\<WebProxyScript ></span><span class="sxs-lookup"><span data-stu-id="1ac87-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ac87-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ac87-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ac87-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1ac87-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1ac87-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ac87-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ac87-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1ac87-111">Attributes</span></span>  
  
|<span data-ttu-id="1ac87-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="1ac87-112">Attribute</span></span>|<span data-ttu-id="1ac87-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ac87-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="1ac87-114">Gibt die maximale Zeit, in Stunden, Minuten und Sekunden das Skript herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1ac87-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="1ac87-115">Der Standardwert beträgt eine Minute.</span><span class="sxs-lookup"><span data-stu-id="1ac87-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ac87-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ac87-116">Child Elements</span></span>  
 <span data-ttu-id="1ac87-117">Keine</span><span class="sxs-lookup"><span data-stu-id="1ac87-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ac87-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ac87-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1ac87-119">Element</span><span class="sxs-lookup"><span data-stu-id="1ac87-119">Element</span></span>|<span data-ttu-id="1ac87-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ac87-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ac87-121">settings</span><span class="sxs-lookup"><span data-stu-id="1ac87-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="1ac87-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="1ac87-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ac87-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ac87-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1ac87-124">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="1ac87-124">Configuration Files</span></span>  
 <span data-ttu-id="1ac87-125">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ac87-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ac87-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ac87-126">See Also</span></span>  
 [<span data-ttu-id="1ac87-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1ac87-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
