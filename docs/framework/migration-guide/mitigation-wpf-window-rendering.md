---
title: 'Entschärfung: Rendern von WPF-Fenstern'
description: Hier erfahren Sie mehr über die Auswirkung und Entschärfung für das Rendern von WPF-Fenstern in .NET Framework 4.6 unter Windows 8 oder höher.
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
ms.openlocfilehash: d624478d17a4076107438f71b0a86eeb6d9f3ea4
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475332"
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="bef49-103">Entschärfung: Rendern von WPF-Fenstern</span><span class="sxs-lookup"><span data-stu-id="bef49-103">Mitigation: WPF Window Rendering</span></span>

<span data-ttu-id="bef49-104">In .NET Framework 4.6, das auf Windows 8 und höher ausgeführt wird, wird das gesamte Fenster ohne Clipping gerendert, wenn es in einem Szenario mit mehreren Monitoren außerhalb einer einzelnen Anzeige liegt.</span><span class="sxs-lookup"><span data-stu-id="bef49-104">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>

## <a name="impact"></a><span data-ttu-id="bef49-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="bef49-105">Impact</span></span>

<span data-ttu-id="bef49-106">Im Allgemeinen handelt es sich beim Rendering eines Fensters über mehrere Monitore hinweg ohne Clipping um ein erwartetes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="bef49-106">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="bef49-107">Unter Windows 7 und früher ist jedoch ein Clipping der WPF-Fenster zu beobachten, wenn sie über eine einzelne Anzeige hinausgehen, da sich das Rendern einer Teilmenge des Fensters für einen zweiten Monitor erheblich auf die Leistung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="bef49-107">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>

<span data-ttu-id="bef49-108">Die Auswirkung des Renderings von WPF-Fenstern über Monitore unter Windows 8 hinweg, lässt sich nicht genau quantifizieren, da es von einer Vielzahl von Faktoren abhängt.</span><span class="sxs-lookup"><span data-stu-id="bef49-108">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="bef49-109">In einigen Fällen führt dies möglicherweise weiterhin zu einer unerwünschten Auswirkung hinsichtlich der Leistung, insbesondere für Benutzer, die grafikintensive Anwendungen ausführen und über Fenster verfügen, die sich über mehrere Monitore hinweg erstrecken.</span><span class="sxs-lookup"><span data-stu-id="bef49-109">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="bef49-110">In anderen Fällen möchten Sie möglicherweise einfach ein einheitliches Verhalten über .NET Framework-Versionen hinweg sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="bef49-110">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>

## <a name="mitigation"></a><span data-ttu-id="bef49-111">Minderung</span><span class="sxs-lookup"><span data-stu-id="bef49-111">Mitigation</span></span>

<span data-ttu-id="bef49-112">Sie können diese Änderung deaktivieren und das vorherige Verhalten des Clippings eines WPF-Fensters wiederherstellen, wenn es über eine einzelne Anzeige hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="bef49-112">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="bef49-113">Hierfür gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="bef49-113">There are two ways to do this:</span></span>

- <span data-ttu-id="bef49-114">Durch das Hinzufügen des `<EnableMultiMonitorDisplayClipping>`-Elements zum Abschnitt `<appSettings>` Ihrer Anwendungskonfigurationsdatei können Sie dieses Verhalten in Apps auf Windows 8 oder höher deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bef49-114">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="bef49-115">Beispielsweise deaktiviert der folgende Konfigurationsabschnitt das Rendering ohne Clipping:</span><span class="sxs-lookup"><span data-stu-id="bef49-115">For example, the following configuration section disables rendering without clipping:</span></span>

  ```xml
  <appSettings>
      <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    </appSettings>
  ```

  <span data-ttu-id="bef49-116">Die `<EnableMultiMonitorDisplayClipping>`-Konfigurationseinstellung kann einen der zwei Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="bef49-116">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>

  - <span data-ttu-id="bef49-117">`true`, um das Clipping bei Fenstern zu aktivieren, um Grenzen beim Rendering zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="bef49-117">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>

  - <span data-ttu-id="bef49-118">`false`, um das Clipping bei Fenstern zu deaktivieren, um Grenzen beim Rendering zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="bef49-118">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>

- <span data-ttu-id="bef49-119">Durch das Festlegen der <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A>-Eigenschaft auf `true` beim Starten der App.</span><span class="sxs-lookup"><span data-stu-id="bef49-119">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>

## <a name="see-also"></a><span data-ttu-id="bef49-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bef49-120">See also</span></span>

- [<span data-ttu-id="bef49-121">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="bef49-121">Application compatibility</span></span>](application-compatibility.md)
