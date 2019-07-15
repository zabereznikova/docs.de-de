---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804648"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="87129-101">WorkflowDesigner.Load entfernt die Symbol-Eigenschaft nicht</span><span class="sxs-lookup"><span data-stu-id="87129-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

|   |   |
|---|---|
|<span data-ttu-id="87129-102">Details</span><span class="sxs-lookup"><span data-stu-id="87129-102">Details</span></span>|<span data-ttu-id="87129-103">Wenn für den Workflow-Designer .NET Framework 4.5 als Zielplattform verwendet und ein neu gehosteter Workflow der Version 3.5 mit der Methode <xref:System.Activities.Presentation.WorkflowDesigner.Load> geladen wird, wird beim Speichern des Workflows eine <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="87129-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> is thrown while saving the workflow.</span></span>|
|<span data-ttu-id="87129-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="87129-104">Suggestion</span></span>|<span data-ttu-id="87129-105">Dieser Fehler tritt nur auf, wenn der Workflow-Designer auf .NET Framework 4.5 ausgerichtet ist. Daher kann das Problem umgangen werden, indem <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> auf .NET Framework 4.0 festgelegt wird. Alternativ kann der Fehler umgangen werden, indem anstelle von <xref:System.Activities.Presentation.WorkflowDesigner.Load> die Methode <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> zum Laden des Workflows verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87129-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>|
|<span data-ttu-id="87129-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="87129-106">Scope</span></span>|<span data-ttu-id="87129-107">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="87129-107">Major</span></span>|
|<span data-ttu-id="87129-108">Version</span><span class="sxs-lookup"><span data-stu-id="87129-108">Version</span></span>|<span data-ttu-id="87129-109">4.5</span><span class="sxs-lookup"><span data-stu-id="87129-109">4.5</span></span>|
|<span data-ttu-id="87129-110">Typ</span><span class="sxs-lookup"><span data-stu-id="87129-110">Type</span></span>|<span data-ttu-id="87129-111">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="87129-111">Retargeting</span></span>|
|<span data-ttu-id="87129-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="87129-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

