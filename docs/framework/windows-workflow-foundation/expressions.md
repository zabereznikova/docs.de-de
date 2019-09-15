---
title: Ausdrücke-WF
ms.date: 03/30/2017
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
ms.openlocfilehash: 1c79d4294ce1e7d6f6fc13e8220f88919c8f6021
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989752"
---
# <a name="expressions"></a>Ausdrücke
Ein Windows Workflow Foundation (WF)-Ausdruck ist eine beliebige Aktivität, die ein Ergebnis zurückgibt. Alle Ausdrucksaktivitäten werden indirekt von <xref:System.Activities.Activity%601> abgeleitet, die eine <xref:System.Activities.OutArgument>-Eigenschaft mit dem Namen <xref:System.Activities.Activity%601.Result%2A> als Rückgabewert der Aktivität enthält. Im Lieferumfang von [!INCLUDE[wf1](../../../includes/wf1-md.md)] ist eine Vielzahl von Ausdrucksaktivitäten enthalten, darunter einfache Ausdrucksaktivitäten wie <xref:System.Activities.Expressions.VariableValue%601> und <xref:System.Activities.Expressions.VariableReference%601>, die den Zugriff auf einzelne Workflowvariablen über Operatoraktivitäten ermöglichen, sowie komplexe Aktivitäten wie <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> und <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>, die zum Erzielen des gewünschten Ergebnisses den Zugriff auf die volle Bandbreite der Visual Basic-Programmiersprache ermöglichen. Zusätzliche Ausdrucksaktivitäten können durch Ableitungen von <xref:System.Activities.CodeActivity%601> oder <xref:System.Activities.NativeActivity%601> erstellt werden.  
  
## <a name="using-expressions"></a>Verwenden von Ausdrücken  
 Workflow-Designer verwendet <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> und <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> für alle Ausdrücke in Visual Basic-Projekten sowie <xref:Microsoft.CSharp.Activities.CSharpValue%601> und <xref:Microsoft.CSharp.Activities.CSharpReference%601> für Ausdrücke in den C#-Workflowprojekten.  
  
> [!NOTE]
> Die unter C# Stützung für Ausdrücke in Workflow Projekten wurde in .NET Framework 4,5 eingeführt. Weitere Informationen finden [ C# ](csharp-expressions.md)Sie unter Ausdrücke.  
  
 Vom Designer erzeugte Workflows werden im XAML-Format gespeichert, bei dem Ausdrücke in eckige Klammern eingeschlossen sind. Dies wird im folgenden Beispiel veranschaulicht.  
  
```xml  
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <Variable x:TypeArguments="x:Int32" Default="1" Name="a" />  
    <Variable x:TypeArguments="x:Int32" Default="2" Name="b" />  
    <Variable x:TypeArguments="x:Int32" Default="3" Name="c" />  
    <Variable x:TypeArguments="x:Int32" Default="0" Name="r" />  
  </Sequence.Variables>  
  <Assign>  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:Int32">[r]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:Int32">[a + b + c]</InArgument>  
    </Assign.Value>  
  </Assign>  
</Sequence>  
```  
  
 Sie können beim Definieren eines Workflows im Code beliebige Ausdrucksaktivitäten verwenden. Im folgenden Beispiel wird die Verwendung von Operatoraktivitäten zum Hinzufügen von drei Zahlen veranschaulicht.  
  
```csharp  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int> {  
                Expression = new Add<int, int, int> {  
                    Left = new Add<int, int, int> {  
                        Left = new InArgument<int>(a),  
                        Right = new InArgument<int>(b)  
                    },  
                    Right = new InArgument<int>(c)  
                }  
            }  
        }  
    }  
};  
```  
  
 Der gleiche Workflow kann auch kürzer ausgedrückt werden, indem C#-Lambdaausdrücke verwendet werden. Dies ist im folgenden Beispiel gezeigt.  
  
```csharp  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int>((ctx) => a.Get(ctx) + b.Get(ctx) + c.Get(ctx))  
        }  
    }  
};  
```  
  
 Außerdem können Sie den Workflow mithilfe von Visual Basic-Ausdrucksaktivitäten ausdrücken, wie im folgenden Beispiel gezeigt.  
  
```vb  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int>(new VisualBasicValue<int>("a + b + c"))  
        }  
    }  
};  
```  
  
## <a name="extending-available-expressions-with-custom-expression-activities"></a>Erweitern von verfügbaren Ausdrücken mit benutzerdefinierten Ausdrucksaktivitäten  
 Ausdrücke in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] sind erweiterbar und ermöglichen das Erstellen zusätzlicher Ausdrucksaktivitäten. Das folgende Beispiel zeigt eine Aktivität, die eine Summe aus drei ganzzahligen Werten zurückgibt.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Activities;  
  
namespace ExpressionsDemo  
{  
    public sealed class AddThreeValues : CodeActivity<int>  
    {  
        public InArgument<int> Value1 { get; set; }  
        public InArgument<int> Value2 { get; set; }  
        public InArgument<int> Value3 { get; set; }  
  
        protected override int Execute(CodeActivityContext context)  
        {  
            return Value1.Get(context) +   
                   Value2.Get(context) +   
                   Value3.Get(context);  
        }  
    }  
}  
```  
  
 Mit dieser neuen Aktivität können Sie den vorherigen Workflow umschreiben, in dem drei Werte hinzugefügt wurden. Dies ist im folgenden Beispiel gezeigt.  
  
```csharp  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int> {  
                Expression = new AddThreeValues() {  
                    Value1 = new InArgument<int>(a),  
                    Value2 = new InArgument<int>(b),  
                    Value3 = new InArgument<int>(c)  
                }  
            }  
        }  
    }  
};  
```  
  
 Weitere Informationen zur Verwendung von Ausdrücken im Code finden [Sie unter Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).
