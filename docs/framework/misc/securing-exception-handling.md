---
title: Sichern der Ausnahmebehandlung
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c406edcef393d3c2b9e4cf6dbeee9d572c0951f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679382"
---
# <a name="securing-exception-handling"></a>Sichern der Ausnahmebehandlung
In Visual C++ und Visual Basic können ein Filterausdruck weiter oben im Stapel ausgeführt wird, vor allen **schließlich** Anweisung. Die **catch** Block zugeordnet ist, dass der Filter ausgeführt wird, nachdem die **schließlich** Anweisung. Weitere Informationen finden Sie unter [Verwenden benutzergefilterter Ausnahmen](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md). In diesem Abschnitt werden die Sicherheitsaspekte bei der angegebenen Reihenfolge untersucht. Betrachten Sie das folgende Pseudocodebeispiel, die die Reihenfolge, in welche filteranweisungen veranschaulicht und **schließlich** Anweisungen ausführen.  
  
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
  
 Der Filter ausgeführt wird, bevor die **schließlich** Anweisung, daher Sicherheitsprobleme von etwas eingeführt werden können, die einen Zustand zu ändern, wenn die Ausführung von anderem Code nutzen kann. Zum Beispiel:  
  
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
  
 Dieser Pseudocode ermöglicht einen Filter, die weiter oben im Stapel, beliebigen Code auszuführen. Weitere Beispiele für Vorgänge, die eine ähnliche Wirkung hätte sind temporäre Identitätswechsel von einer anderen Identität, die ein internes Flag, das die umgeht einige sicherheitsüberprüfung festlegen oder Ändern der Kultur mit dem Thread zugeordnet. Die empfohlene Lösung ist einen Ausnahmehandler, um auf den Zustand des Threads des Codes Änderungen zu isolieren, vom Aufrufer Filter blockiert einführen. Allerdings es ist wichtig, dass der Ausnahmehandler ordnungsgemäß eingeführt werden, oder wird dieses Problem nicht behoben werden. Das folgende Beispiel schaltet die Kultur der Benutzeroberfläche, aber jede Art von Thread Zustandsänderung auf ähnliche Weise verfügbar gemacht werden.  
  
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
  
 Die richtige Lösung in diesem Fall ist, um die vorhandene umschließen **versuchen Sie es**/**schließlich** -block in eine **versuchen**/**catch** Block. Einführung einfach in eine **Catch-Throw** Klausel in der vorhandenen **versuchen Sie es**/**schließlich** Block nicht das Problem wird behoben, wie im folgenden Beispiel gezeigt.  
  
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
  
 Dadurch wird das Problem nicht behoben, da die **schließlich** Anweisung nicht ausgeführt wurde, bevor Sie die `FilterFunc` ruft Steuerelement ab.  
  
 Im folgende Beispiel wird das Problem behebt, indem sichergestellt wird, die die **schließlich** Klausel ausgeführt wurde, bevor eine Ausnahme des Aufrufers Ausnahme Filter wird angeboten.  
  
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
- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
