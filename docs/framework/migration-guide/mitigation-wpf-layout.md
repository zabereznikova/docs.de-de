---
title: 'Entschärfung: WPF-Layout'
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d266ad33110d2bda8f7911d89981c372624c3f36
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779066"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="02368-102">Entschärfung: WPF-Layout</span><span class="sxs-lookup"><span data-stu-id="02368-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="02368-103">Das Layout der WPF-Steuerelemente kann sich leicht ändern.</span><span class="sxs-lookup"><span data-stu-id="02368-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="02368-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="02368-104">Impact</span></span>  
 <span data-ttu-id="02368-105">Auswirkungen durch diese Änderung:</span><span class="sxs-lookup"><span data-stu-id="02368-105">As a result of this change:</span></span>  
  
- <span data-ttu-id="02368-106">Die Breite oder Höhe der Elemente vergrößert oder verkleinert sich allenfalls um einen Pixel.</span><span class="sxs-lookup"><span data-stu-id="02368-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="02368-107">Die Platzierung eines Objekts kann sich allenfalls um einen Pixel verschieben.</span><span class="sxs-lookup"><span data-stu-id="02368-107">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="02368-108">Zentrierte Elemente können sich vertikal oder horizontal um allenfalls ein Pixel von der Mitte verschieben.</span><span class="sxs-lookup"><span data-stu-id="02368-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="02368-109">Standardmäßig wird dieses neue Layout nur für Apps aktiviert, die auf .NET Framework 4.6 abzielen.</span><span class="sxs-lookup"><span data-stu-id="02368-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="02368-110">Minderung</span><span class="sxs-lookup"><span data-stu-id="02368-110">Mitigation</span></span>  
 <span data-ttu-id="02368-111">Da durch diese Änderung das Clipping die rechte oder Unterseite von WPF-Steuerelementen bei hohen DPIs beseitigt wird, können Apps, die auf frühere Versionen von .NET Framework abzielen, aber auf .NET Framework 4.6 ausgeführt werden, dieses neue Verhalten übernehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="02368-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="02368-112">Apps, die auf .NET Framework 4.6 abzielen, aber WPF-Steuerelemente zum Rendern mithilfe des vorherigen Layoutalgorithmus verwenden möchten, können dies vornehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="02368-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="02368-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02368-113">See also</span></span>

- [<span data-ttu-id="02368-114">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="02368-114">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6.md)
