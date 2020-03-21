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
ms.openlocfilehash: ad27e62197f6fdaa6b5e706f4ae02c03fecae9f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181140"
---
# <a name="securing-exception-handling"></a>Sichern der Ausnahmebehandlung
In Visual C++ und Visual Basic wird ein Filterausdruck weiter oben im Stapel ausgeführt, bevor eine **abschließende** Anweisung ausgeführt wird. Der diesem Filter zugeordnete **catch-Block** wird nach der **finally-Anweisung** ausgeführt. Weitere Informationen finden Sie unter [Verwenden von benutzergefilterten Ausnahmen](../../standard/exceptions/using-user-filtered-exception-handlers.md). In diesem Abschnitt werden die Sicherheitsauswirkungen dieser Bestellung untersucht. Betrachten Sie das folgende Pseudocodebeispiel, das die Reihenfolge veranschaulicht, in der Filteranweisungen und **schließlich** Anweisungen ausgeführt werden.  
  
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
  
 Dieser Code druckt Folgendes.  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 Der Filter wird vor der **finally-Anweisung** ausgeführt, sodass Sicherheitsprobleme durch alles eingeführt werden können, was eine Zustandsänderung vornimmt, bei der die Ausführung von anderem Code vorteilen sein könnte. Beispiel:  
  
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
  
 Dieser Pseudocode ermöglicht es einem Filter höher im Stapel, beliebigen Code auszuführen. Andere Beispiele für Vorgänge, die einen ähnlichen Effekt haben würden, sind die temporäre Identitätswechsel mit einer anderen Identität, das Festlegen eines internen Flags, das eine Sicherheitsüberprüfung umgeht, oder das Ändern der dem Thread zugeordneten Kultur. Die empfohlene Lösung besteht darin, einen Ausnahmehandler einzuführen, um die Änderungen des Codes im Threadstatus von den Filterblöcken der Aufrufer zu isolieren. Es ist jedoch wichtig, dass der Ausnahmehandler ordnungsgemäß eingeführt wird, oder dieses Problem wird nicht behoben. Im folgenden Beispiel wird die UI-Kultur geändert, aber jede Art von Threadstatusänderung kann auf ähnliche Weise verfügbar gemacht werden.  
  
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
  
 Die richtige Lösung in diesem Fall ist, den **try**/vorhandenen/**Try-Finally-Block** in einem try**catch-Block** zu umschließen. **try** Die einfache Einführung einer **Catch-throw-Klausel** in den vorhandenen **try**/**Try-Finally-Block** behebt das Problem nicht, wie im folgenden Beispiel gezeigt.  
  
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
  
 Dadurch wird das Problem nicht behoben, da `FilterFunc` die **finally-Anweisung** nicht ausgeführt wurde, bevor das Steuerelement abruft.  
  
 Im folgenden Beispiel wird das Problem behoben, indem sichergestellt wird, dass die **finally-Klausel** ausgeführt wurde, bevor eine Ausnahme in den Ausnahmefilterblöcken der Aufrufer angeboten wird.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
