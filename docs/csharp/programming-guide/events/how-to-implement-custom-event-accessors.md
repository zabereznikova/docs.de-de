---
title: 'Gewusst wie: Implementieren benutzerdefinierter Ereigniszugriffsmethoden (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 6d0181a93831fa054d7ba1a740bafe1f228bfc15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331148"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Gewusst wie: Implementieren benutzerdefinierter Ereigniszugriffsmethoden (C#-Programmierhandbuch)
Ein Ereignis ist eine besondere Art eines Multitaskdelegaten, der nur aus der Klasse , in der er deklariert ist, aufgerufen werden kann. Der Client abonniert das Ereignis durch Bereitstellen eines Verweises auf eine Methode, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird. Diese Methoden werden der Aufrufliste des Delegaten über Ereignisaccessoren hinzugefügt, die Eigenschaftenaccessoren ähneln, mit der Ausnahme, dass Ereignisaccessoren mit `add` und `remove` bezeichnet werden. In den meisten Fällen müssen Sie keine benutzerdefinierten Ereignisaccessoren angeben. Wenn keine benutzerdefinierten Ereignisaccessoren im Code angegeben werden, werden sie durch den Compiler automatisch hinzugefügt. In einigen Fällen müssen Sie möglicherweise jedoch benutzerdefiniertes Verhalten bereitstellen. Einen solchen Fall enthält das Thema [Vorgehensweise: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Implementieren von Ereignisaccessoren zum Hinzufügen und Entfernen. Obwohl Sie Code innerhalb der Accessoren ersetzen können, wird empfohlen, dass Sie das Ereignis sperren, bevor Sie eine neue Ereignishandlermethode hinzufügen oder entfernen.  
  
```csharp
event EventHandler IDrawingObject.OnDraw  
{  
    add  
    {  
        lock (PreDrawEvent)  
        {  
            PreDrawEvent += value;  
        }  
    }  
    remove  
    {  
        lock (PreDrawEvent)  
        {  
            PreDrawEvent -= value;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)  
 [event](../../../csharp/language-reference/keywords/event.md)