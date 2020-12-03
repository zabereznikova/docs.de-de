---
title: 'Breaking Change: Keine A/W-Überprüfung des Suffixes auf anderen Plattformen als Windows'
description: Hier erfahren Sie mehr über den Breaking Change für den Interopbereich in .NET 5.0, durch den bei der Suche nach „P/Invokes“ auf Nicht-Windows-Plattformen keine Suffixe mehr zu den Namen von Funktionsexporten hinzugefügt werden.
ms.date: 08/13/2020
ms.openlocfilehash: a4c612a81796faf80fa257df21232a54f7b95431
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759481"
---
# <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="f6b52-103">Keine A/W-Überprüfung des Suffixes auf anderen Plattformen als Windows</span><span class="sxs-lookup"><span data-stu-id="f6b52-103">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="f6b52-104">Die .NET-Runtimes fügen kein `A`- oder `W`-Suffix zu Funktionsexportnamen während der Stichprobenentnahme für P/Invokes auf anderen Plattformen als Windows hinzu.</span><span class="sxs-lookup"><span data-stu-id="f6b52-104">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f6b52-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f6b52-105">Version introduced</span></span>

<span data-ttu-id="f6b52-106">5.0</span><span class="sxs-lookup"><span data-stu-id="f6b52-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="f6b52-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f6b52-107">Change description</span></span>

<span data-ttu-id="f6b52-108">[Windows umfasst eine Konvention](/windows/win32/intl/conventions-for-function-prototypes), laut der ein `A`- oder `W`-Suffix zu Funktionsnamen des Windows SDKs hinzugefügt werden, die jeweils der Windows-Codeseite und den Unicode-Versionen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f6b52-108">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="f6b52-109">In vorherigen Versionen von .NET haben die CoreCLR- und Mono-Runtimes während der Exportermittlung *auf allen Plattformen* ein `A`- oder `W`-Suffix zum Exportnamen für P/Invokes hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f6b52-109">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="f6b52-110">In .NET 5.0 und höheren Versionen wird ein `A`- oder `W`-Suffix *nur unter Windows* während der Exportermittlung zum Exportnamen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f6b52-110">In .NET 5.0 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="f6b52-111">Auf UNIX-Plattformen wird das Suffix nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f6b52-111">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="f6b52-112">Die Semantik beider Runtimes bleiben auf der Windows-Plattform unverändert.</span><span class="sxs-lookup"><span data-stu-id="f6b52-112">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f6b52-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="f6b52-113">Reason for change</span></span>

<span data-ttu-id="f6b52-114">Diese Änderung wurde zur Vereinfachung der plattformübergreifenden Überprüfung implementiert.</span><span class="sxs-lookup"><span data-stu-id="f6b52-114">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="f6b52-115">Dabei handelt es sich um einen Mehraufwand, der nicht hätte auftreten sollen, da andere Plattformen als Windows diese Semantik nicht aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f6b52-115">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f6b52-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="f6b52-116">Recommended action</span></span>

<span data-ttu-id="f6b52-117">Sie können das gewünschte Suffix auf anderen Plattformen als Windows manuell hinzufügen, um diese Änderung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="f6b52-117">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="f6b52-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f6b52-118">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

## <a name="affected-apis"></a><span data-ttu-id="f6b52-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f6b52-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

### Category

Interop

-->
