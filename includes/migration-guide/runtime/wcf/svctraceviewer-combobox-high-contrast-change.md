---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770806"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="a1884-101">Änderungen bei ComboBox in svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="a1884-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="a1884-102">Details</span><span class="sxs-lookup"><span data-stu-id="a1884-102">Details</span></span>

<span data-ttu-id="a1884-103">Bei bestimmten Designs mit hohem Kontrast wurden ComboBox-Steuerelemente im Tool [Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) nicht in der richtigen Farbe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1884-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="a1884-104">Dieses Problem wurde in .NET Framework 4.7.2 behoben.</span><span class="sxs-lookup"><span data-stu-id="a1884-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="a1884-105">Aufgrund der für .NET Framework SDK geltenden Abwärtskompatibilitätsanforderungen war die Korrektur für Kunden nicht standardmäßig sichtbar.</span><span class="sxs-lookup"><span data-stu-id="a1884-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="a1884-106">In .NET 4.8 zeigt sich diese Änderung nun, da der Datei „svcTraceViewer.exe.config“ die folgenden [AppContext-Konfigurationsswitches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) hinzugefügt wurden:</span><span class="sxs-lookup"><span data-stu-id="a1884-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a><span data-ttu-id="a1884-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a1884-107">Suggestion</span></span>

<span data-ttu-id="a1884-108">Wenn Sie die Änderung im Verhalten bei hohem Kontrast nicht wünschen, können Sie diese deaktivieren, indem Sie den folgenden Abschnitt in der Konfigurationsdatei „svcTraceViewer.exe.config“ entfernen:</span><span class="sxs-lookup"><span data-stu-id="a1884-108">If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| <span data-ttu-id="a1884-109">name</span><span class="sxs-lookup"><span data-stu-id="a1884-109">Name</span></span>    | <span data-ttu-id="a1884-110">Wert</span><span class="sxs-lookup"><span data-stu-id="a1884-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="a1884-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="a1884-111">Scope</span></span>   | <span data-ttu-id="a1884-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a1884-112">Edge</span></span>    |
| <span data-ttu-id="a1884-113">Version</span><span class="sxs-lookup"><span data-stu-id="a1884-113">Version</span></span> | <span data-ttu-id="a1884-114">4.8</span><span class="sxs-lookup"><span data-stu-id="a1884-114">4.8</span></span>     |
| <span data-ttu-id="a1884-115">Typ</span><span class="sxs-lookup"><span data-stu-id="a1884-115">Type</span></span>    | <span data-ttu-id="a1884-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a1884-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a1884-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a1884-117">Affected APIs</span></span>

<span data-ttu-id="a1884-118">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="a1884-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
