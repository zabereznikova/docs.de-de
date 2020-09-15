---
ms.openlocfilehash: c557f1cb65a675446bc77c57ef91972df92712bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617161"
---
### <a name="iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a><span data-ttu-id="db0a4-101">Die IAsyncResult.CompletedSynchronously-Eigenschaft muss korrekt sein, damit die resultierende Aufgabe abgeschlossen wird</span><span class="sxs-lookup"><span data-stu-id="db0a4-101">IAsyncResult.CompletedSynchronously property must be correct for the resulting task to complete</span></span>

#### <a name="details"></a><span data-ttu-id="db0a4-102">Details</span><span class="sxs-lookup"><span data-stu-id="db0a4-102">Details</span></span>

<span data-ttu-id="db0a4-103">Wenn Sie TaskFactory.FromAsync aufrufen, muss die Implementierung der <xref:System.IAsyncResult.CompletedSynchronously>-Eigenschaft korrekt sein, damit die resultierende Aufgabe abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="db0a4-103">When calling TaskFactory.FromAsync, the implementation of the <xref:System.IAsyncResult.CompletedSynchronously> property must be correct for the resulting task to complete.</span></span> <span data-ttu-id="db0a4-104">Das heißt, die Eigenschaft muss für den Fall, und ausschließlich für den Fall, dass die Implementierung synchron abgeschlossen wurde, „true“ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="db0a4-104">That is, the property must return true if, and only if, the implementation completed synchronously.</span></span> <span data-ttu-id="db0a4-105">Zuvor wurde die Eigenschaft nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="db0a4-105">Previously, the property was not checked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="db0a4-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="db0a4-106">Suggestion</span></span>

<span data-ttu-id="db0a4-107">Wenn <xref:System.IAsyncResult?displayProperty=fullName>-Implementierungen nur dann ordnungsgemäß TRUE für die <xref:System.IAsyncResult.CompletedSynchronously?displayProperty=fullName>-Eigenschaft zurückgeben, wenn eine Aufgabe synchron abgeschlossen wurde, tritt kein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="db0a4-107">If <xref:System.IAsyncResult?displayProperty=fullName> implementations correctly return true for the <xref:System.IAsyncResult.CompletedSynchronously?displayProperty=fullName> property only when a task completed synchronously, then no break will be observed.</span></span> <span data-ttu-id="db0a4-108">Benutzer sollten <xref:System.IAsyncResult?displayProperty=fullName>-Implementierungen überprüfen, die sie ggf. besitzen, um sicherzustellen, dass ordnungsgemäß ausgewertet wird, ob eine Aufgabe synchron abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="db0a4-108">Users should review <xref:System.IAsyncResult?displayProperty=fullName> implementations they own (if any) to ensure that they correctly evaluate whether a task completed synchronously or not.</span></span>

| <span data-ttu-id="db0a4-109">name</span><span class="sxs-lookup"><span data-stu-id="db0a4-109">Name</span></span>    | <span data-ttu-id="db0a4-110">Wert</span><span class="sxs-lookup"><span data-stu-id="db0a4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="db0a4-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="db0a4-111">Scope</span></span>   | <span data-ttu-id="db0a4-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="db0a4-112">Edge</span></span>        |
| <span data-ttu-id="db0a4-113">Version</span><span class="sxs-lookup"><span data-stu-id="db0a4-113">Version</span></span> | <span data-ttu-id="db0a4-114">4.5</span><span class="sxs-lookup"><span data-stu-id="db0a4-114">4.5</span></span>         |
| <span data-ttu-id="db0a4-115">Typ</span><span class="sxs-lookup"><span data-stu-id="db0a4-115">Type</span></span>    | <span data-ttu-id="db0a4-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="db0a4-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="db0a4-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="db0a4-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult},System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult},System.Threading.Tasks.TaskCreationOptions,System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%600},System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%600},System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600},System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600},System.Threading.Tasks.TaskCreationOptions,System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%601},%60%600,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%601},%60%600,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%602},%60%600,%60%601,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,%60%602,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,%60%602,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%602},%60%600,%60%601,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%603},%60%600,%60%601,%60%602,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%603},%60%600,%60%601,%60%602,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
