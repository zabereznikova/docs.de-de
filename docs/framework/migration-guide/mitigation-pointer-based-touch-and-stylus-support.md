---
title: 'Entschärfung: Zeigerbasierte Touch- und Stiftunterstützung'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 6b3e8068be2f5ed82c483b760fe100ea0a751588
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457856"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="9a5b9-102">Entschärfung: Zeigerbasierte Touch- und Stiftunterstützung</span><span class="sxs-lookup"><span data-stu-id="9a5b9-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="9a5b9-103">WPF-Anwendungen mit der Zielplattform .NET Framework 4.7, die auf Windows-Systemen ab Windows 10 Creators Update ausgeführt werden, können einen optionalen `WM_POINTER`-basierten WPF-Touch/Stift-Stapel aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-103">WPF applications that target the .NET Framework 4.7 and are running on Windows Systems starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="9a5b9-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="9a5b9-104">Impact</span></span>

<span data-ttu-id="9a5b9-105">Entwickler, die nicht explizit die zeigerbasierte Touch/Stift-Unterstützung aktivieren, sollten keine Änderung im WPF-Touch/Stift-Verhalten feststellen.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="9a5b9-106">Im Folgenden sind die aktuell bekannten Probleme beim optionalen `WM_POINTER`-basierten Touch/Stift-Stapel aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="9a5b9-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="9a5b9-107">Keine Unterstützung für Freihand in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-107">No support for real-time inking.</span></span>

   <span data-ttu-id="9a5b9-108">Zwar funktionieren Freihand- und Stift-Plug-Ins nach wie vor, sie werden aber im Benutzeroberflächen-Thread verarbeitet, was zu schlechter Leistung führen kann.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="9a5b9-109">Verhaltensänderungen aufgrund der Verlagerung von Touch/Stift-Ereignissen zu Mausereignissen.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="9a5b9-110">Die Bearbeitung verhält sich möglicherweise anders.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="9a5b9-111">Drag/Drop zeigt keine angemessene Rückmeldung bei Toucheingaben.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="9a5b9-112">(Dies betrifft keine Stifteingaben.)</span><span class="sxs-lookup"><span data-stu-id="9a5b9-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="9a5b9-113">Drag/Drop kann für Touch/Stift-Ereignisse nicht mehr ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="9a5b9-114">Dadurch kann es vorkommen, dass die Anwendung nicht reagiert, bis die Mauseingabe erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-114">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="9a5b9-115">Stattdessen sollten Entwickler Drag & Drop über Mausereignisse einleiten.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="9a5b9-116">Entscheidung für die WM_POINTER-basierte Touch/Stift-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="9a5b9-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="9a5b9-117">Entwickler, die diesen Stapel aktivieren möchten, können der app.config-Datei ihrer Anwendung Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9a5b9-117">Developers who wish to enable this stack can add the following to their application's app.config file:</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="9a5b9-118">Das Entfernen dieses Eintrags oder das Festlegen seines Werts auf `false` deaktiviert diesen optionalen Stapel.</span><span class="sxs-lookup"><span data-stu-id="9a5b9-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a5b9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a5b9-119">See also</span></span>

- [<span data-ttu-id="9a5b9-120">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="9a5b9-120">Application compatibility</span></span>](application-compatibility.md)
