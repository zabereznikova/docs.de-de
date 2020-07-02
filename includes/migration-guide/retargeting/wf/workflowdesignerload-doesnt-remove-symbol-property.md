---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616061"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load entfernt die Symbol-Eigenschaft nicht

#### <a name="details"></a>Details

Wenn für den Workflow-Designer .NET Framework 4.5 als Zielplattform verwendet und ein neu gehosteter Workflow der Version 3.5 mit der Methode <xref:System.Activities.Presentation.WorkflowDesigner.Load> geladen wird, wird beim Speichern des Workflows eine <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> ausgelöst.

#### <a name="suggestion"></a>Vorschlag

Dieser Fehler tritt nur auf, wenn der Workflow-Designer auf .NET Framework 4.5 ausgerichtet ist. Daher kann das Problem umgangen werden, indem `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` auf .NET Framework 4.0 festgelegt wird. Alternativ kann der Fehler umgangen werden, indem anstelle von <xref:System.Activities.Presentation.WorkflowDesigner.Load> die Methode <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> zum Laden des Workflows verwendet wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.5         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
