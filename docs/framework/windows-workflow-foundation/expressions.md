---
title: Expressions1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 293e59bd53607b7ca4c3d9075cb4bb0c4be4d4da
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="expressions"></a><span data-ttu-id="7d2ce-102">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7d2ce-102">Expressions</span></span>
<span data-ttu-id="7d2ce-103">Ein Windows Workflow Foundation (WF)-Ausdruck ist Aktivität, die ein Ergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-103">A Windows Workflow Foundation (WF) expression is any activity that returns a result.</span></span> <span data-ttu-id="7d2ce-104">Alle Ausdrucksaktivitäten werden indirekt von <xref:System.Activities.Activity%601> abgeleitet, die eine <xref:System.Activities.OutArgument>-Eigenschaft mit dem Namen <xref:System.Activities.Activity%601.Result%2A> als Rückgabewert der Aktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-104">All expression activities derive indirectly from <xref:System.Activities.Activity%601>, which contains an <xref:System.Activities.OutArgument> property named <xref:System.Activities.Activity%601.Result%2A> as the activity’s return value.</span></span> <span data-ttu-id="7d2ce-105">Im Lieferumfang von [!INCLUDE[wf1](../../../includes/wf1-md.md)] ist eine Vielzahl von Ausdrucksaktivitäten enthalten, darunter einfache Ausdrucksaktivitäten wie <xref:System.Activities.Expressions.VariableValue%601> und <xref:System.Activities.Expressions.VariableReference%601>, die den Zugriff auf einzelne Workflowvariablen über Operatoraktivitäten ermöglichen, sowie komplexe Aktivitäten wie <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> und <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>, die zum Erzielen des gewünschten Ergebnisses den Zugriff auf die volle Bandbreite der Visual Basic-Programmiersprache ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-105">[!INCLUDE[wf1](../../../includes/wf1-md.md)] ships with a wide range of expression activities from simple ones like <xref:System.Activities.Expressions.VariableValue%601> and <xref:System.Activities.Expressions.VariableReference%601>, which provide access to single workflow variable through operator activities, to complex activities such as <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> that offer access to the full breadth of Visual Basic language to produce the result.</span></span> <span data-ttu-id="7d2ce-106">Zusätzliche Ausdrucksaktivitäten können durch Ableitungen von <xref:System.Activities.CodeActivity%601> oder <xref:System.Activities.NativeActivity%601> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-106">Additional expression activities can be created by deriving from <xref:System.Activities.CodeActivity%601> or <xref:System.Activities.NativeActivity%601>.</span></span>  
  
## <a name="using-expressions"></a><span data-ttu-id="7d2ce-107">Verwenden von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="7d2ce-107">Using Expressions</span></span>  
 <span data-ttu-id="7d2ce-108">Workflow-Designer verwendet <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> und <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> für alle Ausdrücke in Visual Basic-Projekten sowie <xref:Microsoft.CSharp.Activities.CSharpValue%601> und <xref:Microsoft.CSharp.Activities.CSharpReference%601> für Ausdrücke in den C#-Workflowprojekten.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-108">Workflow designer uses <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> for all expressions in Visual Basic projects, and <xref:Microsoft.CSharp.Activities.CSharpValue%601> and <xref:Microsoft.CSharp.Activities.CSharpReference%601> for expressions in C# workflow projects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d2ce-109">Unterstützung für C#-Ausdrücke in Workflowprojekten wurde mit [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-109">Support for C# expressions in workflow projects was introduced in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7d2ce-110"> [C#-Ausdrücke](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7d2ce-110"> [C# Expressions](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).</span></span>  
  
 <span data-ttu-id="7d2ce-111">Vom Designer erzeugte Workflows werden im XAML-Format gespeichert, bei dem Ausdrücke in eckige Klammern eingeschlossen sind. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-111">Workflows produced by designer are saved in XAML, where expressions appear enclosed in square brackets, as in the following example.</span></span>  
  
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
  
 <span data-ttu-id="7d2ce-112">Sie können beim Definieren eines Workflows im Code beliebige Ausdrucksaktivitäten verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-112">When defining a workflow in code, any expression activities can be used.</span></span> <span data-ttu-id="7d2ce-113">Im folgenden Beispiel wird die Verwendung von Operatoraktivitäten zum Hinzufügen von drei Zahlen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-113">The following example shows the usage of a composition of operator activities to add three numbers.</span></span>  
  
```  
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
  
 <span data-ttu-id="7d2ce-114">Der gleiche Workflow kann auch kürzer ausgedrückt werden, indem C#-Lambda-Ausdrücke verwendet werden. Dies ist im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-114">The same workflow can be expressed more compactly by using C# lambda expressions, as shown in the following example.</span></span>  
  
```  
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
  
 <span data-ttu-id="7d2ce-115">Außerdem können Sie den Workflow mithilfe von Visual Basic-Ausdrucksaktivitäten ausdrücken, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-115">The workflow can also be expressed by using Visual Basic expression activities, as shown in the following example.</span></span>  
  
```  
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
  
## <a name="extending-available-expressions-with-custom-expression-activities"></a><span data-ttu-id="7d2ce-116">Erweitern von verfügbaren Ausdrücken mit benutzerdefinierten Ausdrucksaktivitäten</span><span class="sxs-lookup"><span data-stu-id="7d2ce-116">Extending Available Expressions with Custom Expression Activities</span></span>  
 <span data-ttu-id="7d2ce-117">Ausdrücke in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] sind erweiterbar und ermöglichen das Erstellen zusätzlicher Ausdrucksaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-117">Expressions in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are extensible allowing for additional expression activities to be created.</span></span> <span data-ttu-id="7d2ce-118">Das folgende Beispiel zeigt eine Aktivität, die eine Summe aus drei ganzzahligen Werten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-118">The following example shows an activity that returns a sum of three integer values.</span></span>  
  
```  
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
  
 <span data-ttu-id="7d2ce-119">Mit dieser neuen Aktivität können Sie den vorherigen Workflow umschreiben, in dem drei Werte hinzugefügt wurden. Dies ist im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d2ce-119">With this new activity you can rewrite the previous workflow that added three values as shown in the following example.</span></span>  
  
```  
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
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7d2ce-120"> Mithilfe von Ausdrücken im Code finden Sie unter [Entwickeln von Workflows, Aktivitäten und Ausdrücken mithilfe von imperativem Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="7d2ce-120"> using expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>
