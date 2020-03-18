---
ms.openlocfilehash: 3b7309347c643d89a28331c6ef3cac36085a969a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858531"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="87093-101">WPF-Fenster werden ohne Clipping gerendert, wenn diese die Größe eines einzelnen Monitors überschreiten</span><span class="sxs-lookup"><span data-stu-id="87093-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

|   |   |
|---|---|
|<span data-ttu-id="87093-102">Details</span><span class="sxs-lookup"><span data-stu-id="87093-102">Details</span></span>|<span data-ttu-id="87093-103">In .NET Framework 4.6, das auf Windows 8 und höher ausgeführt wird, wird das gesamte Fenster ohne Clipping gerendert, wenn es in einem Szenario mit mehreren Monitoren außerhalb einer einzelnen Anzeige liegt.</span><span class="sxs-lookup"><span data-stu-id="87093-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="87093-104">Dies unterscheidet sich von früheren Versionen von .NET Framework, bei denen WPF-Fenster beschnitten werden, die eine einzelne Anzeige überschreiten.</span><span class="sxs-lookup"><span data-stu-id="87093-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>|
|<span data-ttu-id="87093-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="87093-105">Suggestion</span></span>|<span data-ttu-id="87093-106">Dieses Verhalten (ob ein Clipping angewendet wird oder nicht) kann explizit festgelegt werden, indem Sie das <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code>-Element von <code>&lt;appSettings&gt;</code> in der Konfigurationsdatei einer Anwendung verwenden oder indem Sie die <code>EnableMultiMonitorDisplayClipping</code>-Eigenschaft beim Starten der App festlegen.</span><span class="sxs-lookup"><span data-stu-id="87093-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>|
|<span data-ttu-id="87093-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="87093-107">Scope</span></span>|<span data-ttu-id="87093-108">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="87093-108">Minor</span></span>|
|<span data-ttu-id="87093-109">Version</span><span class="sxs-lookup"><span data-stu-id="87093-109">Version</span></span>|<span data-ttu-id="87093-110">4.6</span><span class="sxs-lookup"><span data-stu-id="87093-110">4.6</span></span>|
|<span data-ttu-id="87093-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="87093-111">Type</span></span>|<span data-ttu-id="87093-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="87093-112">Runtime</span></span>|
