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
ms.openlocfilehash: bc8cd20a4183ffd002f1399b6b50c8956208a21b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173672"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="b73d0-102">Sichern der Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="b73d0-102">Securing Exception Handling</span></span>
<span data-ttu-id="b73d0-103">In Visual C++ und Visual Basic können ein Filterausdruck weiter oben im Stapel ausgeführt wird, vor allen **schließlich** Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b73d0-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="b73d0-104">Die **catch** Block zugeordnet ist, dass der Filter ausgeführt wird, nachdem die **schließlich** Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b73d0-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="b73d0-105">Weitere Informationen finden Sie unter [Verwenden benutzergefilterter Ausnahmen](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="b73d0-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="b73d0-106">In diesem Abschnitt werden die Sicherheitsaspekte bei der angegebenen Reihenfolge untersucht.</span><span class="sxs-lookup"><span data-stu-id="b73d0-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="b73d0-107">Betrachten Sie das folgende Pseudocodebeispiel, die die Reihenfolge, in welche filteranweisungen veranschaulicht und **schließlich** Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="b73d0-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="b73d0-108">Dieser Code gibt Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="b73d0-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="b73d0-109">Der Filter ausgeführt wird, bevor die **schließlich** Anweisung, daher Sicherheitsprobleme von etwas eingeführt werden können, die einen Zustand zu ändern, wenn die Ausführung von anderem Code nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="b73d0-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="b73d0-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b73d0-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="b73d0-111">Dieser Pseudocode ermöglicht einen Filter, die weiter oben im Stapel, beliebigen Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b73d0-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="b73d0-112">Weitere Beispiele für Vorgänge, die eine ähnliche Wirkung hätte sind temporäre Identitätswechsel von einer anderen Identität, die ein internes Flag, das die umgeht einige sicherheitsüberprüfung festlegen oder Ändern der Kultur mit dem Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b73d0-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="b73d0-113">Die empfohlene Lösung ist einen Ausnahmehandler, um auf den Zustand des Threads des Codes Änderungen zu isolieren, vom Aufrufer Filter blockiert einführen.</span><span class="sxs-lookup"><span data-stu-id="b73d0-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="b73d0-114">Allerdings es ist wichtig, dass der Ausnahmehandler ordnungsgemäß eingeführt werden, oder wird dieses Problem nicht behoben werden.</span><span class="sxs-lookup"><span data-stu-id="b73d0-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="b73d0-115">Das folgende Beispiel schaltet die Kultur der Benutzeroberfläche, aber jede Art von Thread Zustandsänderung auf ähnliche Weise verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b73d0-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="b73d0-116">Die richtige Lösung in diesem Fall ist, um die vorhandene umschließen **versuchen Sie es**/**schließlich** -block in eine **versuchen**/**catch** Block.</span><span class="sxs-lookup"><span data-stu-id="b73d0-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="b73d0-117">Einführung einfach in eine **Catch-Throw** Klausel in der vorhandenen **versuchen Sie es**/**schließlich** Block nicht das Problem wird behoben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b73d0-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="b73d0-118">Dadurch wird das Problem nicht behoben, da die **schließlich** Anweisung nicht ausgeführt wurde, bevor Sie die `FilterFunc` ruft Steuerelement ab.</span><span class="sxs-lookup"><span data-stu-id="b73d0-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="b73d0-119">Im folgende Beispiel wird das Problem behebt, indem sichergestellt wird, die die **schließlich** Klausel ausgeführt wurde, bevor eine Ausnahme des Aufrufers Ausnahme Filter wird angeboten.</span><span class="sxs-lookup"><span data-stu-id="b73d0-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b73d0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b73d0-120">See also</span></span>

- [<span data-ttu-id="b73d0-121">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="b73d0-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
