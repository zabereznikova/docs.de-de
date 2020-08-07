---
title: 'Vorgehensweise: Implementieren von Schnittstellenereignissen (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Schnittstellenereignisse in einer Klasse implementieren. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: bd86aed4f8d8ac6e291c11fe441f87ac97593b03
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302125"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="f7cab-104">Vorgehensweise: Implementieren von Schnittstellenereignissen (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="f7cab-104">How to implement interface events (C# Programming Guide)</span></span>
<span data-ttu-id="f7cab-105">Eine [Schnittstelle](../../language-reference/keywords/interface.md) kann ein [Ereignis](../../language-reference/keywords/event.md) deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f7cab-105">An [interface](../../language-reference/keywords/interface.md) can declare an [event](../../language-reference/keywords/event.md).</span></span> <span data-ttu-id="f7cab-106">Das folgende Beispiel zeigt, wie Schnittstellenereignisse in einer Klasse implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f7cab-106">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="f7cab-107">Die Regeln sind mit den Regeln zum Implementieren von Schnittstellenmethoden oder -eigenschaften weitestgehend identisch.</span><span class="sxs-lookup"><span data-stu-id="f7cab-107">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="f7cab-108">So implementieren Sie Schnittstellenereignisse in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="f7cab-108">To implement interface events in a class</span></span>  
  
<span data-ttu-id="f7cab-109">Deklarieren Sie das Ereignis in der Klasse, und rufen Sie es dann an den entsprechenden Stellen auf.</span><span class="sxs-lookup"><span data-stu-id="f7cab-109">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
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
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a><span data-ttu-id="f7cab-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7cab-110">Example</span></span>  
<span data-ttu-id="f7cab-111">Das folgende Beispiel zeigt die ungewöhnlichere Vorgehensweise, wenn die Klasse von zwei oder mehr Schnittstellen erbt und jede Schnittstelle über ein Ereignis mit dem gleichen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="f7cab-111">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="f7cab-112">In dieser Situation müssen Sie eine explizite Schnittstellenimplementierung für mindestens eines der Ereignisse bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f7cab-112">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="f7cab-113">Wenn Sie eine explizite Schnittstellenimplementierung für ein Ereignis schreiben, müssen Sie auch den `add`-Ereignisaccessor und den `remove`-Ereignisaccessor schreiben.</span><span class="sxs-lookup"><span data-stu-id="f7cab-113">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="f7cab-114">Normalerweise werden diese vom Compiler bereitgestellt, was in diesem Fall jedoch nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="f7cab-114">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="f7cab-115">Durch das Bereitstellen Ihrer eigenen Accessoren können Sie festlegen, ob die beiden Ereignisse durch das gleiche Ereignis oder durch verschiedene Ereignisse in der Klasse dargestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7cab-115">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="f7cab-116">Wenn z. B. die Ereignisse gemäß den Schnittstellenspezifikationen zu unterschiedlichen Zeiten ausgelöst werden sollen, können Sie jedes Ereignis einer separaten Implementierung in der Klasse zuordnen.</span><span class="sxs-lookup"><span data-stu-id="f7cab-116">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="f7cab-117">Im folgenden Beispiel bestimmen Abonnenten, welches `OnDraw`-Ereignis sie erhalten, indem sie den Formverweis entweder in eine `IShape` oder ein `IDrawingObject` umwandeln.</span><span class="sxs-lookup"><span data-stu-id="f7cab-117">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="f7cab-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7cab-118">See also</span></span>

- [<span data-ttu-id="f7cab-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f7cab-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f7cab-120">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f7cab-120">Events</span></span>](./index.md)
- [<span data-ttu-id="f7cab-121">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f7cab-121">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="f7cab-122">Explizite Schnittstellenimplementierung</span><span class="sxs-lookup"><span data-stu-id="f7cab-122">Explicit Interface Implementation</span></span>](../interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="f7cab-123">Auslösen von Basisklassenereignissen in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="f7cab-123">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)
