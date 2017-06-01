---
title: 'Gewusst wie: Implementieren von Schnittstellenereignissen (C#-Programmierhandbuch) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: 21
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: 4a5b5b862a88d7008049e411e6dc0f020952cc5c
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Gewusst wie: Implementieren von Schnittstellenereignissen (C#-Programmierhandbuch)
Eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) kann ein [Ereignis](../../../csharp/language-reference/keywords/event.md) deklarieren. Das folgende Beispiel zeigt, wie Schnittstellenereignisse in einer Klasse implementiert werden. Die Regeln sind mit den Regeln zum Implementieren von Schnittstellenmethoden oder -eigenschaften weitestgehend identisch.  
  
### <a name="to-implement-interface-events-in-a-class"></a>So implementieren Sie Schnittstellenereignisse in einer Klasse  
  
-   Deklarieren Sie das Ereignis in der Klasse, und rufen Sie es dann an den entsprechenden Stellen auf.  
  
    ```  
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
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die ungewöhnlichere Vorgehensweise, wenn die Klasse von zwei oder mehr Schnittstellen erbt und jede Schnittstelle über ein Ereignis mit dem gleichen Namen verfügt. In dieser Situation müssen Sie eine explizite Schnittstellenimplementierung für mindestens eines der Ereignisse bereitstellen. Wenn Sie eine explizite Schnittstellenimplementierung für ein Ereignis schreiben, müssen Sie auch den `add`-Ereignisaccessor und den `remove`-Ereignisaccessor schreiben. Normalerweise werden diese vom Compiler bereitgestellt, was in diesem Fall jedoch nicht möglich ist.  
  
 Durch das Bereitstellen Ihrer eigenen Accessoren können Sie festlegen, ob die beiden Ereignisse durch das gleiche Ereignis oder durch verschiedene Ereignisse in der Klasse dargestellt werden sollen. Wenn z. B. die Ereignisse gemäß den Schnittstellenspezifikationen zu unterschiedlichen Zeiten ausgelöst werden sollen, können Sie jedes Ereignis einer separaten Implementierung in der Klasse zuordnen. Im folgenden Beispiel bestimmen Abonnenten, welches `OnDraw`-Ereignis sie erhalten, indem sie den Formverweis entweder in eine `IShape` oder ein `IDrawingObject` umwandeln.  
  
 [!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Explizite Schnittstellenimplementierung](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)   
 [Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
