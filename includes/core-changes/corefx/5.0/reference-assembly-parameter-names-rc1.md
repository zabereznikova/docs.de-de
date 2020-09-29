---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738818"
---
### <a name="parameter-names-changed-in-rc1"></a><span data-ttu-id="77780-101">Parameternamen in RC1 geändert</span><span class="sxs-lookup"><span data-stu-id="77780-101">Parameter names changed in RC1</span></span>

<span data-ttu-id="77780-102">Einige Parameternamen für Referenzassemblys wurden so geändert, dass sie mit den Parameternamen in den Implementierungsassemblys übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="77780-102">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

#### <a name="change-description"></a><span data-ttu-id="77780-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="77780-103">Change description</span></span>

<span data-ttu-id="77780-104">In früheren .NET 5.0 Preview- und RC-Versionen unterscheiden sich einige Parameternamen in [Referenzassemblys](../../../../docs/standard/assembly/reference-assemblies.md) von den entsprechenden Parametern in der Implementierungsassembly.</span><span class="sxs-lookup"><span data-stu-id="77780-104">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../docs/standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="77780-105">Dies kann Probleme bei der Verwendung von benannten Argumenten und Reflexion verursachen.</span><span class="sxs-lookup"><span data-stu-id="77780-105">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="77780-106">In .NET 5.0 RC2 wurden diese nicht übereinstimmenden Parameternamen in den Referenzassemblys so aktualisiert, dass sie den entsprechenden Parameternamen in den Implementierungsassemblys exakt entsprechen.</span><span class="sxs-lookup"><span data-stu-id="77780-106">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="77780-107">In der folgenden Tabelle sind die APIs und Parameternamen aufgeführt, die sich geändert haben.</span><span class="sxs-lookup"><span data-stu-id="77780-107">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="77780-108">API</span><span class="sxs-lookup"><span data-stu-id="77780-108">API</span></span> | <span data-ttu-id="77780-109">Alter Parametername</span><span class="sxs-lookup"><span data-stu-id="77780-109">Old parameter name</span></span> | <span data-ttu-id="77780-110">Neuer Parametername</span><span class="sxs-lookup"><span data-stu-id="77780-110">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a><span data-ttu-id="77780-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="77780-111">Reason for change</span></span>

<span data-ttu-id="77780-112">Die Parameternamen wurden aus Gründen der Konsistenz und zum Vermeiden von Fehlern bei der Verwendung von benannten Argumenten und Reflexion geändert.</span><span class="sxs-lookup"><span data-stu-id="77780-112">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="77780-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="77780-113">Version introduced</span></span>

<span data-ttu-id="77780-114">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="77780-114">5.0 RC2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="77780-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="77780-115">Recommended action</span></span>

<span data-ttu-id="77780-116">Wenn aufgrund der Änderung eines Parameternamens ein Compilerfehler auftritt, aktualisieren Sie den Parameternamen entsprechend.</span><span class="sxs-lookup"><span data-stu-id="77780-116">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

#### <a name="category"></a><span data-ttu-id="77780-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="77780-117">Category</span></span>

<span data-ttu-id="77780-118">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="77780-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="77780-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="77780-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
