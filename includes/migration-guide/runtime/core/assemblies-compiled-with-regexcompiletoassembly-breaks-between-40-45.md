---
ms.openlocfilehash: 0bd90b3d479a7e0897aaf78b7718ae156a4a239f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620190"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="3cb6e-101">Mit der Regex.CompileToAssembly-Methode kompilierte Assemblys zwischen 4.0 und 4.5 werden unterbrochen</span><span class="sxs-lookup"><span data-stu-id="3cb6e-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="3cb6e-102">Details</span><span class="sxs-lookup"><span data-stu-id="3cb6e-102">Details</span></span>

<span data-ttu-id="3cb6e-103">Wenn eine Assembly aus kompilierten regulären Ausdrücken mit .NET Framework 4.5 erstellt wird und auf .NET Framework 4 ausgerichtet ist, wird bei dem Versuch, die regulären Ausdrücke in dieser Assembly auf einem System zu verwenden, auf dem .NET Framework 4 installiert ist, eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3cb6e-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3cb6e-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3cb6e-104">Suggestion</span></span>

<span data-ttu-id="3cb6e-105">Um dieses Problem zu umgehen, haben Sie die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="3cb6e-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="3cb6e-106">Erstellen Sie die Assembly, die die regulären Ausdrücke enthält, mit .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3cb6e-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="3cb6e-107">Verwenden Sie einen interpretierten regulären Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="3cb6e-107">Use an interpreted regular expression.</span></span></li></ul>

| <span data-ttu-id="3cb6e-108">name</span><span class="sxs-lookup"><span data-stu-id="3cb6e-108">Name</span></span>    | <span data-ttu-id="3cb6e-109">Wert</span><span class="sxs-lookup"><span data-stu-id="3cb6e-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3cb6e-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="3cb6e-110">Scope</span></span>   |<span data-ttu-id="3cb6e-111">Gering</span><span class="sxs-lookup"><span data-stu-id="3cb6e-111">Minor</span></span>|
|<span data-ttu-id="3cb6e-112">Version</span><span class="sxs-lookup"><span data-stu-id="3cb6e-112">Version</span></span>|<span data-ttu-id="3cb6e-113">4.5</span><span class="sxs-lookup"><span data-stu-id="3cb6e-113">4.5</span></span>|
|<span data-ttu-id="3cb6e-114">Typ</span><span class="sxs-lookup"><span data-stu-id="3cb6e-114">Type</span></span>|<span data-ttu-id="3cb6e-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3cb6e-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3cb6e-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3cb6e-116">Affected APIs</span></span>

-<xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
