---
title: "Optimierung für freigegebenes Webhosting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="1b7dc-102">Optimierung für freigegebenes Webhosting</span><span class="sxs-lookup"><span data-stu-id="1b7dc-102">Optimization for Shared Web Hosting</span></span>
<span data-ttu-id="1b7dc-103">Wenn Sie eine Server-Administrator, die sind durch das Hosten von mehreren kleinen Websites gemeinsam verwendet wird, können Sie Optimieren der Leistung und Websitekapazität erhöhen, indem Sie den folgenden Code `gcTrimCommitOnLowMemory` zum Festlegen der `runtime` Knoten in der Aspnet.config-Datei in .NET Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="1b7dc-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  <span data-ttu-id="1b7dc-104">Diese Einstellung ist nur für freigegebene Web empfohlen Hostingszenarien.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="1b7dc-105">Da der Garbage Collector den Speicher für zukünftige belegungen bereit beibehält, kann seine belegter Speicher mehr als unbedingt erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="1b7dc-106">Sie können diesen Speicher angepasst Zeiten reduzieren bei hoher Auslastung auf dem Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="1b7dc-107">Reduzierung des belegten Speichers verbessert die Leistung und erweitert die Kapazität für mehrere Websites hosten.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="1b7dc-108">Wenn die `gcTrimCommitOnLowMemory` aktiviert ist, wird der Garbage Collector wertet die Arbeitsspeicher-Systemlast und einen Modus eingibt, wenn die Last über 90 % erreicht.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="1b7dc-109">Dabei wird der Modus beibehalten, bis wieder die Last unter 85 % liegt.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="1b7dc-110">Wenn Umstände es erlauben, kann der Garbage Collector entscheiden, die die `gcTrimCommitOnLowMemory` Einstellung nicht die aktuelle Anwendung helfen und ignorieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b7dc-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b7dc-111">Example</span></span>  
 <span data-ttu-id="1b7dc-112">Das folgende XML-Fragment zeigt, wie zum Aktivieren der `gcTrimCommitOnLowMemory` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="1b7dc-113">Ellipsen kennzeichnen andere Einstellungen, die bei der `runtime` Knoten.</span><span class="sxs-lookup"><span data-stu-id="1b7dc-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b7dc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b7dc-114">See Also</span></span>  
 [<span data-ttu-id="1b7dc-115">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="1b7dc-115">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
