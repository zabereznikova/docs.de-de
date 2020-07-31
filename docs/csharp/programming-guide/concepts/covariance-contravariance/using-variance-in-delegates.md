---
title: Verwenden von Varianz bei Delegaten (C#)
description: Hier erfahren Sie, wie Sie die Varianz in Delegaten mithilfe der enthaltenen Ko- und Kontravarianzcodebeispiele verwenden.
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 62b0555ee29c5e7d2ba0954a8949d61596122cc7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105689"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="d42ed-103">Verwenden von Varianz bei Delegaten (C#)</span><span class="sxs-lookup"><span data-stu-id="d42ed-103">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="d42ed-104">Wenn Sie einem Delegat eine Methode zuweisen, bieten *Kovarianz* und *Kontravarianz* Flexibilität für das Abgleichen eines Delegattyps mit einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="d42ed-104">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="d42ed-105">Kovarianz lässt die Verfügung einer Methode über einen Rückgabetyp zu, der stärker abgeleitet ist als der im Delegat definierte Typ.</span><span class="sxs-lookup"><span data-stu-id="d42ed-105">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="d42ed-106">Kontravarianz lässt eine Methode zu, die über Typen verfügt, die weniger abgeleitet sind als die im Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="d42ed-106">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="d42ed-107">Beispiel 1: Kovarianz</span><span class="sxs-lookup"><span data-stu-id="d42ed-107">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="d42ed-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d42ed-108">Description</span></span>  
 <span data-ttu-id="d42ed-109">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Rückgabetypen verfügen, die von den Rückgabetypen in der Delegatsignatur abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="d42ed-109">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="d42ed-110">Der von `DogsHandler` zurückgegebene Datentyp ist vom Typ `Dogs`, der vom im Delegat definierten Typ `Mammals` abhängt.</span><span class="sxs-lookup"><span data-stu-id="d42ed-110">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d42ed-111">Code</span><span class="sxs-lookup"><span data-stu-id="d42ed-111">Code</span></span>  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="d42ed-112">Beispiel 2: Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="d42ed-112">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="d42ed-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d42ed-113">Description</span></span>

<span data-ttu-id="d42ed-114">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Parameter eines Typs verfügen, die Basistypen von den Parametertypen der Delegatsignatur sind.</span><span class="sxs-lookup"><span data-stu-id="d42ed-114">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="d42ed-115">Mithilfe von Kontravarianz können Sie einen Ereignishandler anstelle getrennter Handler verwenden.</span><span class="sxs-lookup"><span data-stu-id="d42ed-115">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="d42ed-116">Im folgenden Beispiel werden zwei Delegaten verwendet:</span><span class="sxs-lookup"><span data-stu-id="d42ed-116">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="d42ed-117">Ein <xref:System.Windows.Forms.KeyEventHandler>-Delegat, der die Signatur des Ereignisses [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) definiert.</span><span class="sxs-lookup"><span data-stu-id="d42ed-117">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="d42ed-118">Die Signatur lautet:</span><span class="sxs-lookup"><span data-stu-id="d42ed-118">Its signature is:</span></span>

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- <span data-ttu-id="d42ed-119">Ein <xref:System.Windows.Forms.MouseEventHandler>-Delegat, der die Signatur des Ereignisses [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) definiert.</span><span class="sxs-lookup"><span data-stu-id="d42ed-119">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="d42ed-120">Die Signatur lautet:</span><span class="sxs-lookup"><span data-stu-id="d42ed-120">Its signature is:</span></span>

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

<span data-ttu-id="d42ed-121">Das Beispiel definiert einen Ereignishandler mit einem <xref:System.EventArgs>-Parameter und verwendet diesen, um die Ereignisse `Button.KeyDown` und `Button.MouseClick` zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d42ed-121">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="d42ed-122">Dies ist möglich, weil <xref:System.EventArgs> der Basistyp sowohl von <xref:System.Windows.Forms.KeyEventArgs> als auch von <xref:System.Windows.Forms.MouseEventArgs> ist.</span><span class="sxs-lookup"><span data-stu-id="d42ed-122">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>
  
### <a name="code"></a><span data-ttu-id="d42ed-123">Code</span><span class="sxs-lookup"><span data-stu-id="d42ed-123">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d42ed-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d42ed-124">See also</span></span>

- [<span data-ttu-id="d42ed-125">Variance in Delegates (C#) (Varianz bei Delegaten (C#))</span><span class="sxs-lookup"><span data-stu-id="d42ed-125">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="d42ed-126">Verwenden von Varianz für die generischen Delegaten Func und Action (C#)</span><span class="sxs-lookup"><span data-stu-id="d42ed-126">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
