---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617218"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="d506b-101">List&lt;T&gt;.ForEach kann beim Ändern eines Listenelements eine Ausnahme auslösen</span><span class="sxs-lookup"><span data-stu-id="d506b-101">List&lt;T&gt;.ForEach can throw exception when modifying list item</span></span>

#### <a name="details"></a><span data-ttu-id="d506b-102">Details</span><span class="sxs-lookup"><span data-stu-id="d506b-102">Details</span></span>

<span data-ttu-id="d506b-103">Ab .NET Framework 4.5 löst ein <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})>-Enumerator eine <xref:System.InvalidOperationException?displayProperty=fullName>-Ausnahme aus, wenn ein Element in der aufrufenden Sammlung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="d506b-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=fullName> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="d506b-104">Zuvor hätte dies keine Ausnahme ausgelöst, aber zu Racebedingungen geführt.</span><span class="sxs-lookup"><span data-stu-id="d506b-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d506b-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d506b-105">Suggestion</span></span>

<span data-ttu-id="d506b-106">Im Idealfall sollte der Code unveränderlich sein, damit Listen nicht geändert werden, während ihre Elemente aufgezählt werden, da dies nie ein sicherer Vorgang ist.</span><span class="sxs-lookup"><span data-stu-id="d506b-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="d506b-107">Eine App kann auf .NET Framework 4.0 ausgelegt werden, um zum vorherigen Verhalten zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d506b-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>

| <span data-ttu-id="d506b-108">name</span><span class="sxs-lookup"><span data-stu-id="d506b-108">Name</span></span>    | <span data-ttu-id="d506b-109">Wert</span><span class="sxs-lookup"><span data-stu-id="d506b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d506b-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="d506b-110">Scope</span></span>   | <span data-ttu-id="d506b-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d506b-111">Edge</span></span>        |
| <span data-ttu-id="d506b-112">Version</span><span class="sxs-lookup"><span data-stu-id="d506b-112">Version</span></span> | <span data-ttu-id="d506b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d506b-113">4.5</span></span>         |
| <span data-ttu-id="d506b-114">Typ</span><span class="sxs-lookup"><span data-stu-id="d506b-114">Type</span></span>    | <span data-ttu-id="d506b-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="d506b-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d506b-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d506b-116">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>
