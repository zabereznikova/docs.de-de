---
title: Sicherheit und Racebedingungen
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
ms.openlocfilehash: a667bf69ba72cbe203bd2603c4c6b7a1e58a6d43
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555109"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="893da-102">Sicherheit und Racebedingungen</span><span class="sxs-lookup"><span data-stu-id="893da-102">Security and Race Conditions</span></span>

<span data-ttu-id="893da-103">Ein weiterer betroffenbereich ist das Potenzial von Sicherheitslücken, die von Racebedingungen ausgenutzt werden.</span><span class="sxs-lookup"><span data-stu-id="893da-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="893da-104">Es gibt mehrere Möglichkeiten, dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="893da-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="893da-105">In den folgenden Unterthemen werden einige der Hauptprobleme erläutert, die der Entwickler vermeiden muss.</span><span class="sxs-lookup"><span data-stu-id="893da-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="893da-106">Racebedingungen in der verwerfen-Methode</span><span class="sxs-lookup"><span data-stu-id="893da-106">Race Conditions in the Dispose Method</span></span>  

<span data-ttu-id="893da-107">Wenn die **verwerfen-Methode** einer Klasse (Weitere Informationen finden Sie unter [Garbage Collection](../garbage-collection/index.md)) nicht synchronisiert ist, kann der Bereinigungs **Code in "** verwerfen" mehrmals ausgeführt werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="893da-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()
{  
    if (myObj != null)
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
<span data-ttu-id="893da-108">Da diese **Lösch** Implementierung nicht synchronisiert wird, kann es vorkommen, dass Sie `Cleanup` durch den ersten Thread aufgerufen wird und ein zweiter Thread vor `_myObj` auf **null**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="893da-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="893da-109">Ob dies ein Sicherheitsproblem ist, hängt davon ab, was geschieht, wenn der Code ausgeführt wird `Cleanup` .</span><span class="sxs-lookup"><span data-stu-id="893da-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="893da-110">Ein schwerwiegendes Problem bei **nicht synchronisierten** Lösch Implementierungen umfasst die Verwendung von Ressourcen Handles wie z. b. Dateien.</span><span class="sxs-lookup"><span data-stu-id="893da-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="893da-111">Eine nicht ordnungsgemäße Löschung kann dazu führen, dass das falsche Handle verwendet wird. Dies führt häufig zu Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="893da-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="893da-112">Racebedingungen in Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="893da-112">Race Conditions in Constructors</span></span>

<span data-ttu-id="893da-113">In einigen Anwendungen kann es möglich sein, dass andere Threads auf Klassenmember zugreifen können, bevor deren Klassenkonstruktoren vollständig ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="893da-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="893da-114">Überprüfen Sie alle Klassenkonstruktoren, um sicherzustellen, dass keine Sicherheitsprobleme auftreten, oder synchronisieren Sie ggf. Threads.</span><span class="sxs-lookup"><span data-stu-id="893da-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="893da-115">Racebedingungen mit zwischengespeicherten Objekten</span><span class="sxs-lookup"><span data-stu-id="893da-115">Race Conditions with Cached Objects</span></span>  

<span data-ttu-id="893da-116">Code, der Sicherheitsinformationen zwischenspeichert oder den Code Zugriffs Sicherheits- [Assert](../../framework/misc/using-the-assert-method.md) -Vorgang verwendet, ist möglicherweise auch anfällig für Racebedingungen, wenn andere Teile der Klasse nicht ordnungsgemäß synchronisiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="893da-116">Code that caches security information or uses the code access security [Assert](../../framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()
{  
    if (SomeDemandPasses())
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()
{  
    if (fCallersOK)
    {  
        DoSomethingTrusted();  
    }  
    else
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
<span data-ttu-id="893da-117">Wenn andere Pfade zu vorhanden sind, die `DoOtherWork` von einem anderen Thread mit demselben Objekt aufgerufen werden können, kann ein nicht vertrauenswürdiger Aufrufer über eine Anforderung hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="893da-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
<span data-ttu-id="893da-118">Wenn Ihr Code Sicherheitsinformationen zwischenspeichert, stellen Sie sicher, dass Sie diese Sicherheitslücke überprüfen.</span><span class="sxs-lookup"><span data-stu-id="893da-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="893da-119">Racebedingungen in Finalizern</span><span class="sxs-lookup"><span data-stu-id="893da-119">Race Conditions in Finalizers</span></span>  

<span data-ttu-id="893da-120">Racebedingungen können auch in einem Objekt auftreten, das auf eine statische oder nicht verwaltete Ressource verweist, die Sie dann im Finalizer freigibt.</span><span class="sxs-lookup"><span data-stu-id="893da-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="893da-121">Wenn mehrere Objekte eine Ressource gemeinsam verwenden, die im Finalizer einer Klasse bearbeitet wird, müssen die Objekte den gesamten Zugriff auf diese Ressource synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="893da-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893da-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="893da-122">See also</span></span>

- [<span data-ttu-id="893da-123">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="893da-123">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="893da-124">ASP.net Core Sicherheit</span><span class="sxs-lookup"><span data-stu-id="893da-124">ASP.NET Core Security</span></span>](/aspnet/core/security/)
