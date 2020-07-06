---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614601"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a><span data-ttu-id="8ad1b-101">Der Tastaturfokus bewegt sich jetzt ordnungsgemäß über mehrere Ebenen von WinForms-/WPF-Hosting</span><span class="sxs-lookup"><span data-stu-id="8ad1b-101">Keyboard focus now moves correctly across multiple layers of WinForms/WPF hosting</span></span>

#### <a name="details"></a><span data-ttu-id="8ad1b-102">Details</span><span class="sxs-lookup"><span data-stu-id="8ad1b-102">Details</span></span>

<span data-ttu-id="8ad1b-103">Nehmen Sie als Beispiel eine WPF-Anwendung, die ein WinForms-Steuerelement hostet, das wiederum WPF-Steuerelemente hostet.</span><span class="sxs-lookup"><span data-stu-id="8ad1b-103">Consider a WPF application hosting a WinForms control which in turn hosts WPF controls.</span></span> <span data-ttu-id="8ad1b-104">Benutzer können die WinForms-Ebene möglicherweise nicht mit der TABULATORTASTE verlassen, wenn das erste oder letzte Steuerelement in diese Ebene `System.Windows.Forms.Integration.ElementHost` von WPF ist.</span><span class="sxs-lookup"><span data-stu-id="8ad1b-104">Users may not be able to tab out of the WinForms layer if the first or last control in that layer is the WPF `System.Windows.Forms.Integration.ElementHost`.</span></span> <span data-ttu-id="8ad1b-105">Diese Änderung behebt dieses Problem, und Benutzer können die WinForms-Ebene jetzt mit der TABULATORTASTE verlassen. Automatisierte Anwendungen, die erfordern, dass der Fokus die WinForms-Ebene nie verlässt, funktionieren möglicherweise nicht mehr wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="8ad1b-105">This change fixes this issue, and users are now able to tab out of the WinForms layer.Automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8ad1b-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="8ad1b-106">Suggestion</span></span>

<span data-ttu-id="8ad1b-107">Ein Entwickler, der diese Änderung für eine niedrigere Frameworkversion als .NET 4.7.2 nutzen möchte, kann die folgende Gruppe von AppContext-Flags auf FALSE festlegen, damit die Änderung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="8ad1b-107">A developer who wants to utilize this change while targeting a framework version below .NET 4.7.2 can set the following set of AppContext flags to false for the change to be enabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="8ad1b-108">WPF-Anwendungen müssen alle frühen Barrierefreiheitsverbesserungen aktivieren, um die späteren Verbesserungen abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="8ad1b-108">WPF applications must opt in to all early accessibility improvements to get the later improvements.</span></span> <span data-ttu-id="8ad1b-109">Das heißt, die `Switch.UseLegacyAccessibilityFeatures`- und `Switch.UseLegacyAccessibilityFeatures.2`-Schalter müssen festgelegt werden. Ein-Entwickler, der die vorherige Funktionalität für .NET 4.7.2 oder höher benötigt, kann das folgende AppContext-Flag auf TRUE festlegen, damit die Änderung deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="8ad1b-109">In other words, both the `Switch.UseLegacyAccessibilityFeatures` and the `Switch.UseLegacyAccessibilityFeatures.2` switches must be setA developer who requires the previous functionality while targeting .NET 4.7.2 or greater can set the following AppContext flag to true for the change to be disabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="8ad1b-110">name</span><span class="sxs-lookup"><span data-stu-id="8ad1b-110">Name</span></span>    | <span data-ttu-id="8ad1b-111">Wert</span><span class="sxs-lookup"><span data-stu-id="8ad1b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8ad1b-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="8ad1b-112">Scope</span></span>   | <span data-ttu-id="8ad1b-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8ad1b-113">Edge</span></span>        |
| <span data-ttu-id="8ad1b-114">Version</span><span class="sxs-lookup"><span data-stu-id="8ad1b-114">Version</span></span> | <span data-ttu-id="8ad1b-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="8ad1b-115">4.7.2</span></span>       |
| <span data-ttu-id="8ad1b-116">Typ</span><span class="sxs-lookup"><span data-stu-id="8ad1b-116">Type</span></span>    | <span data-ttu-id="8ad1b-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="8ad1b-117">Retargeting</span></span> |
