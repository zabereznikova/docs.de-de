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
ms.openlocfilehash: e0465f2eb6be61e161f5e6b8cadf629a53f11906
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215787"
---
# <a name="securing-exception-handling"></a>Sichern der Ausnahmebehandlung
In Visual C++ und Visual Basic wird ein Filter Ausdruck, der den Stapel weiter oben aufführt, vor jeder **abschließend** -Anweisung ausgeführt. Der **catch** -Block, der diesem Filter zugeordnet ist, wird nach der **letztanweisung** ausgeführt. Weitere Informationen finden Sie unter [Verwenden von Benutzer gefilterten Ausnahmen](../../standard/exceptions/using-user-filtered-exception-handlers.md). In diesem Abschnitt werden die Sicherheitsauswirkungen dieser Bestellung erläutert. Sehen Sie sich das folgende Pseudo Codebeispiel an, das die Reihenfolge veranschaulicht, in der Filter Anweisungen und **schließlich** -Anweisungen ausgeführt werden.  
  
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
  
 Dieser Code druckt Folgendes:  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 **Der Filter wird vor der letzten** -Anweisung ausgeführt, sodass Sicherheitsprobleme von allen Änderungen verursacht werden können, die eine Zustandsänderung vornehmen, wenn die Ausführung anderer Codes ausgenutzt werden könnte. Beispiel:  
  
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
  
 Mit diesem Pseudo Code kann ein Filter höher im Stapel nach oben ausgeführt werden, um beliebigen Code auszuführen. Weitere Beispiele für Vorgänge, die einen ähnlichen Effekt haben würden, sind der temporäre Identitätswechsel einer anderen Identität, das Festlegen eines internen Flags, das eine Sicherheitsüberprüfung umgeht, oder das Ändern der dem Thread zugeordneten Kultur. Die empfohlene Lösung ist das Einführen eines Ausnahme Handlers, um die Änderungen des Codes von den Filter Blöcken der Aufrufer an den Thread Zustand zu isolieren. Es ist jedoch wichtig, dass der Ausnahmehandler ordnungsgemäß eingeführt wird oder dieses Problem nicht behoben wird. Im folgenden Beispiel wird die Benutzeroberflächen Kultur gewechselt, aber jede Art von Thread Zustandsänderung kann auf ähnliche Weise verfügbar gemacht werden.  
  
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
  
 Die korrekte Behebung in diesem Fall besteht darin, den vorhandenen **try**/-Block in einem **try**/**catch** **-Block zu** wrappen. Wenn Sie einfach eine **catch-throw-** Klausel in den vorhandenen **try** **/-** Block einführen, wird das Problem nicht behoben, wie im folgenden Beispiel gezeigt.  
  
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
  
 Dadurch wird das Problem nicht behoben, weil die letzte-Anweisung nicht ausgeführt wurde, bevor die **`FilterFunc` die Steuerung** erhält.  
  
 Im folgenden Beispiel wird das Problem behoben, indem sichergestellt wird, dass die letzte-Klausel ausgeführt wurde, **bevor die Ausnahme** Filter Blöcke der Aufrufer ausgelöst werden.  
  
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
