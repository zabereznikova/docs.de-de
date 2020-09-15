---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615721"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a><span data-ttu-id="1afae-101">Die WPF-Layoutglättung von Rändern wurde geändert</span><span class="sxs-lookup"><span data-stu-id="1afae-101">WPF layout rounding of margins has changed</span></span>

#### <a name="details"></a><span data-ttu-id="1afae-102">Details</span><span class="sxs-lookup"><span data-stu-id="1afae-102">Details</span></span>

<span data-ttu-id="1afae-103">Die Art und Weise, wie Ränder und die Grenzen und der Hintergrund darin geglättet werden, hat sich geändert.</span><span class="sxs-lookup"><span data-stu-id="1afae-103">The way in which margins are rounded and borders and the background inside of them has changed.</span></span> <span data-ttu-id="1afae-104">Auswirkungen durch diese Änderung:</span><span class="sxs-lookup"><span data-stu-id="1afae-104">As a result of this change:</span></span>

- <span data-ttu-id="1afae-105">Die Breite oder Höhe der Elemente vergrößert oder verkleinert sich allenfalls um einen Pixel.</span><span class="sxs-lookup"><span data-stu-id="1afae-105">The width or height of elements may grow or shrink by at most one pixel.</span></span>
- <span data-ttu-id="1afae-106">Die Platzierung eines Objekts kann sich allenfalls um einen Pixel verschieben.</span><span class="sxs-lookup"><span data-stu-id="1afae-106">The placement of an object can move by at most one pixel.</span></span>
- <span data-ttu-id="1afae-107">Zentrierte Elemente können sich vertikal oder horizontal um allenfalls ein Pixel von der Mitte verschieben.</span><span class="sxs-lookup"><span data-stu-id="1afae-107">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>
<span data-ttu-id="1afae-108">Standardmäßig wird dieses neue Layout nur für Apps aktiviert, die auf .NET Framework 4.6 abzielen.</span><span class="sxs-lookup"><span data-stu-id="1afae-108">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1afae-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1afae-109">Suggestion</span></span>

<span data-ttu-id="1afae-110">Da durch diese Änderung das Clipping die rechte oder Unterseite von WPF-Steuerelementen bei hohen DPIs beseitigt wird, können Apps, die auf frühere Versionen von .NET Framework abzielen, aber auf .NET Framework 4.6 ausgeführt werden, dieses neue Verhalten übernehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="1afae-110">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

<span data-ttu-id="1afae-111">Apps, die auf .NET Framework 4.6 ausgelegt sind, aber WPF-Steuerelemente zum Rendern mithilfe des vorherigen Layoutalgorithmus verwenden möchten, können dies vornehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="1afae-111">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| <span data-ttu-id="1afae-112">name</span><span class="sxs-lookup"><span data-stu-id="1afae-112">Name</span></span>    | <span data-ttu-id="1afae-113">Wert</span><span class="sxs-lookup"><span data-stu-id="1afae-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1afae-114">Bereich</span><span class="sxs-lookup"><span data-stu-id="1afae-114">Scope</span></span>   | <span data-ttu-id="1afae-115">Gering</span><span class="sxs-lookup"><span data-stu-id="1afae-115">Minor</span></span>       |
| <span data-ttu-id="1afae-116">Version</span><span class="sxs-lookup"><span data-stu-id="1afae-116">Version</span></span> | <span data-ttu-id="1afae-117">4.6</span><span class="sxs-lookup"><span data-stu-id="1afae-117">4.6</span></span>         |
| <span data-ttu-id="1afae-118">Typ</span><span class="sxs-lookup"><span data-stu-id="1afae-118">Type</span></span>    | <span data-ttu-id="1afae-119">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="1afae-119">Retargeting</span></span> |
