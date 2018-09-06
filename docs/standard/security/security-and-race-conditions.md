---
title: Sicherheit und Racebedingungen
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e613ad4823254a6bed43cb95294e6b8d3674b6d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881748"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="a83e5-102">Sicherheit und Racebedingungen</span><span class="sxs-lookup"><span data-stu-id="a83e5-102">Security and Race Conditions</span></span>
<span data-ttu-id="a83e5-103">Ein weiterer Bereich von Bedeutung ist, potenzielle Sicherheitslücken, die durch Racebedingungen ausgenutzt wird.</span><span class="sxs-lookup"><span data-stu-id="a83e5-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="a83e5-104">Es gibt mehrere Möglichkeiten, die in denen dies geschehen kann.</span><span class="sxs-lookup"><span data-stu-id="a83e5-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="a83e5-105">Die folgenden untergeordneten Themen werden einige der wichtigsten Fehlerquellen, die der Entwickler zu vermeiden, muss.</span><span class="sxs-lookup"><span data-stu-id="a83e5-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="a83e5-106">Racebedingungen, in die Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="a83e5-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="a83e5-107">Wenn einer Klasse des **Dispose** Methode (Weitere Informationen finden Sie unter [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) ist nicht synchronisiert, es ist möglich, Bereinigungscode in **Dispose** kann ausgeführt werden, mehr als einmal, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a83e5-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 <span data-ttu-id="a83e5-108">Da dies **Dispose** Implementierung nicht synchronisiert wird, ist es möglich, dass `Cleanup` Aufruf durch einen Thread, und klicken Sie dann einen zweiten Thread vor dem `_myObj` nastaven NA hodnotu **null**.</span><span class="sxs-lookup"><span data-stu-id="a83e5-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="a83e5-109">Ob dies ein Sicherheitsproblem ist Was geschieht, hängt bei dem `Cleanup` code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a83e5-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="a83e5-110">Problem mit der nicht synchronisierten **Dispose** Implementierungen schließt die Verwendung eines Ressourcenhandles, z. B. Dateien.</span><span class="sxs-lookup"><span data-stu-id="a83e5-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="a83e5-111">Eine fehlerhafte Löschung kann das falsche Handle verwendet werden, was häufig zu Sicherheitsrisiken führt.</span><span class="sxs-lookup"><span data-stu-id="a83e5-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="a83e5-112">Racebedingungen in Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="a83e5-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="a83e5-113">In einigen Anwendungen ist es möglicherweise möglich, dass andere Threads auf Klassenmember zugegriffen wird, bevor Sie deren Klassenkonstruktoren vollständig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="a83e5-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="a83e5-114">Sie sollten überprüfen, dass alle Klassenkonstruktoren, um sicherzustellen, dass keine Sicherheitsprobleme vorliegen, wenn dies geschehen sollte, oder Threads zu synchronisieren, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a83e5-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="a83e5-115">Racebedingungen mit zwischengespeicherten Objekten</span><span class="sxs-lookup"><span data-stu-id="a83e5-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="a83e5-116">Code, speichert Informationen zur Sicherheit oder verwendet die Codezugriffssicherheit [Assert](../../../docs/framework/misc/using-the-assert-method.md) Vorgang möglicherweise auch Racebedingungen anfällig, wenn andere Teile der Klasse nicht ordnungsgemäß synchronisiert sind, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a83e5-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
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
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
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
  
 <span data-ttu-id="a83e5-117">Wenn es gibt andere Pfade zu `DoOtherWork` , die von einem anderen Thread mit demselben Objekt aufgerufen werden kann, ein nicht vertrauenswürdiger Aufrufer Forderung verzögern kann.</span><span class="sxs-lookup"><span data-stu-id="a83e5-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="a83e5-118">Stellen Sie Informationen zur Sicherheit von Ihrem Code zwischengespeichert werden, sicher, dass es hinsichtlich dieser Schwachstelle zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a83e5-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="a83e5-119">Racebedingungen im Finalizer</span><span class="sxs-lookup"><span data-stu-id="a83e5-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="a83e5-120">Racebedingungen können auch in einem Objekt auftreten, die eine statische oder nicht verwaltete Ressource verweist, die dann in der Finalizer freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a83e5-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="a83e5-121">Wenn mehrere Objekte auf eine Ressource, die in den Finalizer einer Klasse geändert wird freigeben, müssen die Objekte alle Zugriffe auf diese Ressource synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="a83e5-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83e5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a83e5-122">See also</span></span>

- [<span data-ttu-id="a83e5-123">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="a83e5-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
