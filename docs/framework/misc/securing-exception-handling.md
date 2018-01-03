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
# <a name="securing-exception-handling"></a><span data-ttu-id="90b4e-102">Sichern der Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="90b4e-102">Securing Exception Handling</span></span>
<span data-ttu-id="90b4e-103">In Visual C++ und Visual Basic ein Filterausdruck weiter oben im Stapel ausgeführt wird, bevor eine **schließlich** Anweisung.</span><span class="sxs-lookup"><span data-stu-id="90b4e-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="90b4e-104">Die **catch** Block zugeordnet diesen Filter ausgeführt wird, nachdem die **schließlich** Anweisung.</span><span class="sxs-lookup"><span data-stu-id="90b4e-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="90b4e-105">Weitere Informationen finden Sie unter [Verwenden benutzergefilterter Ausnahmen](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="90b4e-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="90b4e-106">In diesem Abschnitt werden die Auswirkungen auf die Sicherheit der angegebenen Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="90b4e-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="90b4e-107">Betrachten Sie die folgenden Pseudocodebeispiel zur Veranschaulichung der Reihenfolge, in welcher filteranweisungen und **schließlich** Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="90b4e-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="90b4e-108">Dieser Code gibt Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="90b4e-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="90b4e-109">Der Filter wird ausgeführt, bevor die **schließlich** Anweisung, damit Sicherheitsprobleme nichts ergeben können, die einen Zustand zu ändern, in dem Ausführung von anderem Code nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="90b4e-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="90b4e-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="90b4e-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="90b4e-111">Dieser Pseudocode ermöglicht einen Filter, die weiter oben im Stapel, beliebigen Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="90b4e-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="90b4e-112">Weitere Beispiele für Vorgänge, die einen ähnlichen Effekt hätte sind temporäre Identitätswechsel von einer anderen Identität, die eine interne Flag, das einige sicherheitsüberprüfung umgeht festlegen oder Ändern der Kultur des Threads zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="90b4e-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="90b4e-113">Die empfohlene Lösung ist, einen Ausnahmehandler, um Änderungen des Codes zu Threadzustand von Aufrufern Filter-Blöcken zu isolieren einzuführen.</span><span class="sxs-lookup"><span data-stu-id="90b4e-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="90b4e-114">Allerdings ist es wichtig, dass der Ausnahmehandler ordnungsgemäß eingeführt werden, oder wird dieses Problem nicht behoben werden.</span><span class="sxs-lookup"><span data-stu-id="90b4e-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="90b4e-115">Das folgende Beispiel schaltet die Benutzeroberflächenkultur, aber jede Art von Änderung des Threads kann auf ähnliche Weise verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="90b4e-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="90b4e-116">Die richtige Lösung ist in diesem Fall die vorhandenen umschließen **versuchen**/**schließlich** -block in ein **versuchen**/**catch** Block.</span><span class="sxs-lookup"><span data-stu-id="90b4e-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="90b4e-117">Einführung einfach in eine **Catch-Throw** Klausel in der vorhandenen **versuchen**/**schließlich** Block nicht das Problem beheben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90b4e-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="90b4e-118">Wird dadurch das Problem nicht behoben, da die **schließlich** Anweisung wurde nicht ausgeführt, bevor die `FilterFunc` Ruft das Steuerelement ab.</span><span class="sxs-lookup"><span data-stu-id="90b4e-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="90b4e-119">Im folgende Beispiel wird das Problem behebt, indem Sie sicherstellen, dass die **schließlich** -Klausel wurde ausgeführt, bevor eine Ausnahme des Aufrufers Filter Ausnahmeblöcke angeboten.</span><span class="sxs-lookup"><span data-stu-id="90b4e-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90b4e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90b4e-120">See Also</span></span>  
 [<span data-ttu-id="90b4e-121">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="90b4e-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
