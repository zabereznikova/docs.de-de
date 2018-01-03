---
title: Sichern der Ausnahmebehandlung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 548606a0196012fdd21bf5512e8ea7b089c723ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="securing-exception-handling"></a>Sichern der Ausnahmebehandlung
In Visual C++ und Visual Basic ein Filterausdruck weiter oben im Stapel ausgeführt wird, bevor eine **schließlich** Anweisung. Die **catch** Block zugeordnet diesen Filter ausgeführt wird, nachdem die **schließlich** Anweisung. Weitere Informationen finden Sie unter [Verwenden benutzergefilterter Ausnahmen](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md). In diesem Abschnitt werden die Auswirkungen auf die Sicherheit der angegebenen Reihenfolge. Betrachten Sie die folgenden Pseudocodebeispiel zur Veranschaulichung der Reihenfolge, in welcher filteranweisungen und **schließlich** Anweisungen ausführen.  
  
```cpp  
void Main()   
{  
    try   
    {  
        Sub();  
    }   
    except (Filter())   
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()   
{  
    try   
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }   
    finally   
    {  
        Console.WriteLine("finally");  
    }  
}                        
```  
  
 Dieser Code gibt Folgendes aus.  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 Der Filter wird ausgeführt, bevor die **schließlich** Anweisung, damit Sicherheitsprobleme nichts ergeben können, die einen Zustand zu ändern, in dem Ausführung von anderem Code nutzen kann. Zum Beispiel:  
  
```cpp  
try   
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and   
    // so on) that could be exploited if malicious   
    // code ran before state is restored.  
    Do_some_work();  
}   
finally   
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 Dieser Pseudocode ermöglicht einen Filter, die weiter oben im Stapel, beliebigen Code auszuführen. Weitere Beispiele für Vorgänge, die einen ähnlichen Effekt hätte sind temporäre Identitätswechsel von einer anderen Identität, die eine interne Flag, das einige sicherheitsüberprüfung umgeht festlegen oder Ändern der Kultur des Threads zugeordnet. Die empfohlene Lösung ist, einen Ausnahmehandler, um Änderungen des Codes zu Threadzustand von Aufrufern Filter-Blöcken zu isolieren einzuführen. Allerdings ist es wichtig, dass der Ausnahmehandler ordnungsgemäß eingeführt werden, oder wird dieses Problem nicht behoben werden. Das folgende Beispiel schaltet die Benutzeroberflächenkultur, aber jede Art von Änderung des Threads kann auf ähnliche Weise verfügbar gemacht werden.  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",   
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 Die richtige Lösung ist in diesem Fall die vorhandenen umschließen **versuchen**/**schließlich** -block in ein **versuchen**/**catch** Block. Einführung einfach in eine **Catch-Throw** Klausel in der vorhandenen **versuchen**/**schließlich** Block nicht das Problem beheben, wie im folgenden Beispiel gezeigt.  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try   
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally   
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 Wird dadurch das Problem nicht behoben, da die **schließlich** Anweisung wurde nicht ausgeführt, bevor die `FilterFunc` Ruft das Steuerelement ab.  
  
 Im folgende Beispiel wird das Problem behebt, indem Sie sicherstellen, dass die **schließlich** -Klausel wurde ausgeführt, bevor eine Ausnahme des Aufrufers Filter Ausnahmeblöcke angeboten.  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try    
    {  
        try   
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally   
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
