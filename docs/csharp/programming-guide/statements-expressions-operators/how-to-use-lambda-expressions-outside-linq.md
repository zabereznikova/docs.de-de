---
title: 'Vorgehensweise: Verwenden von Lambdaausdrücken außerhalb von LINQ – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: 947f80fdaa90b6b5f8176aac01dd8e3cf40e38cc
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363772"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a>Vorgehensweise: Verwenden von Lambdaausdrücken außerhalb von LINQ (C#-Programmierhandbuch)
Lambdaausdrücke sind nicht auf [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen beschränkt. Sie können sie überall verwenden, wo ein Delegatwert erwartet wird, also immer wenn eine anonyme Methode verwendet werden kann. Im folgenden Beispiel wird veranschaulicht, wie eine Lambdaausdruck in einem Windows Forms-Ereignishandler verwendet wird. Beachten Sie, dass die Eingabetypen (<xref:System.Object> und <xref:System.Windows.Forms.MouseEventArgs>) vom Compiler abgeleitet werden und nicht explizit in den Lambdaeingabeparametern angegeben werden müssen.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Lambda-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [LINQ (Language-Integrated Query)](../../../csharp/programming-guide/concepts/linq/index.md)
