---
title: "Gewusst wie: Verwenden von Lambdaausdrücken außerhalb von LINQ (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 29c5d750e428e3ca6efe784cee50ca80bfd63cfd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="829ae-102">Gewusst wie: Verwenden von Lambdaausdrücken außerhalb von LINQ (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="829ae-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="829ae-103">Lambdaausdrücke sind nicht auf [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="829ae-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="829ae-104">Sie können sie überall verwenden, wo ein Delegatwert erwartet wird, also immer wenn eine anonyme Methode verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="829ae-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="829ae-105">Im folgenden Beispiel wird veranschaulicht, wie eine Lambdaausdruck in einem Windows Forms-Ereignishandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="829ae-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="829ae-106">Beachten Sie, dass die Eingabetypen (<xref:System.Object> und <xref:System.Windows.Forms.MouseEventArgs>) vom Compiler abgeleitet werden und nicht explizit in den Lambdaeingabeparametern angegeben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="829ae-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="829ae-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="829ae-107">Example</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="829ae-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="829ae-108">See Also</span></span>  
 <span data-ttu-id="829ae-109">[Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="829ae-109">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="829ae-110">[Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="829ae-110">[Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
 [<span data-ttu-id="829ae-111">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="829ae-111">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)

