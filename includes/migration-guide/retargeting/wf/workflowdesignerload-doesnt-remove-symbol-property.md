---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616061"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="70332-101">WorkflowDesigner.Load entfernt die Symbol-Eigenschaft nicht</span><span class="sxs-lookup"><span data-stu-id="70332-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

#### <a name="details"></a><span data-ttu-id="70332-102">Details</span><span class="sxs-lookup"><span data-stu-id="70332-102">Details</span></span>

<span data-ttu-id="70332-103">Wenn für den Workflow-Designer .NET Framework 4.5 als Zielplattform verwendet und ein neu gehosteter Workflow der Version 3.5 mit der Methode <xref:System.Activities.Presentation.WorkflowDesigner.Load> geladen wird, wird beim Speichern des Workflows eine <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="70332-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> is thrown while saving the workflow.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="70332-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="70332-104">Suggestion</span></span>

<span data-ttu-id="70332-105">Dieser Fehler tritt nur auf, wenn der Workflow-Designer auf .NET Framework 4.5 ausgerichtet ist. Daher kann das Problem umgangen werden, indem `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` auf .NET Framework 4.0 festgelegt wird. Alternativ kann der Fehler umgangen werden, indem anstelle von <xref:System.Activities.Presentation.WorkflowDesigner.Load> die Methode <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> zum Laden des Workflows verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70332-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>

| <span data-ttu-id="70332-106">name</span><span class="sxs-lookup"><span data-stu-id="70332-106">Name</span></span>    | <span data-ttu-id="70332-107">Wert</span><span class="sxs-lookup"><span data-stu-id="70332-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="70332-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="70332-108">Scope</span></span>   | <span data-ttu-id="70332-109">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="70332-109">Major</span></span>       |
| <span data-ttu-id="70332-110">Version</span><span class="sxs-lookup"><span data-stu-id="70332-110">Version</span></span> | <span data-ttu-id="70332-111">4.5</span><span class="sxs-lookup"><span data-stu-id="70332-111">4.5</span></span>         |
| <span data-ttu-id="70332-112">Typ</span><span class="sxs-lookup"><span data-stu-id="70332-112">Type</span></span>    | <span data-ttu-id="70332-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="70332-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="70332-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="70332-114">Affected APIs</span></span>

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
