---
ms.openlocfilehash: 6a6c0af9cc0f3e5d1bbc3a4462a9ff7eaa748a5f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497068"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="6752b-101">Änderungen bei ComboBox in svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="6752b-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="6752b-102">Details</span><span class="sxs-lookup"><span data-stu-id="6752b-102">Details</span></span>

<span data-ttu-id="6752b-103">Bei bestimmten Designs mit hohem Kontrast wurden ComboBox-Steuerelemente im Tool [Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) nicht in der richtigen Farbe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6752b-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="6752b-104">Dieses Problem wurde in .NET Framework 4.7.2 behoben.</span><span class="sxs-lookup"><span data-stu-id="6752b-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="6752b-105">Aufgrund der für .NET Framework SDK geltenden Abwärtskompatibilitätsanforderungen war die Korrektur für Kunden nicht standardmäßig sichtbar.</span><span class="sxs-lookup"><span data-stu-id="6752b-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="6752b-106">In .NET 4.8 zeigt sich diese Änderung nun, da der Datei „svcTraceViewer.exe.config“ die folgenden [AppContext-Konfigurationsswitches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) hinzugefügt wurden:</span><span class="sxs-lookup"><span data-stu-id="6752b-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a><span data-ttu-id="6752b-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6752b-107">Suggestion</span></span>

<ul><li><span data-ttu-id="6752b-108">Deaktivieren der Änderung Wenn Sie die Änderung im Verhalten bei hohem Kontrast nicht möchten, können Sie diese deaktivieren, indem Sie den folgenden Abschnitt in der Konfigurationsdatei „svcTraceViewer.exe.config“ entfernen:</span><span class="sxs-lookup"><span data-stu-id="6752b-108">How to opt out of the change If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span></li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="6752b-109">name</span><span class="sxs-lookup"><span data-stu-id="6752b-109">Name</span></span>    | <span data-ttu-id="6752b-110">Wert</span><span class="sxs-lookup"><span data-stu-id="6752b-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6752b-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="6752b-111">Scope</span></span>   |<span data-ttu-id="6752b-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6752b-112">Edge</span></span>|
|<span data-ttu-id="6752b-113">Version</span><span class="sxs-lookup"><span data-stu-id="6752b-113">Version</span></span>|<span data-ttu-id="6752b-114">4.8</span><span class="sxs-lookup"><span data-stu-id="6752b-114">4.8</span></span>|
|<span data-ttu-id="6752b-115">Typ</span><span class="sxs-lookup"><span data-stu-id="6752b-115">Type</span></span>|<span data-ttu-id="6752b-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6752b-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6752b-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6752b-117">Affected APIs</span></span>

<span data-ttu-id="6752b-118">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="6752b-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
