---
title: Verwenden von Varianz bei Delegaten (C#)
description: Hier erfahren Sie, wie Sie die Varianz in Delegaten mithilfe der enthaltenen Ko- und Kontravarianzcodebeispiele verwenden.
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 6704c3bf09dd854335f1e2719ccc8462cb7cde26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176317"
---
# <a name="using-variance-in-delegates-c"></a>Verwenden von Varianz bei Delegaten (C#)

Wenn Sie einem Delegat eine Methode zuweisen, bieten *Kovarianz* und *Kontravarianz* Flexibilität für das Abgleichen eines Delegattyps mit einer Methodensignatur. Kovarianz lässt die Verfügung einer Methode über einen Rückgabetyp zu, der stärker abgeleitet ist als der im Delegat definierte Typ. Kontravarianz lässt eine Methode zu, die über Typen verfügt, die weniger abgeleitet sind als die im Delegattyp.  
  
## <a name="example-1-covariance"></a>Beispiel 1: Kovarianz  
  
### <a name="description"></a>Beschreibung  

 In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Rückgabetypen verfügen, die von den Rückgabetypen in der Delegatsignatur abgeleitet sind. Der von `DogsHandler` zurückgegebene Datentyp ist vom Typ `Dogs`, der vom im Delegat definierten Typ `Mammals` abhängt.  
  
### <a name="code"></a>Code  
  
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
  
## <a name="example-2-contravariance"></a>Beispiel 2: Kontravarianz  
  
### <a name="description"></a>Beschreibung

In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Parameter eines Typs verfügen, die Basistypen von den Parametertypen der Delegatsignatur sind. Mithilfe von Kontravarianz können Sie einen Ereignishandler anstelle getrennter Handler verwenden. Im folgenden Beispiel werden zwei Delegaten verwendet:

- Ein <xref:System.Windows.Forms.KeyEventHandler>-Delegat, der die Signatur des Ereignisses [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) definiert. Die Signatur lautet:

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- Ein <xref:System.Windows.Forms.MouseEventHandler>-Delegat, der die Signatur des Ereignisses [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) definiert. Die Signatur lautet:

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

Das Beispiel definiert einen Ereignishandler mit einem <xref:System.EventArgs>-Parameter und verwendet diesen, um die Ereignisse `Button.KeyDown` und `Button.MouseClick` zu bearbeiten. Dies ist möglich, weil <xref:System.EventArgs> der Basistyp sowohl von <xref:System.Windows.Forms.KeyEventArgs> als auch von <xref:System.Windows.Forms.MouseEventArgs> ist.
  
### <a name="code"></a>Code  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Variance in Delegates (C#) (Varianz bei Delegaten (C#))](./variance-in-delegates.md)
- [Verwenden von Varianz für die generischen Delegaten Func und Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)
