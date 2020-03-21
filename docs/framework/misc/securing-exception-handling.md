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
# <a name="securing-exception-handling"></a><span data-ttu-id="ef9b9-102">Sichern der Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="ef9b9-102">Securing Exception Handling</span></span>
<span data-ttu-id="ef9b9-103">In Visual C++ und Visual Basic wird ein Filterausdruck weiter oben im Stapel ausgeführt, bevor eine **abschließende** Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="ef9b9-104">Der diesem Filter zugeordnete **catch-Block** wird nach der **finally-Anweisung** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="ef9b9-105">Weitere Informationen finden Sie unter [Verwenden von benutzergefilterten Ausnahmen](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="ef9b9-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="ef9b9-106">In diesem Abschnitt werden die Sicherheitsauswirkungen dieser Bestellung untersucht.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="ef9b9-107">Betrachten Sie das folgende Pseudocodebeispiel, das die Reihenfolge veranschaulicht, in der Filteranweisungen und **schließlich** Anweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="ef9b9-108">Dieser Code druckt Folgendes.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="ef9b9-109">Der Filter wird vor der **finally-Anweisung** ausgeführt, sodass Sicherheitsprobleme durch alles eingeführt werden können, was eine Zustandsänderung vornimmt, bei der die Ausführung von anderem Code vorteilen sein könnte.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="ef9b9-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ef9b9-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="ef9b9-111">Dieser Pseudocode ermöglicht es einem Filter höher im Stapel, beliebigen Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="ef9b9-112">Andere Beispiele für Vorgänge, die einen ähnlichen Effekt haben würden, sind die temporäre Identitätswechsel mit einer anderen Identität, das Festlegen eines internen Flags, das eine Sicherheitsüberprüfung umgeht, oder das Ändern der dem Thread zugeordneten Kultur.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="ef9b9-113">Die empfohlene Lösung besteht darin, einen Ausnahmehandler einzuführen, um die Änderungen des Codes im Threadstatus von den Filterblöcken der Aufrufer zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="ef9b9-114">Es ist jedoch wichtig, dass der Ausnahmehandler ordnungsgemäß eingeführt wird, oder dieses Problem wird nicht behoben.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="ef9b9-115">Im folgenden Beispiel wird die UI-Kultur geändert, aber jede Art von Threadstatusänderung kann auf ähnliche Weise verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="ef9b9-116">Die richtige Lösung in diesem Fall ist, den **try**/vorhandenen/**Try-Finally-Block** in einem try**catch-Block** zu umschließen. **try**</span><span class="sxs-lookup"><span data-stu-id="ef9b9-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="ef9b9-117">Die einfache Einführung einer **Catch-throw-Klausel** in den vorhandenen **try**/**Try-Finally-Block** behebt das Problem nicht, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="ef9b9-118">Dadurch wird das Problem nicht behoben, da `FilterFunc` die **finally-Anweisung** nicht ausgeführt wurde, bevor das Steuerelement abruft.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="ef9b9-119">Im folgenden Beispiel wird das Problem behoben, indem sichergestellt wird, dass die **finally-Klausel** ausgeführt wurde, bevor eine Ausnahme in den Ausnahmefilterblöcken der Aufrufer angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="ef9b9-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ef9b9-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef9b9-120">See also</span></span>

- [<span data-ttu-id="ef9b9-121">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="ef9b9-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
