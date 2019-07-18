---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804648"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load entfernt die Symbol-Eigenschaft nicht

|   |   |
|---|---|
|Details|Wenn für den Workflow-Designer .NET Framework 4.5 als Zielplattform verwendet und ein neu gehosteter Workflow der Version 3.5 mit der Methode <xref:System.Activities.Presentation.WorkflowDesigner.Load> geladen wird, wird beim Speichern des Workflows eine <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> ausgelöst.|
|Vorschlag|Dieser Fehler tritt nur auf, wenn der Workflow-Designer auf .NET Framework 4.5 ausgerichtet ist. Daher kann das Problem umgangen werden, indem <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> auf .NET Framework 4.0 festgelegt wird. Alternativ kann der Fehler umgangen werden, indem anstelle von <xref:System.Activities.Presentation.WorkflowDesigner.Load> die Methode <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> zum Laden des Workflows verwendet wird.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

