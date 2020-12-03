---
title: 'Breaking Change: Parameternamen in RC2 geändert'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den einige Parameternamen für Referenzassemblys aus Vorschau- und Release-Candidate-Versionen von .NET 5.0 geändert wurden.
ms.date: 11/01/2020
ms.openlocfilehash: 554a4fa9e08fdb504f380465496d7e7e9df85814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759450"
---
# <a name="parameter-names-changed-in-rc2"></a><span data-ttu-id="c80ba-103">Parameternamen in RC2 geändert</span><span class="sxs-lookup"><span data-stu-id="c80ba-103">Parameter names changed in RC2</span></span>

<span data-ttu-id="c80ba-104">Einige Parameternamen für Referenzassemblys wurden so geändert, dass sie mit den Parameternamen in den Implementierungsassemblys übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c80ba-104">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

## <a name="change-description"></a><span data-ttu-id="c80ba-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="c80ba-105">Change description</span></span>

<span data-ttu-id="c80ba-106">In früheren .NET 5.0 Preview- und RC-Versionen unterscheiden sich einige Parameternamen in [Referenzassemblys](../../../../standard/assembly/reference-assemblies.md) von den entsprechenden Parametern in der Implementierungsassembly.</span><span class="sxs-lookup"><span data-stu-id="c80ba-106">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="c80ba-107">Dies kann Probleme bei der Verwendung von benannten Argumenten und Reflexion verursachen.</span><span class="sxs-lookup"><span data-stu-id="c80ba-107">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="c80ba-108">In .NET 5.0 RC2 wurden diese nicht übereinstimmenden Parameternamen in den Referenzassemblys so aktualisiert, dass sie den entsprechenden Parameternamen in den Implementierungsassemblys exakt entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c80ba-108">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="c80ba-109">In der folgenden Tabelle sind die APIs und Parameternamen aufgeführt, die sich geändert haben.</span><span class="sxs-lookup"><span data-stu-id="c80ba-109">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="c80ba-110">API</span><span class="sxs-lookup"><span data-stu-id="c80ba-110">API</span></span> | <span data-ttu-id="c80ba-111">Alter Parametername</span><span class="sxs-lookup"><span data-stu-id="c80ba-111">Old parameter name</span></span> | <span data-ttu-id="c80ba-112">Neuer Parametername</span><span class="sxs-lookup"><span data-stu-id="c80ba-112">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

## <a name="reason-for-change"></a><span data-ttu-id="c80ba-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="c80ba-113">Reason for change</span></span>

<span data-ttu-id="c80ba-114">Die Parameternamen wurden aus Gründen der Konsistenz und zum Vermeiden von Fehlern bei der Verwendung von benannten Argumenten und Reflexion geändert.</span><span class="sxs-lookup"><span data-stu-id="c80ba-114">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c80ba-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c80ba-115">Version introduced</span></span>

<span data-ttu-id="c80ba-116">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="c80ba-116">5.0 RC2</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c80ba-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="c80ba-117">Recommended action</span></span>

<span data-ttu-id="c80ba-118">Wenn aufgrund der Änderung eines Parameternamens ein Compilerfehler auftritt, aktualisieren Sie den Parameternamen entsprechend.</span><span class="sxs-lookup"><span data-stu-id="c80ba-118">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c80ba-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c80ba-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
