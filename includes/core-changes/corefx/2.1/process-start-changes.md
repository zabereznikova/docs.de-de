---
ms.openlocfilehash: 7c0930f6606aa96d2863dc740aef8e9cab724b37
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344874"
---
### <a name="change-in-default-value-of-useshellexecute"></a><span data-ttu-id="4400e-101">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="4400e-101">Change in default value of UseShellExecute</span></span>

<span data-ttu-id="4400e-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> besitzt den Standardwert `false` für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4400e-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> has a default value of `false` on .NET Core.</span></span> <span data-ttu-id="4400e-103">Für .NET Framework lautet der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="4400e-103">On .NET Framework, its default value is `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4400e-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4400e-104">Change description</span></span>

<span data-ttu-id="4400e-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> ermöglicht es Ihnen, eine Anwendung direkt zu starten, z. B. mit Code wie `Process.Start("mspaint.exe")`, der Paint startet.</span><span class="sxs-lookup"><span data-stu-id="4400e-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> lets you launch an application directly, for example, with code such as `Process.Start("mspaint.exe")` that launches Paint.</span></span> <span data-ttu-id="4400e-106">Außerdem können Sie eine zugehörige Anwendung indirekt starten, wenn <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4400e-106">It also lets you indirectly launch an associated application if <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is set to `true`.</span></span> <span data-ttu-id="4400e-107">Für .NET Framework lautet der Standardwert für <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `true`. Dies bedeutet, dass Code wie `Process.Start("mytextfile.txt")` den Editor starten würde, wenn Sie *TXT*-Dateien diesem Editor zugeordnet haben.</span><span class="sxs-lookup"><span data-stu-id="4400e-107">On .NET Framework, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`, meaning that code such as `Process.Start("mytextfile.txt")` would launch Notepad, if you've associated *.txt* files with that editor.</span></span> <span data-ttu-id="4400e-108">Um zu verhindern, dass eine App indirekt unter .NET Framework gestartet wird, müssen Sie <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> explizit auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="4400e-108">To prevent indirectly launching an app on .NET Framework, you must explicitly set <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="4400e-109">Für .NET Core ist der Standardwert für <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `false`.</span><span class="sxs-lookup"><span data-stu-id="4400e-109">On .NET Core, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `false`.</span></span> <span data-ttu-id="4400e-110">Dies bedeutet, dass zugehörige Anwendungen standardmäßig nicht gestartet werden, wenn Sie `Process.Start` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4400e-110">This means that, by default, associated applications are not launched when you call `Process.Start`.</span></span>

<span data-ttu-id="4400e-111">Diese Änderung wurde aus Leistungsgründen in .NET Core eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4400e-111">This change was introduced in .NET Core for performance reasons.</span></span> <span data-ttu-id="4400e-112">In der Regel wird <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> verwendet, um eine Anwendung direkt zu starten.</span><span class="sxs-lookup"><span data-stu-id="4400e-112">Typically, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> is used to launch an application directly.</span></span> <span data-ttu-id="4400e-113">Wenn Sie eine App direkt starten, muss die Windows-Shell nicht einbezogen werden, und die damit verbundenen Leistungskosten entfallen.</span><span class="sxs-lookup"><span data-stu-id="4400e-113">Launching an app directly does not need to involve the Windows shell and incur the associated performance cost.</span></span> <span data-ttu-id="4400e-114">Damit dieser Standardfall schneller wird, ändert .NET Core den Standardwert aus <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> in `false`.</span><span class="sxs-lookup"><span data-stu-id="4400e-114">To make this default case faster, .NET Core changes the default value of <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="4400e-115">Wenn Sie ihn benötigen, können Sie wahlweise den langsameren Pfad verwenden.</span><span class="sxs-lookup"><span data-stu-id="4400e-115">You can opt in to the slower path if you need it.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4400e-116">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="4400e-116">Version introduced</span></span>

<span data-ttu-id="4400e-117">2.1</span><span class="sxs-lookup"><span data-stu-id="4400e-117">2.1</span></span>

> [!NOTE]
> <span data-ttu-id="4400e-118">In früheren Versionen von .NET Core wurde `UseShellExecute` nicht für Windows implementiert.</span><span class="sxs-lookup"><span data-stu-id="4400e-118">In earlier versions of .NET Core, `UseShellExecute` was not implemented for Windows.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4400e-119">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="4400e-119">Recommended action</span></span>

<span data-ttu-id="4400e-120">Wenn Ihre App das alte Verhalten benötigt, rufen Sie <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> auf und legen dabei <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> auf `true` für das <xref:System.Diagnostics.ProcessStartInfo>-Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="4400e-120">If your app relies on the old behavior, call <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> with <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> set to `true` on the <xref:System.Diagnostics.ProcessStartInfo> object.</span></span>

#### <a name="category"></a><span data-ttu-id="4400e-121">Kategorie</span><span class="sxs-lookup"><span data-stu-id="4400e-121">Category</span></span>

<span data-ttu-id="4400e-122">CoreFx</span><span class="sxs-lookup"><span data-stu-id="4400e-122">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4400e-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4400e-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
