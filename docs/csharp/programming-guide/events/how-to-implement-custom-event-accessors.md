---
title: "Gewusst wie: Implementieren benutzerdefinierter Ereignisaccessoren (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Accessoren [C#], Ereignisaccessor"
  - "Add-Accessor [C#]"
  - "Ereignisse [C#], Add-Accessor"
  - "Ereignisse [C#], Remove-Accessor"
  - "Remove-Accessor [C#]"
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# Gewusst wie: Implementieren benutzerdefinierter Ereignisaccessoren (C#-Programmierhandbuch)
Ein Ereignis ist ein spezieller Multicastdelegat, der nur innerhalb der Klasse aufgerufen werden kann, in der er deklariert ist.  Der Client abonniert das Ereignis, indem er einen Verweis auf eine Methode zur Verfügung stellt, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird.  Diese Methoden werden der Aufrufliste des Delegaten mithilfe von Ereignisaccessoren hinzugefügt, die Eigenschaftenaccessoren ähneln. Allerdings werden Eigenschaftenaccessoren `add` und `remove` benannt.  In der Regel müssen Sie keine benutzerdefinierten Ereignisaccessoren zur Verfügung stellen.  Wenn keine benutzerdefinierten Ereignisaccessoren im Code angegeben werden, fügt der Compiler sie automatisch hinzu.  In einigen Fällen jedoch müssen Sie möglicherweise das benutzerdefinierte Verhalten bereitstellen.  Ein entsprechendes Szenario wird im Thema [Gewusst wie: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md) veranschaulicht.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie benutzerdefinierte Ereignisaccessoren implementieren, hinzufügen und entfernen.  Sie können zwar jeden Code in den Accessoren ersetzen, es wird jedoch empfohlen, vor dem Hinzufügen oder Entfernen einer neuen Ereignishandlermethode das Ereignis zu sperren.  
  
```  
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
  
## Siehe auch  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)   
 [event](../../../csharp/language-reference/keywords/event.md)