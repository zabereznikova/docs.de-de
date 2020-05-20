---
title: Flussdiagrammworkflows
description: In diesem Artikel wird die Flowchart-Aktivität beschrieben, die in der Regel zur Implementierung nicht sequenzieller Workflows in Workflow Foundation verwendet wird.
ms.date: 03/30/2017
ms.assetid: b0a3475c-d22f-49eb-8912-973c960aebf5
ms.openlocfilehash: ce0661653a1d50b3f7264246b810faabbd12bf5f
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419914"
---
# <a name="flowchart-workflows"></a><span data-ttu-id="c00be-103">Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="c00be-103">Flowchart Workflows</span></span>

<span data-ttu-id="c00be-104">Ein Flussdiagramm ist ein bekanntes Paradigma zum Entwerfen von Programmen.</span><span class="sxs-lookup"><span data-stu-id="c00be-104">A flowchart is a well-known paradigm for designing programs.</span></span> <span data-ttu-id="c00be-105">Die Flowchart-Aktivität wird in der Regel dazu verwendet, nicht sequenzielle Workflows zu implementieren. Sie kann jedoch auch für sequenzielle Workflows verwendet werden, falls es keine `FlowDecision`-Knoten gibt.</span><span class="sxs-lookup"><span data-stu-id="c00be-105">The Flowchart activity is typically used to implement non-sequential workflows, but can be used for sequential workflows if no `FlowDecision` nodes are used.</span></span>

## <a name="flowchart-workflow-structure"></a><span data-ttu-id="c00be-106">Flussdiagramm-Workflow Struktur</span><span class="sxs-lookup"><span data-stu-id="c00be-106">Flowchart workflow structure</span></span>

 <span data-ttu-id="c00be-107">Eine Flowchart-Aktivität ist eine Aktivität, die eine Auflistung von Aktivitäten enthält, die ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c00be-107">A Flowchart activity is an activity that contains a collection of activities to be executed.</span></span>  <span data-ttu-id="c00be-108">Flussdiagramme enthalten auch Flusssteuerungselemente wie <xref:System.Activities.Statements.FlowDecision> und <xref:System.Activities.Statements.FlowSwitch%601>, die die Ausführung zwischen enthaltenen Aktivitäten auf der Grundlage der Variablenwerte steuern.</span><span class="sxs-lookup"><span data-stu-id="c00be-108">Flowcharts also contain flow control elements such as <xref:System.Activities.Statements.FlowDecision> and <xref:System.Activities.Statements.FlowSwitch%601> that direct execution between contained activities based on the values of variables.</span></span>

## <a name="types-of-flow-nodes"></a><span data-ttu-id="c00be-109">Typen von Fluss Knoten</span><span class="sxs-lookup"><span data-stu-id="c00be-109">Types of flow nodes</span></span>

 <span data-ttu-id="c00be-110">Andere Elementtypen werden abhängig vom erforderlichen Typ der Flusssteuerung verwendet, wenn das Element ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c00be-110">Different types of elements are used depending on the type of flow control required when the element executes.</span></span> <span data-ttu-id="c00be-111">Es gibt folgende Typen von Flussdiagrammelementen:</span><span class="sxs-lookup"><span data-stu-id="c00be-111">Types of flowchart elements include:</span></span>

- <span data-ttu-id="c00be-112">`FlowStep` – modelliert einen Ausführungsschritt im Flussdiagramm.</span><span class="sxs-lookup"><span data-stu-id="c00be-112">`FlowStep` - Models one step of execution in the flowchart.</span></span>

- <span data-ttu-id="c00be-113">`FlowDecision` – verzweigt die Ausführung auf Grundlage einer booleschen Bedingung, wie dies auch bei <xref:System.Activities.Statements.If> der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="c00be-113">`FlowDecision` - Branches execution based on a Boolean condition, similar to <xref:System.Activities.Statements.If>.</span></span>

- <span data-ttu-id="c00be-114">`FlowSwitch` – verzweigt die Ausführung auf Grundlage eines exklusiven Schalters, wie dies auch bei <xref:System.Activities.Statements.Switch%601> der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="c00be-114">`FlowSwitch` – Branches execution based on an exclusive switch, similar to <xref:System.Activities.Statements.Switch%601>.</span></span>

<span data-ttu-id="c00be-115">Jeder Link verfügt über eine `Action`-Eigenschaft, die eine <xref:System.Activities.ActivityAction> definiert, mit der untergeordnete Aktivitäten ausgeführt werden können, und über mindestens eine `Next`-Eigenschaft, die definiert, welche Elemente ausgeführt werden sollen, wenn das aktuelle Element die Ausführung beendet.</span><span class="sxs-lookup"><span data-stu-id="c00be-115">Each link has an `Action` property that defines a <xref:System.Activities.ActivityAction> that can be used to execute child activities, and one or more `Next` properties that define which element or elements to execute when the current element finishes execution.</span></span>

### <a name="creating-a-basic-activity-sequence-with-a-flowstep-node"></a><span data-ttu-id="c00be-116">Erstellen einer grundlegenden Aktivitäts Sequenz mit einem FlowStep-Knoten</span><span class="sxs-lookup"><span data-stu-id="c00be-116">Creating a basic activity sequence with a FlowStep node</span></span>

<span data-ttu-id="c00be-117">Um eine grundlegende Sequenz zu modellieren, in der zwei Aktivitäten abwechselnd ausgeführt werden, wird das `FlowStep`-Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="c00be-117">To model a basic sequence in which two activities execute in turn, the `FlowStep` element is used.</span></span> <span data-ttu-id="c00be-118">Im folgenden Beispiel werden mithilfe des `FlowStep`-Elements zwei Aktivitäten abwechselnd ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c00be-118">In the following example, two `FlowStep` elements are used to execute two activities in sequence.</span></span>

```xml
<Flowchart>
  <FlowStep>
    <Assign DisplayName="Get Name">
      <Assign.To>
        <OutArgument x:TypeArguments="x:String">[result]</OutArgument>
      </Assign.To>
      <Assign.Value>
        <InArgument x:TypeArguments="x:String">["User"]</InArgument>
      </Assign.Value>
    </Assign>
    <FlowStep.Next>
      <FlowStep>
        <WriteLine Text="Hello, " & [result]/>
      </FlowStep>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-a-conditional-flowchart-with-a-flowdecision-node"></a><span data-ttu-id="c00be-119">Erstellen eines bedingten Fluss Diagramms mit einem FlowDecision-Knoten</span><span class="sxs-lookup"><span data-stu-id="c00be-119">Creating a conditional flowchart with a FlowDecision node</span></span>

<span data-ttu-id="c00be-120">Um einen bedingten Flussknoten in einem Flussdiagramm-Workflow zu modellieren (d. h., einen Link zu erstellen, der als normales Entscheidungssymbol eines Flussdiagramms fungiert), wird ein <xref:System.Activities.Statements.FlowDecision>-Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="c00be-120">To model a conditional flow node in a flowchart workflow (that is, to create a link that functions as a traditional flowchart's decision symbol), a <xref:System.Activities.Statements.FlowDecision> node is used.</span></span> <span data-ttu-id="c00be-121">Die <xref:System.Activities.Statements.FlowDecision.Condition%2A>-Eigenschaft des Knotens wird auf einen Ausdruck festgelegt, der die Bedingung definiert, und die <xref:System.Activities.Statements.FlowDecision.True%2A>-Eigenschaft und die <xref:System.Activities.Statements.FlowDecision.False%2A>-Eigenschaft werden auf <xref:System.Activities.Statements.FlowNode>-Instanzen festgelegt, die ausgeführt werden sollen, wenn der Ausdruck `true` oder `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="c00be-121">The <xref:System.Activities.Statements.FlowDecision.Condition%2A> property of the node is set to an expression that defines the condition, and the <xref:System.Activities.Statements.FlowDecision.True%2A> and <xref:System.Activities.Statements.FlowDecision.False%2A> properties are set to <xref:System.Activities.Statements.FlowNode> instances to be executed if the expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="c00be-122">Im folgenden Beispiel wird gezeigt, wie ein Workflow definiert wird, der einen <xref:System.Activities.Statements.FlowDecision>-Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="c00be-122">The following example shows how to define a workflow that uses a <xref:System.Activities.Statements.FlowDecision> node.</span></span>

```xml
<Flowchart>
  <FlowStep>
    <Read Result="[s]"/>
    <FlowStep.Next>
      <FlowDecision>
        <IsEmpty Input="[s]" />
        <FlowDecision.True>
          <FlowStep>
            <Write Text="Empty"/>
          </FlowStep>
        </FlowDecision.True>
        <FlowDecision.False>
          <FlowStep>
            <Write Text="Non-Empty"/>
          </FlowStep>
        </FlowDecision.False>
      </FlowDecision>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-an-exclusive-switch-with-a-flowswitch-node"></a><span data-ttu-id="c00be-123">Erstellen eines exklusiven Schalters mit einem FlowSwitch-Knoten</span><span class="sxs-lookup"><span data-stu-id="c00be-123">Creating an exclusive switch with a FlowSwitch node</span></span>

<span data-ttu-id="c00be-124">Um ein Flussdiagramm zu modellieren, in dem ein exklusiver Pfad auf Grundlage eines übereinstimmenden Werts ausgewählt wird, wird der <xref:System.Activities.Statements.FlowSwitch%601>-Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="c00be-124">To model a flowchart in which one exclusive path is selected based on a matching value, the <xref:System.Activities.Statements.FlowSwitch%601> node is used.</span></span> <span data-ttu-id="c00be-125">Die <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>-Eigenschaft wird auf <xref:System.Activities.Activity%601> mit dem Typparameter <xref:System.Object> festgelegt, der den Wert definiert, mit dem die Auswahlen verglichen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c00be-125">The <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> property is set to a <xref:System.Activities.Activity%601> with a type parameter of <xref:System.Object> that defines the value to match choices against.</span></span> <span data-ttu-id="c00be-126">Die <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>-Eigenschaft definiert ein Wörterbuch von Schlüsseln sowie <xref:System.Activities.Statements.FlowNode>-Objekte, mit denen der bedingte Ausdruck verglichen werden soll, und einen Satz von <xref:System.Activities.Statements.FlowNode>-Objekten, die definieren, wie der Ausführungsfluss erfolgen soll, wenn der angegebene Fall eine Entsprechung für den bedingten Ausdruck findet.</span><span class="sxs-lookup"><span data-stu-id="c00be-126">The <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> property defines a dictionary of keys and <xref:System.Activities.Statements.FlowNode> objects to match against the conditional expression, and a set of <xref:System.Activities.Statements.FlowNode> objects that define how execution should flow if the given case matches the conditional expression.</span></span> <span data-ttu-id="c00be-127">Der <xref:System.Activities.Statements.FlowSwitch%601> definiert außerdem eine <xref:System.Activities.Statements.FlowSwitch%601.Default%2A>-Eigenschaft, die den Ausführungsfluss für den Fall definiert, dass keine Übereinstimmung mit dem bedingten Ausdruck gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="c00be-127">The <xref:System.Activities.Statements.FlowSwitch%601> also defines a <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> property that defines how execution should flow if no cases match the condition expression.</span></span> <span data-ttu-id="c00be-128">Das folgende Beispiel zeigt die Definition eines Workflows, der ein <xref:System.Activities.Statements.FlowSwitch%601>-Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="c00be-128">The following example demonstrates how to define a workflow that uses a <xref:System.Activities.Statements.FlowSwitch%601> element.</span></span>

```xml
<Flowchart>
  <FlowSwitch>
    <FlowStep x:Key="Red">
      <WriteRed/>
    </FlowStep>
    <FlowStep x:Key="Blue">
      <WriteBlue/>
    </FlowStep>
    <FlowStep x:Key="Green">
      <WriteGreen/>
    </FlowStep>
  </FlowSwitch>
</Flowchart>
```
