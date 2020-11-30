---
title: Optimierung für freigegebenes Webhosting
ms.date: 03/30/2017
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
ms.openlocfilehash: abab4ac451a70fbc81ac6d7c9da6f8d0123287a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669028"
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="130a3-102">Optimierung für freigegebenes Webhosting</span><span class="sxs-lookup"><span data-stu-id="130a3-102">Optimization for Shared Web Hosting</span></span>

<span data-ttu-id="130a3-103">Wenn Sie Administrator eines Servers sind, der zum Hosten von mehreren kleinen Websites freigegeben ist, können Sie die Leistung optimieren und die Websitekapazität erhöhen, indem Sie die folgende `gcTrimCommitOnLowMemory`-Einstellung für den `runtime`-Knoten in der Datei „aspnet.config“ im .NET-Verzeichnis festlegen:</span><span class="sxs-lookup"><span data-stu-id="130a3-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
> <span data-ttu-id="130a3-104">Diese Einstellung wird nur für freigegebene Webhostingszenarien empfohlen.</span><span class="sxs-lookup"><span data-stu-id="130a3-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="130a3-105">Da der Garbage Collector den Speicher für zukünftige Belegungen beibehält, kann sein belegter Speicher größer sein als der unbedingt erforderliche Speicher.</span><span class="sxs-lookup"><span data-stu-id="130a3-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="130a3-106">Sie können diesen Speicher im Hinblick auf Zeiten reduzieren, in denen eine hohe Auslastung des Systemspeichers vorherrscht.</span><span class="sxs-lookup"><span data-stu-id="130a3-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="130a3-107">Durch eine Reduzierung des belegten Speichers wird die Leistung verbessert und die Kapazität zum Hosten mehrerer Websites erweitert.</span><span class="sxs-lookup"><span data-stu-id="130a3-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="130a3-108">Wenn die Einstellung `gcTrimCommitOnLowMemory` aktiviert ist, wertet der Garbage Collector die Speichersystemlast aus und wechselt in einen eingeschränkten Modus, wenn die Last 90 % erreicht.</span><span class="sxs-lookup"><span data-stu-id="130a3-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="130a3-109">Dabei bleibt der eingeschränkte Modus bestehen, bis die Last unter 85 % fällt.</span><span class="sxs-lookup"><span data-stu-id="130a3-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="130a3-110">Wenn die Umstände es erlauben, kann der Garbage Collector veranlassen, dass die `gcTrimCommitOnLowMemory`-Einstellung nicht die aktuelle Anwendung unterstützt und diese ignoriert.</span><span class="sxs-lookup"><span data-stu-id="130a3-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="130a3-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="130a3-111">Example</span></span>  

 <span data-ttu-id="130a3-112">Das folgende XML-Fragment zeigt, wie die `gcTrimCommitOnLowMemory`-Einstellung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="130a3-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="130a3-113">Ellipsen weisen auf andere Einstellungen hin, die im `runtime`-Knoten festgelegt wären.</span><span class="sxs-lookup"><span data-stu-id="130a3-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="130a3-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="130a3-114">See also</span></span>

- [<span data-ttu-id="130a3-115">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="130a3-115">Garbage Collection</span></span>](index.md)
