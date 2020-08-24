---
ms.openlocfilehash: e128bdb5735b3e4844356ad4807cc092f6f2b105
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062423"
---
### <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="f3722-101">Keine A/W-Überprüfung des Suffixes auf anderen Plattformen als Windows</span><span class="sxs-lookup"><span data-stu-id="f3722-101">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="f3722-102">Die .NET-Runtimes fügen kein `A`- oder `W`-Suffix zu Funktionsexportnamen während der Stichprobenentnahme für P/Invokes auf anderen Plattformen als Windows hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3722-102">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f3722-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f3722-103">Version introduced</span></span>

<span data-ttu-id="f3722-104">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="f3722-104">5.0 Preview 4</span></span>

#### <a name="change-description"></a><span data-ttu-id="f3722-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f3722-105">Change description</span></span>

<span data-ttu-id="f3722-106">[Windows umfasst eine Konvention](/windows/win32/intl/conventions-for-function-prototypes), laut der ein `A`- oder `W`-Suffix zu Funktionsnamen des Windows SDKs hinzugefügt werden, die jeweils der Windows-Codeseite und den Unicode-Versionen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f3722-106">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="f3722-107">In vorherigen Versionen von .NET haben die CoreCLR- und Mono-Runtimes während der Exportermittlung *auf allen Plattformen* ein `A`- oder `W`-Suffix zum Exportnamen für P/Invokes hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f3722-107">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="f3722-108">In .NET 5.0 und höheren Versionen wird ein `A`- oder `W`-Suffix *nur unter Windows* während der Exportermittlung zum Exportnamen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f3722-108">In .NET 5.0 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="f3722-109">Auf UNIX-Plattformen wird das Suffix nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f3722-109">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="f3722-110">Die Semantik beider Runtimes bleiben auf der Windows-Plattform unverändert.</span><span class="sxs-lookup"><span data-stu-id="f3722-110">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f3722-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="f3722-111">Reason for change</span></span>

<span data-ttu-id="f3722-112">Diese Änderung wurde zur Vereinfachung der plattformübergreifenden Überprüfung implementiert.</span><span class="sxs-lookup"><span data-stu-id="f3722-112">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="f3722-113">Dabei handelt es sich um einen Mehraufwand, der nicht hätte auftreten sollen, da andere Plattformen als Windows diese Semantik nicht aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f3722-113">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f3722-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="f3722-114">Recommended action</span></span>

<span data-ttu-id="f3722-115">Sie können das gewünschte Suffix auf anderen Plattformen als Windows manuell hinzufügen, um diese Änderung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="f3722-115">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="f3722-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f3722-116">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

#### <a name="category"></a><span data-ttu-id="f3722-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="f3722-117">Category</span></span>

<span data-ttu-id="f3722-118">Interop</span><span class="sxs-lookup"><span data-stu-id="f3722-118">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f3722-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f3722-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

-->
