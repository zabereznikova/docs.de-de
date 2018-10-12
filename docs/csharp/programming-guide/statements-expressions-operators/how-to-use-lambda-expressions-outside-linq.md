---
title: 'Gewusst wie: Verwenden von Lambdaausdrücken außerhalb von LINQ (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: eb9fea64b8aeb96a880b7e177673c1316b7aa4c1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261530"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="8d892-102">Gewusst wie: Verwenden von Lambdaausdrücken außerhalb von LINQ (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8d892-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="8d892-103">Lambdaausdrücke sind nicht auf [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8d892-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="8d892-104">Sie können sie überall verwenden, wo ein Delegatwert erwartet wird, also immer wenn eine anonyme Methode verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d892-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="8d892-105">Im folgenden Beispiel wird veranschaulicht, wie eine Lambdaausdruck in einem Windows Forms-Ereignishandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d892-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="8d892-106">Beachten Sie, dass die Eingabetypen (<xref:System.Object> und <xref:System.Windows.Forms.MouseEventArgs>) vom Compiler abgeleitet werden und nicht explizit in den Lambdaeingabeparametern angegeben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8d892-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d892-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d892-107">Example</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
       this.Click += (s, e) => { MessageBox.Show(((MouseEventArgs)e).Location.ToString());};  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d892-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d892-108">See Also</span></span>

- [<span data-ttu-id="8d892-109">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8d892-109">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [<span data-ttu-id="8d892-110">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="8d892-110">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [<span data-ttu-id="8d892-111">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="8d892-111">Language Integrated Query (LINQ))</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
