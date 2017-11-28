---
title: "Entschärfung: Zeigerbasierte Touch- und Stiftunterstützung"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
caps.latest.revision: "2"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 053ff4c5fba7b4f2b5a4c29a35c954e888cb095a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="4d7bb-102">Entschärfung: Zeigerbasierte Touch- und Stiftunterstützung</span><span class="sxs-lookup"><span data-stu-id="4d7bb-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="4d7bb-103">WPF-Anwendungen mit der Zielplattform .NET Framework 4.7, die auf Windows-Systemen ab Windows 10 Creators Update ausgeführt werden, können einen optionalen `WM_POINTER`-basierten WPF-Touch/Stift-Stapel aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-103">WPF applications that target the .NET Framework 4.7 and are running on Windows Systems starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="4d7bb-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="4d7bb-104">Impact</span></span>

<span data-ttu-id="4d7bb-105">Entwickler, die nicht explizit die zeigerbasierte Touch/Stift-Unterstützung aktivieren, sollten keine Änderung im WPF-Touch/Stift-Verhalten feststellen.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="4d7bb-106">Im Folgenden sind die aktuell bekannten Probleme beim optionalen `WM_POINTER`-basierten Touch/Stift-Stapel aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4d7bb-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="4d7bb-107">Keine Unterstützung für Freihand in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-107">No support for real-time inking.</span></span>

   <span data-ttu-id="4d7bb-108">Zwar funktionieren Freihand- und Stift-Plug-Ins nach wie vor, sie werden aber im Benutzeroberflächen-Thread verarbeitet, was zu schlechter Leistung führen kann.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="4d7bb-109">Verhaltensänderungen aufgrund der Verlagerung von Touch/Stift-Ereignissen zu Mausereignissen.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="4d7bb-110">Die Bearbeitung verhält sich möglicherweise anders.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="4d7bb-111">Drag/Drop zeigt keine angemessene Rückmeldung bei Toucheingaben.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="4d7bb-112">(Dies betrifft keine Stifteingaben.)</span><span class="sxs-lookup"><span data-stu-id="4d7bb-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="4d7bb-113">Drag/Drop kann für Touch/Stift-Ereignisse nicht mehr ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="4d7bb-114">Dadurch kann es möglicherweise zu einem Hängen der Anwendung kommen, bis die Mauseingabe erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-114">This can potentially hang the application until mouse input is detected.</span></span> <span data-ttu-id="4d7bb-115">Stattdessen sollten Entwickler Drag & Drop über Mausereignisse einleiten.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wmpointer-based-touchstylus-support"></a><span data-ttu-id="4d7bb-116">Entscheidung für die WM_POINTER-basierte Touch/Stift-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="4d7bb-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="4d7bb-117">Entwickler, die diesen Stapel aktivieren möchten, können der app.config-Datei ihrer Anwendung Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="4d7bb-117">Developers who wish to enable this stack can add the following to their application's app.config file:</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="4d7bb-118">Das Entfernen dieses Eintrags oder das Festlegen seines Werts auf `false` deaktiviert diesen optionalen Stapel.</span><span class="sxs-lookup"><span data-stu-id="4d7bb-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d7bb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d7bb-119">See also</span></span>

[<span data-ttu-id="4d7bb-120">Änderungen der Neuzuweisungen in .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="4d7bb-120">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
