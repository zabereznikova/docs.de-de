---
ms.openlocfilehash: 6431f3b4d0983c44629e4fe760c75adcc277ddd4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497868"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a><span data-ttu-id="01976-101">Einige .NET-APIs führen zu erstmaligen (behandelten) EntryPointNotFoundExceptions</span><span class="sxs-lookup"><span data-stu-id="01976-101">Some .NET APIs cause first chance (handled) EntryPointNotFoundExceptions</span></span>

#### <a name="details"></a><span data-ttu-id="01976-102">Details</span><span class="sxs-lookup"><span data-stu-id="01976-102">Details</span></span>

<span data-ttu-id="01976-103">In .NET Framework 4.5 hat eine geringe Anzahl von .NET-Methoden damit begonnen, erstmalige <xref:System.EntryPointNotFoundException?displayProperty=fullName> auszulösen.</span><span class="sxs-lookup"><span data-stu-id="01976-103">In the .NET Framework 4.5, a small number of .NET methods began throwing first chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span> <span data-ttu-id="01976-104">Diese Ausnahmen wurden in .NET Framework behandelt, konnten aber die Testautomatisierung unterbrechen, die keine erstmaligen Ausnahmen erwartete.</span><span class="sxs-lookup"><span data-stu-id="01976-104">These exceptions were handled within the .NET Framework, but could break test automation that did not expect the first chance exceptions.</span></span> <span data-ttu-id="01976-105">Dieselben APIs stören einige ApiVerifier-Szenarien, wenn „HighVersionLie“ aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="01976-105">These same APIs break some ApiVerifier scenarios when HighVersionLie is enabled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="01976-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="01976-106">Suggestion</span></span>

<span data-ttu-id="01976-107">Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="01976-107">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="01976-108">Alternativ kann die Testautomatisierung aktualisiert werden, damit keine Störung durch erstmalige <xref:System.EntryPointNotFoundException?displayProperty=fullName> erfolgt.</span><span class="sxs-lookup"><span data-stu-id="01976-108">Alternatively, test automation can be updated to not break on first-chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="01976-109">name</span><span class="sxs-lookup"><span data-stu-id="01976-109">Name</span></span>    | <span data-ttu-id="01976-110">Wert</span><span class="sxs-lookup"><span data-stu-id="01976-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="01976-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="01976-111">Scope</span></span>   |<span data-ttu-id="01976-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="01976-112">Edge</span></span>|
|<span data-ttu-id="01976-113">Version</span><span class="sxs-lookup"><span data-stu-id="01976-113">Version</span></span>|<span data-ttu-id="01976-114">4.5</span><span class="sxs-lookup"><span data-stu-id="01976-114">4.5</span></span>|
|<span data-ttu-id="01976-115">Typ</span><span class="sxs-lookup"><span data-stu-id="01976-115">Type</span></span>|<span data-ttu-id="01976-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="01976-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="01976-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="01976-117">Affected APIs</span></span>

- <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)>

<!--

#### Affected APIs

- `M:System.Diagnostics.Debug.Assert(System.Boolean)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])`
- `M:System.Xml.Serialization.XmlSerializer.#ctor(System.Type)`

-->
