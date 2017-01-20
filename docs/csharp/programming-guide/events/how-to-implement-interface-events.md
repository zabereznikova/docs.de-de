---
title: "Gewusst wie: Implementieren von Schnittstellenereignissen (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ereignisse [C#], In Schnittstellen"
  - "Schnittstellen [C#], Ereignisimplementierung in Klassen"
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Implementieren von Schnittstellenereignissen (C#-Programmierhandbuch)
Eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) kann ein [Ereignis](../../../csharp/language-reference/keywords/event.md) deklarieren.  Das folgende Beispiel zeigt, wie Schnittstellenereignisse in einer Klasse implementiert werden.  Die Regeln sind mit den Regeln zum Implementieren von Schnittstellenmethoden oder \-eigenschaften weitestgehend identisch.  
  
### So implementieren Sie Schnittstellenereignisse in einer Klasse  
  
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
  
## Beispiel  
 Das folgende Beispiel zeigt die ungewöhnlichere Vorgehensweise, wenn die Klasse von zwei oder mehr Schnittstellen erbt und jede Schnittstelle über ein Ereignis mit dem gleichen Namen verfügt.  In dieser Situation müssen Sie eine explizite Schnittstellenimplementierung für mindestens eines der Ereignisse bereitstellen.  Wenn Sie eine explizite Schnittstellenimplementierung für ein Ereignis schreiben, müssen Sie auch den `add`\-Ereignisaccessor und den `remove`\-Ereignisaccessor schreiben.  Normalerweise werden diese vom Compiler bereitgestellt, was in diesem Fall jedoch nicht möglich ist.  
  
 Durch das Bereitstellen Ihrer eigenen Accessoren können Sie festlegen, ob die beiden Ereignisse durch das gleiche Ereignis oder durch verschiedene Ereignisse in der Klasse dargestellt werden sollen.  Wenn z. B. die Ereignisse gemäß den Schnittstellenspezifikationen zu unterschiedlichen Zeiten ausgelöst werden sollen, können Sie jedes Ereignis mit einer separaten Implementierung in der Klasse verknüpfen.  Im folgenden Beispiel bestimmen Abonnenten, welches `OnDraw`\-Ereignis sie erhalten, indem Sie den Formverweis entweder in eine `IShape` oder ein `IDrawingObject` umwandeln.  
  
 [!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Explizite Schnittstellenimplementierung](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)   
 [Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)