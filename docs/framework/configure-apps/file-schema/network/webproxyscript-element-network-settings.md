---
title: <webProxyScript>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: 8a77c2567401fd80e355bb7fcee17b6684653ebe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659044"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="02c41-102">\<WebProxyScript >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="02c41-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="02c41-103">Konfiguriert die Merkmale des Skripts, das zum Ermitteln von Webproxys verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02c41-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="02c41-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="02c41-104">\<configuration></span></span>  
<span data-ttu-id="02c41-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="02c41-105">\<system.net></span></span>  
<span data-ttu-id="02c41-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="02c41-106">\<settings></span></span>  
<span data-ttu-id="02c41-107">\<webProxyScript></span><span class="sxs-lookup"><span data-stu-id="02c41-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c41-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="02c41-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02c41-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02c41-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02c41-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02c41-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02c41-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="02c41-111">Attributes</span></span>  
  
|<span data-ttu-id="02c41-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="02c41-112">Attribute</span></span>|<span data-ttu-id="02c41-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02c41-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="02c41-114">Gibt die maximale Zeit für das Herunterladen des Skripts in Stunden, Minuten und Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="02c41-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="02c41-115">Der Standardwert ist eine Minute.</span><span class="sxs-lookup"><span data-stu-id="02c41-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02c41-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02c41-116">Child Elements</span></span>  
 <span data-ttu-id="02c41-117">Keine</span><span class="sxs-lookup"><span data-stu-id="02c41-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02c41-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02c41-118">Parent Elements</span></span>  
  
|<span data-ttu-id="02c41-119">Element</span><span class="sxs-lookup"><span data-stu-id="02c41-119">Element</span></span>|<span data-ttu-id="02c41-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02c41-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02c41-121">settings</span><span class="sxs-lookup"><span data-stu-id="02c41-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="02c41-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="02c41-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02c41-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02c41-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="02c41-124">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="02c41-124">Configuration Files</span></span>  
 <span data-ttu-id="02c41-125">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02c41-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c41-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02c41-126">See also</span></span>

- [<span data-ttu-id="02c41-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="02c41-127">Network Settings Schema</span></span>](index.md)
