---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621354"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="7aad4-101">WPF-Fenster werden ohne Clipping gerendert, wenn diese die Größe eines einzelnen Monitors überschreiten</span><span class="sxs-lookup"><span data-stu-id="7aad4-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="7aad4-102">Details</span><span class="sxs-lookup"><span data-stu-id="7aad4-102">Details</span></span>

<span data-ttu-id="7aad4-103">In .NET Framework 4.6, das auf Windows 8 und höher ausgeführt wird, wird das gesamte Fenster ohne Clipping gerendert, wenn es in einem Szenario mit mehreren Monitoren außerhalb einer einzelnen Anzeige liegt.</span><span class="sxs-lookup"><span data-stu-id="7aad4-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="7aad4-104">Dies unterscheidet sich von früheren Versionen von .NET Framework, bei denen WPF-Fenster beschnitten werden, die eine einzelne Anzeige überschreiten.</span><span class="sxs-lookup"><span data-stu-id="7aad4-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7aad4-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7aad4-105">Suggestion</span></span>

<span data-ttu-id="7aad4-106">Dieses Verhalten (ob ein Clipping angewendet wird oder nicht) kann explizit festgelegt werden, indem Sie das <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code>-Element von <code>&lt;appSettings&gt;</code> in der Konfigurationsdatei einer Anwendung verwenden oder indem Sie die <code>EnableMultiMonitorDisplayClipping</code>-Eigenschaft beim Starten der App festlegen.</span><span class="sxs-lookup"><span data-stu-id="7aad4-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="7aad4-107">name</span><span class="sxs-lookup"><span data-stu-id="7aad4-107">Name</span></span>    | <span data-ttu-id="7aad4-108">Wert</span><span class="sxs-lookup"><span data-stu-id="7aad4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7aad4-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="7aad4-109">Scope</span></span>   |<span data-ttu-id="7aad4-110">Gering</span><span class="sxs-lookup"><span data-stu-id="7aad4-110">Minor</span></span>|
|<span data-ttu-id="7aad4-111">Version</span><span class="sxs-lookup"><span data-stu-id="7aad4-111">Version</span></span>|<span data-ttu-id="7aad4-112">4.6</span><span class="sxs-lookup"><span data-stu-id="7aad4-112">4.6</span></span>|
|<span data-ttu-id="7aad4-113">Typ</span><span class="sxs-lookup"><span data-stu-id="7aad4-113">Type</span></span>|<span data-ttu-id="7aad4-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7aad4-114">Runtime</span></span>|
