---
title: Verwenden von Varianz bei Delegaten (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 9f2128080d34e78733cec926e59ee5dbe9b98a0d
ms.openlocfilehash: 83bef688a9d40c08f7a8280309ea5b607a9b06f0
ms.contentlocale: de-de
ms.lasthandoff: 08/07/2017

---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="86355-102">Verwenden von Varianz bei Delegaten (C#)</span><span class="sxs-lookup"><span data-stu-id="86355-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="86355-103">Wenn Sie einem Delegat eine Methode zuweisen, bieten *Kovarianz* und *Kontravarianz* Flexibilität für das Abgleichen eines Delegattyps mit einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="86355-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="86355-104">Kovarianz lässt die Verfügung einer Methode über einen Rückgabetyp zu, der stärker abgeleitet ist als der im Delegat definierte Typ.</span><span class="sxs-lookup"><span data-stu-id="86355-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="86355-105">Kontravarianz lässt eine Methode zu, die über Typen verfügt, die weniger abgeleitet sind als die im Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="86355-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="86355-106">Beispiel 1: Kovarianz</span><span class="sxs-lookup"><span data-stu-id="86355-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="86355-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86355-107">Description</span></span>  
 <span data-ttu-id="86355-108">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Rückgabetypen verfügen, die von den Rückgabetypen in der Delegatsignatur abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="86355-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="86355-109">Der von `DogsHandler` zurückgegebene Datentyp ist vom Typ `Dogs`, der vom im Delegat definierten Typ `Mammals` abhängt.</span><span class="sxs-lookup"><span data-stu-id="86355-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="86355-110">Code</span><span class="sxs-lookup"><span data-stu-id="86355-110">Code</span></span>  
  
```csharp  
class Mammals{}  
class Dogs : Mammals{}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="86355-111">Beispiel 2: Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="86355-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="86355-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86355-112">Description</span></span>  
 <span data-ttu-id="86355-113">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Parameter eines Typs verfügen, die Basistypen von den Parametertypen in der Delegatsignatur sind.</span><span class="sxs-lookup"><span data-stu-id="86355-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="86355-114">Mithilfe von Kontravarianz können Sie einen Ereignishandler anstelle getrennter Handler verwenden.</span><span class="sxs-lookup"><span data-stu-id="86355-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="86355-115">Sie können zum Beispiel einen Ereignishandler erstellen, der einen `EventArgs`-Eingabeparameter annimmt und mit einem `Button.MouseClick`-Ereignis verwendet, das einen Typ `MouseEventArgs` als Parameter sendet. Außerdem können Sie ihn mit einem `TextBox.KeyDown`-Ereignis verwenden, das einen `KeyEventArgs`-Parameter sendet.</span><span class="sxs-lookup"><span data-stu-id="86355-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="86355-116">Code</span><span class="sxs-lookup"><span data-stu-id="86355-116">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method   
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="86355-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86355-117">See Also</span></span>  
 <span data-ttu-id="86355-118">[Variance in Delegates (C#) (Varianz bei Delegaten (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="86355-118">[Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span></span>  
 [<span data-ttu-id="86355-119">Using Variance for Func and Action Generic Delegates C# (Verwenden von Varianz für die generischen Delegaten Func und Action (C#))</span><span class="sxs-lookup"><span data-stu-id="86355-119">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)

