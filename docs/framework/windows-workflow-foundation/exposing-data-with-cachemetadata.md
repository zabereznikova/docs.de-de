---
title: Verfügbarmachen von Daten mit CacheMetadata
ms.date: 03/30/2017
ms.assetid: 34832f23-e93b-40e6-a80b-606a855a00d9
ms.openlocfilehash: a044c896e56541ee954fc33853376eb8293c6ede
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482677"
---
# <a name="exposing-data-with-cachemetadata"></a><span data-ttu-id="111b2-102">Verfügbarmachen von Daten mit CacheMetadata</span><span class="sxs-lookup"><span data-stu-id="111b2-102">Exposing data with CacheMetadata</span></span>

<span data-ttu-id="111b2-103">Vor dem Ausführen einer Aktivität ruft die Workflowlaufzeit alle Aktivitätsinformationen ab, die für die Ausführung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="111b2-103">Before executing an activity, the workflow runtime obtains all of the information about the activity that it needs in order to maintain its execution.</span></span> <span data-ttu-id="111b2-104">Die Workflowlaufzeit ruft diese Informationen während der Ausführung der <xref:System.Activities.Activity.CacheMetadata%2A>-Methode ab.</span><span class="sxs-lookup"><span data-stu-id="111b2-104">The workflow runtime gets this information during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="111b2-105">Die Standardimplementierung dieser Methode stellt der Laufzeit alle öffentlichen Argumente, Variablen und untergeordneten Aktivitäten bereit, die von der Aktivität zur Ausführungszeit verfügbar gemacht werden. Wenn die Aktivität mehr Informationen als diese an die Laufzeit übergeben muss (z. B. private Member oder Aktivitäten, die von der Aktivität geplant werden sollen), kann diese Methode überschrieben werden, um diese Informationen zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="111b2-105">The default implementation of this method provides the runtime with all of the public arguments, variables, and child activities exposed by the activity at the time it is executed; if the activity needs to give more information to the runtime than this (such as private members, or activities to be scheduled by the activity), this method can be overridden to provide it.</span></span>

## <a name="default-cachemetadata-behavior"></a><span data-ttu-id="111b2-106">CacheMetadata-Standardverhalten</span><span class="sxs-lookup"><span data-stu-id="111b2-106">Default CacheMetadata behavior</span></span>

<span data-ttu-id="111b2-107">Die Standardimplementierung von <xref:System.Activities.NativeActivity.CacheMetadata%2A> für Aktivitäten, die aus <xref:System.Activities.NativeActivity> abgeleitet werden, verarbeitet die folgenden Methodentypen auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="111b2-107">The default implementation of <xref:System.Activities.NativeActivity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.NativeActivity> processes the following method types in the following ways:</span></span>

- <span data-ttu-id="111b2-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, oder <xref:System.Activities.InOutArgument%601> (generische Argumente): Diese Argumente als Argumente mit einem Namen zur Laufzeit verfügbar gemacht, und geben dem verfügbar gemachten Eigenschaftsnamen und Typ, die entsprechende argumentrichtung und einige Validierungsdaten gleich.</span><span class="sxs-lookup"><span data-stu-id="111b2-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, or <xref:System.Activities.InOutArgument%601> (generic arguments): These arguments are exposed to the runtime as arguments with a name and type equal to the exposed property name and type, the appropriate argument direction, and some validation data.</span></span>

- <span data-ttu-id="111b2-109"><xref:System.Activities.Variable> oder eine beliebige Unterklasse davon: Diese Member werden an die Laufzeit als öffentliche Variablen verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="111b2-109"><xref:System.Activities.Variable> or any subclass thereof: These members are exposed to the runtime as public variables.</span></span>

- <span data-ttu-id="111b2-110"><xref:System.Activities.Activity> oder eine beliebige Unterklasse davon: Diese Member werden an die Laufzeit als öffentliche untergeordnete Aktivitäten verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="111b2-110"><xref:System.Activities.Activity> or any subclass thereof: These members are exposed to the runtime as public child activities.</span></span> <span data-ttu-id="111b2-111">Das Standardverhalten kann explizit implementiert werden, durch den Aufruf <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>, und übergeben Sie die untergeordnete Aktivität.</span><span class="sxs-lookup"><span data-stu-id="111b2-111">The default behavior can be implemented explicitly by calling <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>, passing in the child activity.</span></span>

- <span data-ttu-id="111b2-112"><xref:System.Activities.ActivityDelegate> oder eine beliebige Unterklasse davon: Diese Member werden an die Laufzeit als öffentliche Delegaten verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="111b2-112"><xref:System.Activities.ActivityDelegate> or any subclass thereof: These members are exposed to the runtime as public delegates.</span></span>

- <span data-ttu-id="111b2-113"><xref:System.Collections.ICollection> Der Typ <xref:System.Activities.Variable>: Alle Elemente in der Auflistung werden zur Laufzeit als öffentliche Variablen verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="111b2-113"><xref:System.Collections.ICollection> of type <xref:System.Activities.Variable>: All elements in the collection are exposed to the runtime as public variables.</span></span>

- <span data-ttu-id="111b2-114"><xref:System.Collections.ICollection> Der Typ <xref:System.Activities.Activity>: Alle Elemente in der Auflistung werden zur Laufzeit als öffentliche untergeordnete Elemente verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="111b2-114"><xref:System.Collections.ICollection> of type <xref:System.Activities.Activity>: All elements in the collection are exposed to the runtime as public children.</span></span>

- <span data-ttu-id="111b2-115"><xref:System.Collections.ICollection> Der Typ <xref:System.Activities.ActivityDelegate>: Alle Elemente in der Auflistung werden zur Laufzeit als öffentliche Delegaten verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="111b2-115"><xref:System.Collections.ICollection> of type <xref:System.Activities.ActivityDelegate>: All elements in the collection are exposed to the runtime as public delegates.</span></span>

<span data-ttu-id="111b2-116">
  <xref:System.Activities.Activity.CacheMetadata%2A> für Aktivitäten, die aus <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity> abgeleitet werden, und <xref:System.Activities.AsyncCodeActivity> funktionieren auch wie oben beschrieben, mit Ausnahme der folgenden Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="111b2-116">The <xref:System.Activities.Activity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity>, and <xref:System.Activities.AsyncCodeActivity> also function as above, except for the following differences:</span></span>

- <span data-ttu-id="111b2-117">Klassen, die aus <xref:System.Activities.Activity> abgeleitet werden, können keine untergeordneten Aktivitäten oder Delegaten planen. Daher werden solche Member als importierte untergeordnete Elemente und Delegaten verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="111b2-117">Classes that derive from <xref:System.Activities.Activity> cannot schedule child activities or delegates, so such members are exposed as imported children and delegates; the</span></span>

- <span data-ttu-id="111b2-118">Klassen, die aus <xref:System.Activities.CodeActivity> und <xref:System.Activities.AsyncCodeActivity> abgeleitet werden, unterstützen keine Variablen, untergeordneten Elemente oder Delegaten, sodass nur Argumente verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="111b2-118">Classes that derive from <xref:System.Activities.CodeActivity> and <xref:System.Activities.AsyncCodeActivity> do not support variables, children, or delegates, so only arguments will be exposed.</span></span>

## <a name="overriding-cachemetadata-to-provide-information-to-the-runtime"></a><span data-ttu-id="111b2-119">Überschreiben von CacheMetadata zum Bereitstellen von Informationen für die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="111b2-119">Overriding CacheMetadata to provide information to the runtime</span></span>

<span data-ttu-id="111b2-120">Der folgende Codeausschnitt veranschaulicht, wie den Metadaten einer Aktivität während der Ausführung der <xref:System.Activities.Activity.CacheMetadata%2A>-Methode Informationen zu Membern hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="111b2-120">The following code snippet demonstrates how to add information about members to an activity’s metadata during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="111b2-121">Beachten Sie, dass die Basis der Methode aufgerufen wird, um alle öffentlichen Daten zur Aktivität zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="111b2-121">Note that the base of the method is called to cache all public data about the activity.</span></span>

```csharp
protected override void CacheMetadata(NativeActivityMetadata metadata)
{
    base.CacheMetadata(metadata);
    metadata.AddImplementationChild(this._writeLine);
    metadata.AddVariable(this._myVariable);
    metadata.AddImplementationVariable(this._myImplementationVariable);

    RuntimeArgument argument = new RuntimeArgument("MyArgument", ArgumentDirection.In, typeof(SomeType));
    metadata.Bind(argument, this.SomeName);
    metadata.AddArgument(argument);
}
```

## <a name="using-cachemetadata-to-expose-implementation-children"></a><span data-ttu-id="111b2-122">Verwenden von CacheMetadata zum Verfügbarmachen von untergeordneten Elementen der Implementierung</span><span class="sxs-lookup"><span data-stu-id="111b2-122">Using CacheMetadata to expose implementation children</span></span>

<span data-ttu-id="111b2-123">Zur Übergabe von Daten an untergeordnete Aktivitäten, die mithilfe von Variablen von einer Aktivität geplant werden sollen, müssen die Variablen als Implementierungsvariablen hinzugefügt werden. Die Werte von öffentlichen Variablen können nicht auf diese Weise festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="111b2-123">In order to pass data to child activities that are to be scheduled by an activity using variables, it is necessary to add the variables as implementation variables; public variables cannot have their values set this way.</span></span> <span data-ttu-id="111b2-124">Der Grund ist, dass Aktivitäten nach Möglichkeit eher als Implementierungen von Funktionen (die über Parameter verfügen) ausgeführt werden sollen und nicht als gekapselte Klassen (die über Eigenschaften verfügen).</span><span class="sxs-lookup"><span data-stu-id="111b2-124">The reason for this is that activities are intended to be executed more as implementations of functions (which have parameters), rather than encapsulated classes (which have properties).</span></span> <span data-ttu-id="111b2-125">Es gibt jedoch Situationen, in denen die Argumente explizit festgelegt werden müssen, beispielsweise beim Verwenden von <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, da die geplante Aktivität nicht so auf die Argumente der übergeordneten Aktivität zugreifen kann wie eine untergeordnete Aktivität.</span><span class="sxs-lookup"><span data-stu-id="111b2-125">However, there are situations in which the arguments must be explicitly set, such as when using <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, since the scheduled activity doesn't have access to the parent activity's arguments in the way a child activity would.</span></span>

<span data-ttu-id="111b2-126">Der folgende Codeausschnitt veranschaulicht, wie ein Argument aus einer systemeigene Aktivität mit <xref:System.Activities.Activity.CacheMetadata%2A> an eine geplante Aktivität übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="111b2-126">The following code snippet demonstrates how to pass an argument form a native activity into a scheduled activity using <xref:System.Activities.Activity.CacheMetadata%2A>.</span></span>

```csharp
public sealed class ChildActivity : NativeActivity
{
    public WriteLine _writeLine;
    public InArgument<string> Message { get; set; }
    private Variable<string> MessageVariable { get; set; }
    public ChildActivity()
    {
        MessageVariable = new Variable<string>();
        _writeLine = new WriteLine
        {
            Text = new InArgument<string>(MessageVariable),
        };
    }
    protected override void CacheMetadata(NativeActivityMetadata metadata)
    {
        base.CacheMetadata(metadata);
        metadata.AddImplementationVariable(this.MessageVariable);
        metadata.AddImplementationChild(this._writeLine);
    }
    protected override void Execute(NativeActivityContext context)
    {
        string configuredMessage = context.GetValue(Message);
        context.SetValue(MessageVariable, configuredMessage);
        context.ScheduleActivity(this._writeLine);
    }
}
```
