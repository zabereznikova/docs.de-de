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
ms.openlocfilehash: dbad888cd0537f63c09840ac1053f924db9ea9bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089062"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="f9ae7-102">\<webProxyScript>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f9ae7-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="f9ae7-103">Konfiguriert die Merkmale des Skripts, das zum Ermitteln von Webproxys verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9ae7-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="f9ae7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9ae7-104">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9ae7-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ae7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f9ae7-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9ae7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9ae7-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9ae7-107">Attributes</span></span>  
  
|<span data-ttu-id="f9ae7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f9ae7-108">Attribute</span></span>|<span data-ttu-id="f9ae7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f9ae7-109">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="f9ae7-110">Gibt die maximale Zeit für das Herunterladen des Skripts in Stunden, Minuten und Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="f9ae7-110">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="f9ae7-111">Der Standardwert ist eine Minute.</span><span class="sxs-lookup"><span data-stu-id="f9ae7-111">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9ae7-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ae7-112">Child Elements</span></span>  
 <span data-ttu-id="f9ae7-113">Keine</span><span class="sxs-lookup"><span data-stu-id="f9ae7-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9ae7-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ae7-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f9ae7-115">Element</span><span class="sxs-lookup"><span data-stu-id="f9ae7-115">Element</span></span>|<span data-ttu-id="f9ae7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9ae7-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9ae7-117">settings</span><span class="sxs-lookup"><span data-stu-id="f9ae7-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="f9ae7-118">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="f9ae7-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9ae7-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f9ae7-119">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f9ae7-120">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="f9ae7-120">Configuration Files</span></span>  
 <span data-ttu-id="f9ae7-121">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9ae7-121">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ae7-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9ae7-122">See also</span></span>

- [<span data-ttu-id="f9ae7-123">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="f9ae7-123">Network Settings Schema</span></span>](index.md)
