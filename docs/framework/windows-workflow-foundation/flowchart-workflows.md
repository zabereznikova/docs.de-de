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
# <a name="flowchart-workflows"></a>Flussdiagrammworkflows

Ein Flussdiagramm ist ein bekanntes Paradigma zum Entwerfen von Programmen. Die Flowchart-Aktivität wird in der Regel dazu verwendet, nicht sequenzielle Workflows zu implementieren. Sie kann jedoch auch für sequenzielle Workflows verwendet werden, falls es keine `FlowDecision`-Knoten gibt.

## <a name="flowchart-workflow-structure"></a>Flussdiagramm-Workflow Struktur

 Eine Flowchart-Aktivität ist eine Aktivität, die eine Auflistung von Aktivitäten enthält, die ausgeführt werden sollen.  Flussdiagramme enthalten auch Flusssteuerungselemente wie <xref:System.Activities.Statements.FlowDecision> und <xref:System.Activities.Statements.FlowSwitch%601>, die die Ausführung zwischen enthaltenen Aktivitäten auf der Grundlage der Variablenwerte steuern.

## <a name="types-of-flow-nodes"></a>Typen von Fluss Knoten

 Andere Elementtypen werden abhängig vom erforderlichen Typ der Flusssteuerung verwendet, wenn das Element ausgeführt wird. Es gibt folgende Typen von Flussdiagrammelementen:

- `FlowStep` – modelliert einen Ausführungsschritt im Flussdiagramm.

- `FlowDecision` – verzweigt die Ausführung auf Grundlage einer booleschen Bedingung, wie dies auch bei <xref:System.Activities.Statements.If> der Fall ist.

- `FlowSwitch` – verzweigt die Ausführung auf Grundlage eines exklusiven Schalters, wie dies auch bei <xref:System.Activities.Statements.Switch%601> der Fall ist.

Jeder Link verfügt über eine `Action`-Eigenschaft, die eine <xref:System.Activities.ActivityAction> definiert, mit der untergeordnete Aktivitäten ausgeführt werden können, und über mindestens eine `Next`-Eigenschaft, die definiert, welche Elemente ausgeführt werden sollen, wenn das aktuelle Element die Ausführung beendet.

### <a name="creating-a-basic-activity-sequence-with-a-flowstep-node"></a>Erstellen einer grundlegenden Aktivitäts Sequenz mit einem FlowStep-Knoten

Um eine grundlegende Sequenz zu modellieren, in der zwei Aktivitäten abwechselnd ausgeführt werden, wird das `FlowStep`-Element verwendet. Im folgenden Beispiel werden mithilfe des `FlowStep`-Elements zwei Aktivitäten abwechselnd ausgeführt.

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

### <a name="creating-a-conditional-flowchart-with-a-flowdecision-node"></a>Erstellen eines bedingten Fluss Diagramms mit einem FlowDecision-Knoten

Um einen bedingten Flussknoten in einem Flussdiagramm-Workflow zu modellieren (d. h., einen Link zu erstellen, der als normales Entscheidungssymbol eines Flussdiagramms fungiert), wird ein <xref:System.Activities.Statements.FlowDecision>-Knoten verwendet. Die <xref:System.Activities.Statements.FlowDecision.Condition%2A>-Eigenschaft des Knotens wird auf einen Ausdruck festgelegt, der die Bedingung definiert, und die <xref:System.Activities.Statements.FlowDecision.True%2A>-Eigenschaft und die <xref:System.Activities.Statements.FlowDecision.False%2A>-Eigenschaft werden auf <xref:System.Activities.Statements.FlowNode>-Instanzen festgelegt, die ausgeführt werden sollen, wenn der Ausdruck `true` oder `false` ergibt. Im folgenden Beispiel wird gezeigt, wie ein Workflow definiert wird, der einen <xref:System.Activities.Statements.FlowDecision>-Knoten verwendet.

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

### <a name="creating-an-exclusive-switch-with-a-flowswitch-node"></a>Erstellen eines exklusiven Schalters mit einem FlowSwitch-Knoten

Um ein Flussdiagramm zu modellieren, in dem ein exklusiver Pfad auf Grundlage eines übereinstimmenden Werts ausgewählt wird, wird der <xref:System.Activities.Statements.FlowSwitch%601>-Knoten verwendet. Die <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>-Eigenschaft wird auf <xref:System.Activities.Activity%601> mit dem Typparameter <xref:System.Object> festgelegt, der den Wert definiert, mit dem die Auswahlen verglichen werden sollen. Die <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>-Eigenschaft definiert ein Wörterbuch von Schlüsseln sowie <xref:System.Activities.Statements.FlowNode>-Objekte, mit denen der bedingte Ausdruck verglichen werden soll, und einen Satz von <xref:System.Activities.Statements.FlowNode>-Objekten, die definieren, wie der Ausführungsfluss erfolgen soll, wenn der angegebene Fall eine Entsprechung für den bedingten Ausdruck findet. Der <xref:System.Activities.Statements.FlowSwitch%601> definiert außerdem eine <xref:System.Activities.Statements.FlowSwitch%601.Default%2A>-Eigenschaft, die den Ausführungsfluss für den Fall definiert, dass keine Übereinstimmung mit dem bedingten Ausdruck gefunden wird. Das folgende Beispiel zeigt die Definition eines Workflows, der ein <xref:System.Activities.Statements.FlowSwitch%601>-Element verwendet.

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
