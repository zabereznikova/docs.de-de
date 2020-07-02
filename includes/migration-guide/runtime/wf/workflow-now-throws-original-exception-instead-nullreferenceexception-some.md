---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621245"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="cd1c8-101">Der Workflow löst jetzt anstelle einer NullReferenceException teilweise eine ursprüngliche Ausnahme aus</span><span class="sxs-lookup"><span data-stu-id="cd1c8-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="cd1c8-102">Details</span><span class="sxs-lookup"><span data-stu-id="cd1c8-102">Details</span></span>

<span data-ttu-id="cd1c8-103">In .NET Framework 4.6.2 und früheren Versionen löst die System.Activities-Workflowruntime eine <code>null</code> aus, wenn die Execute-Methode einer Workflowaktivität eine Ausnahme mit einem <xref:System.Exception.Message>-Wert für die <xref:System.NullReferenceException?displayProperty=fullName>-Eigenschaft auslöst, wodurch die ursprüngliche Ausnahme maskiert wird. In .NET Framework 4.7 wird die zuvor maskierte Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cd1c8-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cd1c8-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="cd1c8-104">Suggestion</span></span>

<span data-ttu-id="cd1c8-105">Wenn Ihr Code von der Verarbeitung von <xref:System.NullReferenceException?displayProperty=fullName> abhängig ist, ändern Sie diesen, um die Ausnahmen zu erfassen, die Ihre benutzerdefinierten Aktivitäten auslösen könnten.</span><span class="sxs-lookup"><span data-stu-id="cd1c8-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="cd1c8-106">Name</span><span class="sxs-lookup"><span data-stu-id="cd1c8-106">Name</span></span>    | <span data-ttu-id="cd1c8-107">Wert</span><span class="sxs-lookup"><span data-stu-id="cd1c8-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cd1c8-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="cd1c8-108">Scope</span></span>   |<span data-ttu-id="cd1c8-109">Gering</span><span class="sxs-lookup"><span data-stu-id="cd1c8-109">Minor</span></span>|
|<span data-ttu-id="cd1c8-110">Version</span><span class="sxs-lookup"><span data-stu-id="cd1c8-110">Version</span></span>|<span data-ttu-id="cd1c8-111">4.7</span><span class="sxs-lookup"><span data-stu-id="cd1c8-111">4.7</span></span>|
|<span data-ttu-id="cd1c8-112">Typ</span><span class="sxs-lookup"><span data-stu-id="cd1c8-112">Type</span></span>|<span data-ttu-id="cd1c8-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="cd1c8-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd1c8-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="cd1c8-114">Affected APIs</span></span>

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
