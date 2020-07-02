---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622043"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a><span data-ttu-id="2cc04-101">Einige .NET-APIs führen zu erstmaligen (behandelten) EntryPointNotFoundExceptions</span><span class="sxs-lookup"><span data-stu-id="2cc04-101">Some .NET APIs cause first chance (handled) EntryPointNotFoundExceptions</span></span>

#### <a name="details"></a><span data-ttu-id="2cc04-102">Details</span><span class="sxs-lookup"><span data-stu-id="2cc04-102">Details</span></span>

<span data-ttu-id="2cc04-103">In .NET Framework 4.5 hat eine geringe Anzahl von .NET-Methoden damit begonnen, erstmalige <xref:System.EntryPointNotFoundException?displayProperty=fullName> auszulösen.</span><span class="sxs-lookup"><span data-stu-id="2cc04-103">In the .NET Framework 4.5, a small number of .NET methods began throwing first chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span> <span data-ttu-id="2cc04-104">Diese Ausnahmen wurden in .NET Framework behandelt, konnten aber die Testautomatisierung unterbrechen, die keine erstmaligen Ausnahmen erwartete.</span><span class="sxs-lookup"><span data-stu-id="2cc04-104">These exceptions were handled within the .NET Framework, but could break test automation that did not expect the first chance exceptions.</span></span> <span data-ttu-id="2cc04-105">Dieselben APIs stören einige ApiVerifier-Szenarien, wenn „HighVersionLie“ aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2cc04-105">These same APIs break some ApiVerifier scenarios when HighVersionLie is enabled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2cc04-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2cc04-106">Suggestion</span></span>

<span data-ttu-id="2cc04-107">Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="2cc04-107">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="2cc04-108">Alternativ kann die Testautomatisierung aktualisiert werden, damit keine Störung durch erstmalige <xref:System.EntryPointNotFoundException?displayProperty=fullName> erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2cc04-108">Alternatively, test automation can be updated to not break on first-chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="2cc04-109">name</span><span class="sxs-lookup"><span data-stu-id="2cc04-109">Name</span></span>    | <span data-ttu-id="2cc04-110">Wert</span><span class="sxs-lookup"><span data-stu-id="2cc04-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2cc04-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="2cc04-111">Scope</span></span>   |<span data-ttu-id="2cc04-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2cc04-112">Edge</span></span>|
|<span data-ttu-id="2cc04-113">Version</span><span class="sxs-lookup"><span data-stu-id="2cc04-113">Version</span></span>|<span data-ttu-id="2cc04-114">4.5</span><span class="sxs-lookup"><span data-stu-id="2cc04-114">4.5</span></span>|
|<span data-ttu-id="2cc04-115">Typ</span><span class="sxs-lookup"><span data-stu-id="2cc04-115">Type</span></span>|<span data-ttu-id="2cc04-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2cc04-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2cc04-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2cc04-117">Affected APIs</span></span>

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|
