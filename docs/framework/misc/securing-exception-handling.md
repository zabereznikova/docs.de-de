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
# <a name="securing-exception-handling"></a><span data-ttu-id="1c6f8-102">Sichern der Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="1c6f8-102">Securing Exception Handling</span></span>
<span data-ttu-id="1c6f8-103">In Visual C++ und Visual Basic wird ein Filter Ausdruck, der den Stapel weiter oben aufführt, vor jeder **abschließend** -Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="1c6f8-104">Der **catch** -Block, der diesem Filter zugeordnet ist, wird nach der **letztanweisung** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="1c6f8-105">Weitere Informationen finden Sie unter [Verwenden von Benutzer gefilterten Ausnahmen](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="1c6f8-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="1c6f8-106">In diesem Abschnitt werden die Sicherheitsauswirkungen dieser Bestellung erläutert.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="1c6f8-107">Sehen Sie sich das folgende Pseudo Codebeispiel an, das die Reihenfolge veranschaulicht, in der Filter Anweisungen und **schließlich** -Anweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="1c6f8-108">Dieser Code druckt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1c6f8-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="1c6f8-109">**Der Filter wird vor der letzten** -Anweisung ausgeführt, sodass Sicherheitsprobleme von allen Änderungen verursacht werden können, die eine Zustandsänderung vornehmen, wenn die Ausführung anderer Codes ausgenutzt werden könnte.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="1c6f8-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1c6f8-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="1c6f8-111">Mit diesem Pseudo Code kann ein Filter höher im Stapel nach oben ausgeführt werden, um beliebigen Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="1c6f8-112">Weitere Beispiele für Vorgänge, die einen ähnlichen Effekt haben würden, sind der temporäre Identitätswechsel einer anderen Identität, das Festlegen eines internen Flags, das eine Sicherheitsüberprüfung umgeht, oder das Ändern der dem Thread zugeordneten Kultur.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="1c6f8-113">Die empfohlene Lösung ist das Einführen eines Ausnahme Handlers, um die Änderungen des Codes von den Filter Blöcken der Aufrufer an den Thread Zustand zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="1c6f8-114">Es ist jedoch wichtig, dass der Ausnahmehandler ordnungsgemäß eingeführt wird oder dieses Problem nicht behoben wird.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="1c6f8-115">Im folgenden Beispiel wird die Benutzeroberflächen Kultur gewechselt, aber jede Art von Thread Zustandsänderung kann auf ähnliche Weise verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="1c6f8-116">Die korrekte Behebung in diesem Fall besteht darin, den vorhandenen **try**/-Block in einem **try**/**catch** **-Block zu** wrappen.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="1c6f8-117">Wenn Sie einfach eine **catch-throw-** Klausel in den vorhandenen **try** **/-** Block einführen, wird das Problem nicht behoben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="1c6f8-118">Dadurch wird das Problem nicht behoben, weil die letzte-Anweisung nicht ausgeführt wurde, bevor die **`FilterFunc` die Steuerung** erhält.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="1c6f8-119">Im folgenden Beispiel wird das Problem behoben, indem sichergestellt wird, dass die letzte-Klausel ausgeführt wurde, **bevor die Ausnahme** Filter Blöcke der Aufrufer ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="1c6f8-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1c6f8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c6f8-120">See also</span></span>

- [<span data-ttu-id="1c6f8-121">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="1c6f8-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
