---
ms.openlocfilehash: 61d5885c19e39b138090c1a98fa26348724893c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496557"
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
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)`
- `M:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)`
- ``M:System.Activities.AsyncCodeActivity`1.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)``
- `M:System.Activities.WorkflowInvoker.Invoke`

-->
