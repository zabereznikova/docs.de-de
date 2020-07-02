---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621245"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>Der Workflow löst jetzt anstelle einer NullReferenceException teilweise eine ursprüngliche Ausnahme aus

#### <a name="details"></a>Details

In .NET Framework 4.6.2 und früheren Versionen löst die System.Activities-Workflowruntime eine <code>null</code> aus, wenn die Execute-Methode einer Workflowaktivität eine Ausnahme mit einem <xref:System.Exception.Message>-Wert für die <xref:System.NullReferenceException?displayProperty=fullName>-Eigenschaft auslöst, wodurch die ursprüngliche Ausnahme maskiert wird. In .NET Framework 4.7 wird die zuvor maskierte Ausnahme ausgelöst.

#### <a name="suggestion"></a>Vorschlag

Wenn Ihr Code von der Verarbeitung von <xref:System.NullReferenceException?displayProperty=fullName> abhängig ist, ändern Sie diesen, um die Ausnahmen zu erfassen, die Ihre benutzerdefinierten Aktivitäten auslösen könnten.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.7|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
