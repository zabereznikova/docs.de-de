---
ms.openlocfilehash: dcc64fe651b219ff1416c0afcdb4c6d275160f4b
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "97911582"
---
### <a name="change-in-default-value-of-useshellexecute"></a><span data-ttu-id="132ce-101">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="132ce-101">Change in default value of UseShellExecute</span></span>

<span data-ttu-id="132ce-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> besitzt den Standardwert `false` für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="132ce-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> has a default value of `false` on .NET Core.</span></span> <span data-ttu-id="132ce-103">Für .NET Framework lautet der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="132ce-103">On .NET Framework, its default value is `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="132ce-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="132ce-104">Change description</span></span>

<span data-ttu-id="132ce-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> ermöglicht es Ihnen, eine Anwendung direkt zu starten, z. B. mit Code wie `Process.Start("mspaint.exe")`, der Paint startet.</span><span class="sxs-lookup"><span data-stu-id="132ce-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> lets you launch an application directly, for example, with code such as `Process.Start("mspaint.exe")` that launches Paint.</span></span> <span data-ttu-id="132ce-106">Außerdem können Sie eine zugehörige Anwendung indirekt starten, wenn <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="132ce-106">It also lets you indirectly launch an associated application if <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is set to `true`.</span></span> <span data-ttu-id="132ce-107">Für .NET Framework lautet der Standardwert für <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `true`. Dies bedeutet, dass Code wie `Process.Start("mytextfile.txt")` den Editor starten würde, wenn Sie *TXT*-Dateien diesem Editor zugeordnet haben.</span><span class="sxs-lookup"><span data-stu-id="132ce-107">On .NET Framework, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`, meaning that code such as `Process.Start("mytextfile.txt")` would launch Notepad, if you've associated *.txt* files with that editor.</span></span> <span data-ttu-id="132ce-108">Um zu verhindern, dass eine App indirekt unter .NET Framework gestartet wird, müssen Sie <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> explizit auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="132ce-108">To prevent indirectly launching an app on .NET Framework, you must explicitly set <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="132ce-109">Für .NET Core ist der Standardwert für <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `false`.</span><span class="sxs-lookup"><span data-stu-id="132ce-109">On .NET Core, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `false`.</span></span> <span data-ttu-id="132ce-110">Dies bedeutet, dass zugehörige Anwendungen standardmäßig nicht gestartet werden, wenn Sie `Process.Start` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="132ce-110">This means that, by default, associated applications are not launched when you call `Process.Start`.</span></span>

<span data-ttu-id="132ce-111">Die folgenden Eigenschaften in <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType> funktionieren nur, wenn <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> auf `true` festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="132ce-111">The following properties on <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType> are only functional when <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`:</span></span>

- <xref:System.Diagnostics.ProcessStartInfo.CreateNoWindow?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo.ErrorDialog?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo.Verb?displayProperty=nameWithType>
- <span data-ttu-id="132ce-112"><xref:System.Diagnostics.ProcessStartInfo.WindowStyle?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="132ce-112"><xref:System.Diagnostics.ProcessStartInfo.WindowStyle?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="132ce-113">Diese Änderung wurde aus Leistungsgründen in .NET Core eingeführt.</span><span class="sxs-lookup"><span data-stu-id="132ce-113">This change was introduced in .NET Core for performance reasons.</span></span> <span data-ttu-id="132ce-114">In der Regel wird <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> verwendet, um eine Anwendung direkt zu starten.</span><span class="sxs-lookup"><span data-stu-id="132ce-114">Typically, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> is used to launch an application directly.</span></span> <span data-ttu-id="132ce-115">Wenn Sie eine App direkt starten, muss die Windows-Shell nicht einbezogen werden, und die damit verbundenen Leistungskosten entfallen.</span><span class="sxs-lookup"><span data-stu-id="132ce-115">Launching an app directly does not need to involve the Windows shell and incur the associated performance cost.</span></span> <span data-ttu-id="132ce-116">Damit dieser Standardfall schneller wird, ändert .NET Core den Standardwert aus <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> in `false`.</span><span class="sxs-lookup"><span data-stu-id="132ce-116">To make this default case faster, .NET Core changes the default value of <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="132ce-117">Wenn Sie ihn benötigen, können Sie wahlweise den langsameren Pfad verwenden.</span><span class="sxs-lookup"><span data-stu-id="132ce-117">You can opt in to the slower path if you need it.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="132ce-118">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="132ce-118">Version introduced</span></span>

<span data-ttu-id="132ce-119">2.1</span><span class="sxs-lookup"><span data-stu-id="132ce-119">2.1</span></span>

> [!NOTE]
> <span data-ttu-id="132ce-120">In früheren Versionen von .NET Core wurde `UseShellExecute` nicht für Windows implementiert.</span><span class="sxs-lookup"><span data-stu-id="132ce-120">In earlier versions of .NET Core, `UseShellExecute` was not implemented for Windows.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="132ce-121">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="132ce-121">Recommended action</span></span>

<span data-ttu-id="132ce-122">Wenn Ihre App das alte Verhalten benötigt, rufen Sie <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> auf und legen dabei <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> auf `true` für das <xref:System.Diagnostics.ProcessStartInfo>-Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="132ce-122">If your app relies on the old behavior, call <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> with <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> set to `true` on the <xref:System.Diagnostics.ProcessStartInfo> object.</span></span>

#### <a name="category"></a><span data-ttu-id="132ce-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="132ce-123">Category</span></span>

<span data-ttu-id="132ce-124">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="132ce-124">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="132ce-125">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="132ce-125">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
