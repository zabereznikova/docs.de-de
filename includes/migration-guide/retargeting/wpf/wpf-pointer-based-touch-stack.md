---
ms.openlocfilehash: eb89cbc72d8b09fd1aa5bc775a6c539eb208fa70
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614576"
---
### <a name="wpf-pointer-based-touch-stack"></a><span data-ttu-id="80723-101">Zeigerbasierte Touch-Stapel in WPF</span><span class="sxs-lookup"><span data-stu-id="80723-101">WPF Pointer-Based Touch Stack</span></span>

#### <a name="details"></a><span data-ttu-id="80723-102">Details</span><span class="sxs-lookup"><span data-stu-id="80723-102">Details</span></span>

<span data-ttu-id="80723-103">Diese Änderung ermöglicht das Aktivieren eines optionalen WM_POINTER-basierten WPF-Touch-/Stift-Stapels.</span><span class="sxs-lookup"><span data-stu-id="80723-103">This change adds the ability to enable an optional WM_POINTER based WPF touch/stylus stack.</span></span>  <span data-ttu-id="80723-104">Entwickler, die diesen Stapel nicht explizit aktivieren, sollten keine Änderung im WPF-Touch/Stift-Verhalten feststellen. Folgende Probleme sind mit dem optionalen WM_POINTER-basierten Touch-/Stift-Stapel bekannt:</span><span class="sxs-lookup"><span data-stu-id="80723-104">Developers that do not explicitly enable this should see no change in WPF touch/stylus behavior.Current Known Issues With optional WM_POINTER based touch/stylus stack:</span></span>

- <span data-ttu-id="80723-105">Keine Unterstützung für Freihand in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="80723-105">No support for real-time inking.</span></span>
- <span data-ttu-id="80723-106">Zwar funktionieren Freihand- und Stift-Plug-Ins nach wie vor, jedoch werden sie im Benutzeroberflächenthread verarbeitet, was zu schlechter Leistung führen kann.</span><span class="sxs-lookup"><span data-stu-id="80723-106">While inking and StylusPlugins will still work, they will be processed on the UI Thread which can lead to poor performance.</span></span>
- <span data-ttu-id="80723-107">Verhaltensänderungen aufgrund der Verlagerung von Touch/Stift-Ereignissen zu Mausereignissen.</span><span class="sxs-lookup"><span data-stu-id="80723-107">Behavioral changes due to changes in promotion from touch/stylus events to mouse events</span></span>
- <span data-ttu-id="80723-108">Die Bearbeitung verhält sich möglicherweise anders.</span><span class="sxs-lookup"><span data-stu-id="80723-108">Manipulation may behave differently</span></span>
- <span data-ttu-id="80723-109">Drag/Drop zeigt keine angemessene Rückmeldung bei Toucheingaben.</span><span class="sxs-lookup"><span data-stu-id="80723-109">Drag/Drop will not show appropriate feedback for touch input</span></span>
- <span data-ttu-id="80723-110">Dies betrifft keine Stifteingaben.</span><span class="sxs-lookup"><span data-stu-id="80723-110">This does not affect stylus input</span></span>
- <span data-ttu-id="80723-111">Drag/Drop kann für Touch/Stift-Ereignisse nicht mehr ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="80723-111">Drag/Drop can no longer be initiated on touch/stylus events</span></span>
- <span data-ttu-id="80723-112">Dadurch kann es möglicherweise zu einem Hängen der Anwendung kommen, bis die Mauseingabe erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="80723-112">This can potentially hang the application until mouse input is detected.</span></span>
- <span data-ttu-id="80723-113">Stattdessen sollten Entwickler Drag & Drop über Mausereignisse einleiten.</span><span class="sxs-lookup"><span data-stu-id="80723-113">Instead, developers should initiate drag and drop from mouse events.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80723-114">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="80723-114">Suggestion</span></span>

<span data-ttu-id="80723-115">Entwickler, die diesen Stapel aktivieren möchten, können der Datei „app.config“ ihrer Anwendung Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="80723-115">Developers who wish to enable this stack can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="80723-116">Entfernen oder Festlegen des Werts auf FALSE deaktiviert diesen optionalen Stapel. Beachten Sie, dass dieser Stapel nur unter Windows 10 Creators Update und höher verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="80723-116">Removing this or setting the value to false will turn this optional stack off.Note that this stack is available only on Windows 10 Creators Update and above.</span></span>

| <span data-ttu-id="80723-117">name</span><span class="sxs-lookup"><span data-stu-id="80723-117">Name</span></span>    | <span data-ttu-id="80723-118">Wert</span><span class="sxs-lookup"><span data-stu-id="80723-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80723-119">Bereich</span><span class="sxs-lookup"><span data-stu-id="80723-119">Scope</span></span>   | <span data-ttu-id="80723-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="80723-120">Edge</span></span>        |
| <span data-ttu-id="80723-121">Version</span><span class="sxs-lookup"><span data-stu-id="80723-121">Version</span></span> | <span data-ttu-id="80723-122">4.7</span><span class="sxs-lookup"><span data-stu-id="80723-122">4.7</span></span>         |
| <span data-ttu-id="80723-123">Typ</span><span class="sxs-lookup"><span data-stu-id="80723-123">Type</span></span>    | <span data-ttu-id="80723-124">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="80723-124">Retargeting</span></span> |
