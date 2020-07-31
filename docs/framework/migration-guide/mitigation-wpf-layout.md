---
title: 'Entschärfung: WPF-Layout'
description: Hier erfahren Sie, wie Sie Probleme beheben, die von einer Änderung des WPF-Layouts für Steuerelemente verursacht werden, z. B. durch die Platzierung eines Objekts durch Verschiebung um einen Pixel.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: e4e4612f7b39eefbf0e76ac86c8eb644c257ba75
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475345"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="629e0-103">Entschärfung: WPF-Layout</span><span class="sxs-lookup"><span data-stu-id="629e0-103">Mitigation: WPF Layout</span></span>
<span data-ttu-id="629e0-104">Das Layout der WPF-Steuerelemente kann sich leicht ändern.</span><span class="sxs-lookup"><span data-stu-id="629e0-104">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="629e0-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="629e0-105">Impact</span></span>  
 <span data-ttu-id="629e0-106">Auswirkungen durch diese Änderung:</span><span class="sxs-lookup"><span data-stu-id="629e0-106">As a result of this change:</span></span>  
  
- <span data-ttu-id="629e0-107">Die Breite oder Höhe der Elemente vergrößert oder verkleinert sich allenfalls um einen Pixel.</span><span class="sxs-lookup"><span data-stu-id="629e0-107">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="629e0-108">Die Platzierung eines Objekts kann sich allenfalls um einen Pixel verschieben.</span><span class="sxs-lookup"><span data-stu-id="629e0-108">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="629e0-109">Zentrierte Elemente können sich vertikal oder horizontal um allenfalls ein Pixel von der Mitte verschieben.</span><span class="sxs-lookup"><span data-stu-id="629e0-109">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="629e0-110">Standardmäßig wird dieses neue Layout nur für Apps aktiviert, die auf .NET Framework 4.6 abzielen.</span><span class="sxs-lookup"><span data-stu-id="629e0-110">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="629e0-111">Minderung</span><span class="sxs-lookup"><span data-stu-id="629e0-111">Mitigation</span></span>  
 <span data-ttu-id="629e0-112">Da durch diese Änderung das Clipping die rechte oder Unterseite von WPF-Steuerelementen bei hohen DPIs beseitigt wird, können Apps, die auf frühere Versionen von .NET Framework abzielen, aber auf .NET Framework 4.6 ausgeführt werden, dieses neue Verhalten übernehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="629e0-112">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="629e0-113">Apps, die auf .NET Framework 4.6 abzielen, aber WPF-Steuerelemente zum Rendern mithilfe des vorherigen Layoutalgorithmus verwenden möchten, können dies vornehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="629e0-113">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="629e0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="629e0-114">See also</span></span>

- [<span data-ttu-id="629e0-115">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="629e0-115">Application compatibility</span></span>](application-compatibility.md)
