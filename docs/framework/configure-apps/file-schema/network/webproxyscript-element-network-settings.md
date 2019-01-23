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
ms.openlocfilehash: 580fcb17c16c4f5de137b8aa298db68c44867c52
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536268"
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="2e15f-102">&lt;WebProxyScript&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2e15f-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="2e15f-103">Konfiguriert die Eigenschaften des Skripts zur Ermittlung von Webproxys, verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e15f-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="2e15f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2e15f-104">\<configuration></span></span>  
<span data-ttu-id="2e15f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2e15f-105">\<system.net></span></span>  
<span data-ttu-id="2e15f-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="2e15f-106">\<settings></span></span>  
<span data-ttu-id="2e15f-107">\<webProxyScript></span><span class="sxs-lookup"><span data-stu-id="2e15f-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e15f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e15f-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e15f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2e15f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2e15f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e15f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e15f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2e15f-111">Attributes</span></span>  
  
|<span data-ttu-id="2e15f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2e15f-112">Attribute</span></span>|<span data-ttu-id="2e15f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e15f-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="2e15f-114">Gibt die maximale Zeit, in Stunden, Minuten und Sekunden das Skript herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2e15f-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="2e15f-115">Der Standardwert beträgt eine Minute.</span><span class="sxs-lookup"><span data-stu-id="2e15f-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e15f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e15f-116">Child Elements</span></span>  
 <span data-ttu-id="2e15f-117">Keine</span><span class="sxs-lookup"><span data-stu-id="2e15f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e15f-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e15f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2e15f-119">Element</span><span class="sxs-lookup"><span data-stu-id="2e15f-119">Element</span></span>|<span data-ttu-id="2e15f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e15f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e15f-121">settings</span><span class="sxs-lookup"><span data-stu-id="2e15f-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="2e15f-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="2e15f-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e15f-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e15f-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2e15f-124">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="2e15f-124">Configuration Files</span></span>  
 <span data-ttu-id="2e15f-125">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e15f-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e15f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e15f-126">See also</span></span>
- [<span data-ttu-id="2e15f-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2e15f-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
