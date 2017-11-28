---
title: "Entschärfung: Rendern von WPF-Fenstern"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 57d4cc56cc8d3a4dc3614043779eb09d7a8b8e25
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="fb43d-102">Entschärfung: Rendern von WPF-Fenstern</span><span class="sxs-lookup"><span data-stu-id="fb43d-102">Mitigation: WPF Window Rendering</span></span>
<span data-ttu-id="fb43d-103">In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], das auf Windows 8 und höher ausgeführt wird, wird das gesamte Fenster ohne Clipping gerendert, wenn es in einem Szenario mit mehreren Monitoren außerhalb einer einzelnen Anzeige liegt.</span><span class="sxs-lookup"><span data-stu-id="fb43d-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="fb43d-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="fb43d-104">Impact</span></span>  
 <span data-ttu-id="fb43d-105">Im Allgemeinen handelt es sich beim Rendering eines Fensters über mehrere Monitore hinweg ohne Clipping um ein erwartetes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="fb43d-105">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="fb43d-106">Unter Windows 7 und früher ist jedoch ein Clipping der WPF-Fenster zu beobachten, wenn sie über eine einzelne Anzeige hinausgehen, da sich das Rendern einer Teilmenge des Fensters für einen zweiten Monitor erheblich auf die Leistung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="fb43d-106">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>  
  
 <span data-ttu-id="fb43d-107">Die Auswirkung des Renderings von WPF-Fenstern über Monitore unter Windows 8 hinweg, lässt sich nicht genau quantifizieren, da es von einer Vielzahl von Faktoren abhängt.</span><span class="sxs-lookup"><span data-stu-id="fb43d-107">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="fb43d-108">In einigen Fällen führt dies möglicherweise weiterhin zu einer unerwünschten Auswirkung hinsichtlich der Leistung, insbesondere für Benutzer, die grafikintensive Anwendungen ausführen und über Fenster verfügen, die sich über mehrere Monitore hinweg erstrecken.</span><span class="sxs-lookup"><span data-stu-id="fb43d-108">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="fb43d-109">In anderen Fällen möchten Sie möglicherweise einfach ein einheitliches Verhalten über .NET Framework-Versionen hinweg sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="fb43d-109">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="fb43d-110">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="fb43d-110">Mitigation</span></span>  
 <span data-ttu-id="fb43d-111">Sie können diese Änderung deaktivieren und das vorherige Verhalten des Clippings eines WPF-Fensters wiederherstellen, wenn es über eine einzelne Anzeige hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="fb43d-111">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="fb43d-112">Hierfür gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="fb43d-112">There are two ways to do this:</span></span>  
  
-   <span data-ttu-id="fb43d-113">Durch das Hinzufügen des `<EnableMultiMonitorDisplayClipping>`-Elements zum Abschnitt `<appSettings>` Ihrer Anwendungskonfigurationsdatei können Sie dieses Verhalten in Apps auf Windows 8 oder höher deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb43d-113">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="fb43d-114">Beispielsweise deaktiviert der folgende Konfigurationsabschnitt das Rendering ohne Clipping:</span><span class="sxs-lookup"><span data-stu-id="fb43d-114">For example, the following configuration section disables rendering without clipping:</span></span>  
  
    ```xml  
    <appSettings>  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
      </appSettings>  
    ```  
  
     <span data-ttu-id="fb43d-115">Die `<EnableMultiMonitorDisplayClipping>`-Konfigurationseinstellung kann einen der zwei Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="fb43d-115">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>  
  
    -   <span data-ttu-id="fb43d-116">`true`, um das Clipping bei Fenstern zu aktivieren, um Grenzen beim Rendering zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="fb43d-116">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>  
  
    -   <span data-ttu-id="fb43d-117">`false`, um das Clipping bei Fenstern zu deaktivieren, um Grenzen beim Rendering zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="fb43d-117">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>  
  
-   <span data-ttu-id="fb43d-118">Durch das Festlegen der <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A>-Eigenschaft auf `true` beim Starten der App.</span><span class="sxs-lookup"><span data-stu-id="fb43d-118">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb43d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb43d-119">See Also</span></span>  
 [<span data-ttu-id="fb43d-120">Änderungen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fb43d-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
