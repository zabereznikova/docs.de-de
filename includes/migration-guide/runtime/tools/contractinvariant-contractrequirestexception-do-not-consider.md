---
ms.openlocfilehash: 29c66edfeb1690199aac39b9c3076d161b2075d4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621342"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a><span data-ttu-id="bc613-101">Contract.Invariant oder Contract.Requires\<TException> erkennen String.IsNullOrEmpty nicht als reinen Wert an</span><span class="sxs-lookup"><span data-stu-id="bc613-101">Contract.Invariant or Contract.Requires\<TException> do not consider String.IsNullOrEmpty to be pure</span></span>

#### <a name="details"></a><span data-ttu-id="bc613-102">Details</span><span class="sxs-lookup"><span data-stu-id="bc613-102">Details</span></span>

<span data-ttu-id="bc613-103">Für Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, gibt der Rewriter die Compilerwarnung CC1036 aus, wenn der Invariantvertrag für <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> oder der Vorbedingungsvertrag für <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> die Methode <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> aufruft: &quot;Detected call to method 'System.String.IsNullOrWhteSpace(System.String)' without [Pure] in method&quot; (Erkannter Aufruf von Methode 'System.String.IsNullOrWhteSpace(System.String)' ohne [Pure] in der Methode). Dies ist eher eine Compilerwarnung als ein Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="bc613-103">For apps that target the .NET Framework 4.6.1, if the invariant contract for <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> or the precondition contract for <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> calls the <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> method, the rewriter emits compiler warning CC1036: &quot;Detected call to method 'System.String.IsNullOrWhteSpace(System.String)' without [Pure] in method.&quot; This is a compiler warning rather than a compiler error.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bc613-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="bc613-104">Suggestion</span></span>

<span data-ttu-id="bc613-105">Dieses Verhalten wurde in [GitHub-Problem Nr. 339](https://github.com/Microsoft/CodeContracts/issues/339) behandelt.</span><span class="sxs-lookup"><span data-stu-id="bc613-105">This behavior was addressed in [GitHub Issue #339](https://github.com/Microsoft/CodeContracts/issues/339).</span></span> <span data-ttu-id="bc613-106">Um diese Warnung zu vermeiden, können Sie eine aktualisierte Version des Quellcodes für das Codevertragstool auf [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) herunterladen und kompilieren.</span><span class="sxs-lookup"><span data-stu-id="bc613-106">To eliminate this warning, you can download and compile an updated version of the source code for the Code Contracts tool from [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span></span> <span data-ttu-id="bc613-107">Informationen zum Herunterladen befinden sich am unteren Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="bc613-107">Download information is found at the bottom of the page.</span></span>

| <span data-ttu-id="bc613-108">name</span><span class="sxs-lookup"><span data-stu-id="bc613-108">Name</span></span>    | <span data-ttu-id="bc613-109">Wert</span><span class="sxs-lookup"><span data-stu-id="bc613-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bc613-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="bc613-110">Scope</span></span>   |<span data-ttu-id="bc613-111">Gering</span><span class="sxs-lookup"><span data-stu-id="bc613-111">Minor</span></span>|
|<span data-ttu-id="bc613-112">Version</span><span class="sxs-lookup"><span data-stu-id="bc613-112">Version</span></span>|<span data-ttu-id="bc613-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="bc613-113">4.6.1</span></span>|
|<span data-ttu-id="bc613-114">Typ</span><span class="sxs-lookup"><span data-stu-id="bc613-114">Type</span></span>|<span data-ttu-id="bc613-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bc613-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bc613-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="bc613-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|
