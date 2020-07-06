---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614593"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a><span data-ttu-id="261fc-101">Der Standardhashalgorithmus für den Markupcompiler von WPF ist jetzt SHA256</span><span class="sxs-lookup"><span data-stu-id="261fc-101">The default hash algorithm for WPF's Markup Compiler is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="261fc-102">Details</span><span class="sxs-lookup"><span data-stu-id="261fc-102">Details</span></span>

<span data-ttu-id="261fc-103">Die WPF-MarkupCompiler stellt Kompilierungsdienste für XAML-Markupdateien bereit.</span><span class="sxs-lookup"><span data-stu-id="261fc-103">The WPF MarkupCompiler provides compilation services for XAML markup files.</span></span>  <span data-ttu-id="261fc-104">In .NET Framework 4.7.1 und früheren Versionen war SHA1 der Standardhashalgorithmus, der für Prüfsummen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="261fc-104">In the .NET Framework 4.7.1 and earlier versions, the default hash algorithm used for checksums was SHA1.</span></span> <span data-ttu-id="261fc-105">Diese Standardeinstellung wurde ab .NET Framework 4.7.2 aufgrund von Sicherheitsbedenken im Zusammenhang mit SHA1 in SHA256 geändert.</span><span class="sxs-lookup"><span data-stu-id="261fc-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.2.</span></span>  <span data-ttu-id="261fc-106">Diese Änderung wirkt sich auf die gesamte Prüfsummengenerierung für Markupdateien während der Kompilierung aus.</span><span class="sxs-lookup"><span data-stu-id="261fc-106">This change affects all checksum generation for markup files during compilation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="261fc-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="261fc-107">Suggestion</span></span>

<span data-ttu-id="261fc-108">Ein Entwickler, der als Zielplattform .NET Framework 4.7.2 oder höher verwendet und das SHA1-Hashverhalten wiederherstellen möchte, muss das folgende AppContext-Flag festlegen.</span><span class="sxs-lookup"><span data-stu-id="261fc-108">A developer who targets .NET Framework 4.7.2 or greater and wants to revert to SHA1 hashing behavior must set the following AppContext flag.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="261fc-109">Ein Entwickler, der SHA256-Hashwerte für eine niedrigere Frameworkversion als .NET 4.7.2 nutzen möchte, muss das unten genannte AppContext-Flag festlegen.</span><span class="sxs-lookup"><span data-stu-id="261fc-109">A developer who wants to utilize SHA256 hashing while targeting a framework version below .NET 4.7.2 must set the below AppContext flag.</span></span>  <span data-ttu-id="261fc-110">Beachten Sie, dass die installierte Version von .NET Framework 4.7.2 oder höher sein muss.</span><span class="sxs-lookup"><span data-stu-id="261fc-110">Note that the installed version of the .NET Framework must be 4.7.2 or greater.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="261fc-111">name</span><span class="sxs-lookup"><span data-stu-id="261fc-111">Name</span></span>    | <span data-ttu-id="261fc-112">Wert</span><span class="sxs-lookup"><span data-stu-id="261fc-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="261fc-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="261fc-113">Scope</span></span>   | <span data-ttu-id="261fc-114">Transparent</span><span class="sxs-lookup"><span data-stu-id="261fc-114">Transparent</span></span> |
| <span data-ttu-id="261fc-115">Version</span><span class="sxs-lookup"><span data-stu-id="261fc-115">Version</span></span> | <span data-ttu-id="261fc-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="261fc-116">4.7.2</span></span>       |
| <span data-ttu-id="261fc-117">Typ</span><span class="sxs-lookup"><span data-stu-id="261fc-117">Type</span></span>    | <span data-ttu-id="261fc-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="261fc-118">Retargeting</span></span> |
