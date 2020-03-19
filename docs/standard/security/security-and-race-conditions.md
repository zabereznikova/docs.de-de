---
title: Sicherheit und Racebedingungen
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
ms.openlocfilehash: 09d8d0d6e85af04fe0fb00f53df408126012081e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186781"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="64a94-102">Sicherheit und Racebedingungen</span><span class="sxs-lookup"><span data-stu-id="64a94-102">Security and Race Conditions</span></span>
<span data-ttu-id="64a94-103">Ein weiterer Bereich, der Anlass zur Sorge gibt, ist das Potenzial für Sicherheitslücken, die durch die Bedingungen der Rassen ausgenutzt werden.</span><span class="sxs-lookup"><span data-stu-id="64a94-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="64a94-104">Es gibt mehrere Möglichkeiten, wie dies geschehen kann.</span><span class="sxs-lookup"><span data-stu-id="64a94-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="64a94-105">Die folgenden Unterthemen skizzieren einige der wichtigsten Fallstricke, die der Entwickler vermeiden muss.</span><span class="sxs-lookup"><span data-stu-id="64a94-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="64a94-106">Race-Bedingungen in der Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="64a94-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="64a94-107">Wenn die **Dispose-Methode** einer Klasse (weitere Informationen finden Sie unter [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) nicht synchronisiert ist, kann Bereinigungscode in **Dispose** möglicherweise mehr als einmal ausgeführt werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="64a94-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="64a94-108">Da diese **Dispose-Implementierung** nicht synchronisiert ist, ist es möglich, zuerst von einem Thread und dann von einem zweiten Thread aufgerufen `Cleanup` zu werden, bevor `_myObj` auf **null**festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="64a94-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="64a94-109">Ob dies ein Sicherheitsproblem ist, `Cleanup` hängt davon ab, was passiert, wenn der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="64a94-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="64a94-110">Ein Hauptproblem bei **Dispose** nicht synchronisierten Dispose-Implementierungen ist die Verwendung von Ressourcenhandles wie Dateien.</span><span class="sxs-lookup"><span data-stu-id="64a94-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="64a94-111">Unsachgemäße Entsorgung kann dazu führen, dass das falsche Handle verwendet wird, was häufig zu Sicherheitslücken führt.</span><span class="sxs-lookup"><span data-stu-id="64a94-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="64a94-112">Rennbedingungen in Konstrukteuren</span><span class="sxs-lookup"><span data-stu-id="64a94-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="64a94-113">In einigen Anwendungen ist es möglicherweise möglich, dass andere Threads auf Klassenmember zugreifen, bevor ihre Klassenkonstruktoren vollständig ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="64a94-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="64a94-114">Sie sollten alle Klassenkonstruktoren überprüfen, um sicherzustellen, dass keine Sicherheitsprobleme auftreten, falls dies geschehen sollte, oder Threads bei Bedarf synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="64a94-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="64a94-115">Race-Bedingungen mit zwischengespeicherten Objekten</span><span class="sxs-lookup"><span data-stu-id="64a94-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="64a94-116">Code, der Sicherheitsinformationen zwischenspeichert oder den [Codezugriffssicherheits-Assert-Vorgang](../../../docs/framework/misc/using-the-assert-method.md) verwendet, kann auch anfällig für Racebedingungen sein, wenn andere Teile der Klasse nicht entsprechend synchronisiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="64a94-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="64a94-117">Wenn es andere `DoOtherWork` Pfade gibt, zu denen von einem anderen Thread mit demselben Objekt aufgerufen werden kann, kann ein nicht vertrauenswürdiger Aufrufer an einer Anforderung vorbeirutschen.</span><span class="sxs-lookup"><span data-stu-id="64a94-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="64a94-118">Wenn Ihr Code Sicherheitsinformationen zwischenspeichert, stellen Sie sicher, dass Sie sie auf diese Sicherheitsanfälligkeit überprüfen.</span><span class="sxs-lookup"><span data-stu-id="64a94-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="64a94-119">Rennbedingungen in Finalizern</span><span class="sxs-lookup"><span data-stu-id="64a94-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="64a94-120">Race-Bedingungen können auch in einem Objekt auftreten, das auf eine statische oder nicht verwaltete Ressource verweist, die es dann im Finalizer freigibt.</span><span class="sxs-lookup"><span data-stu-id="64a94-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="64a94-121">Wenn mehrere Objekte eine Ressource gemeinsam nutzen, die im Finalizer einer Klasse bearbeitet wird, müssen die Objekte den gesamten Zugriff auf diese Ressource synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="64a94-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a94-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64a94-122">See also</span></span>

- [<span data-ttu-id="64a94-123">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="64a94-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
