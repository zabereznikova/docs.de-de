---
title: 'Gewusst wie: Implementieren von Schnittstellenereignissen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 5f6dc5d9c0b901db485028159a2872f7db2f363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="04fcc-102">Gewusst wie: Implementieren von Schnittstellenereignissen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="04fcc-102">How to: Implement Interface Events (C# Programming Guide)</span></span>
<span data-ttu-id="04fcc-103">Eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) kann ein [Ereignis](../../../csharp/language-reference/keywords/event.md) deklarieren.</span><span class="sxs-lookup"><span data-stu-id="04fcc-103">An [interface](../../../csharp/language-reference/keywords/interface.md) can declare an [event](../../../csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="04fcc-104">Das folgende Beispiel zeigt, wie Schnittstellenereignisse in einer Klasse implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="04fcc-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="04fcc-105">Die Regeln sind mit den Regeln zum Implementieren von Schnittstellenmethoden oder -eigenschaften weitestgehend identisch.</span><span class="sxs-lookup"><span data-stu-id="04fcc-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
### <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="04fcc-106">So implementieren Sie Schnittstellenereignisse in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="04fcc-106">To implement interface events in a class</span></span>  
  
-   <span data-ttu-id="04fcc-107">Deklarieren Sie das Ereignis in der Klasse, und rufen Sie es dann an den entsprechenden Stellen auf.</span><span class="sxs-lookup"><span data-stu-id="04fcc-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
    ```csharp
    namespace ImplementInterfaceEvents  
    {  
        public interface IDrawingObject  
        {  
            event EventHandler ShapeChanged;  
        }  
        public class MyEventArgs : EventArgs   
        {  
            // class members  
        }  
        public class Shape : IDrawingObject  
        {  
            public event EventHandler ShapeChanged;  
            void ChangeShape()  
            {  
                // Do something here before the event…  
  
                OnShapeChanged(new MyEventArgs(/*arguments*/));  
  
                // or do something here after the event.   
            }  
            protected virtual void OnShapeChanged(MyEventArgs e)  
            {  
                if(ShapeChanged != null)  
                {  
                   ShapeChanged(this, e);  
                }  
            }  
        }  
  
    }  
    ```  
  
## <a name="example"></a><span data-ttu-id="04fcc-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04fcc-108">Example</span></span>  
 <span data-ttu-id="04fcc-109">Das folgende Beispiel zeigt die ungewöhnlichere Vorgehensweise, wenn die Klasse von zwei oder mehr Schnittstellen erbt und jede Schnittstelle über ein Ereignis mit dem gleichen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="04fcc-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="04fcc-110">In dieser Situation müssen Sie eine explizite Schnittstellenimplementierung für mindestens eines der Ereignisse bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="04fcc-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="04fcc-111">Wenn Sie eine explizite Schnittstellenimplementierung für ein Ereignis schreiben, müssen Sie auch den `add`-Ereignisaccessor und den `remove`-Ereignisaccessor schreiben.</span><span class="sxs-lookup"><span data-stu-id="04fcc-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="04fcc-112">Normalerweise werden diese vom Compiler bereitgestellt, was in diesem Fall jedoch nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="04fcc-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
 <span data-ttu-id="04fcc-113">Durch das Bereitstellen Ihrer eigenen Accessoren können Sie festlegen, ob die beiden Ereignisse durch das gleiche Ereignis oder durch verschiedene Ereignisse in der Klasse dargestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="04fcc-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="04fcc-114">Wenn z. B. die Ereignisse gemäß den Schnittstellenspezifikationen zu unterschiedlichen Zeiten ausgelöst werden sollen, können Sie jedes Ereignis einer separaten Implementierung in der Klasse zuordnen.</span><span class="sxs-lookup"><span data-stu-id="04fcc-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="04fcc-115">Im folgenden Beispiel bestimmen Abonnenten, welches `OnDraw`-Ereignis sie erhalten, indem sie den Formverweis entweder in eine `IShape` oder ein `IDrawingObject` umwandeln.</span><span class="sxs-lookup"><span data-stu-id="04fcc-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="04fcc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04fcc-116">See Also</span></span>  
 [<span data-ttu-id="04fcc-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="04fcc-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="04fcc-118">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="04fcc-118">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="04fcc-119">Delegaten</span><span class="sxs-lookup"><span data-stu-id="04fcc-119">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="04fcc-120">Explizite Schnittstellenimplementierung</span><span class="sxs-lookup"><span data-stu-id="04fcc-120">Explicit Interface Implementation</span></span>](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 [<span data-ttu-id="04fcc-121">Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="04fcc-121">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
