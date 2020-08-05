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
# <a name="security-and-race-conditions"></a>Sicherheit und Racebedingungen

Ein weiterer betroffenbereich ist das Potenzial von Sicherheitslücken, die von Racebedingungen ausgenutzt werden. Es gibt mehrere Möglichkeiten, dies zu tun. In den folgenden Unterthemen werden einige der Hauptprobleme erläutert, die der Entwickler vermeiden muss.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Racebedingungen in der verwerfen-Methode  

Wenn die **verwerfen-Methode** einer Klasse (Weitere Informationen finden Sie unter [Garbage Collection](../garbage-collection/index.md)) nicht synchronisiert ist, kann der Bereinigungs **Code in "** verwerfen" mehrmals ausgeführt werden, wie im folgenden Beispiel gezeigt.  
  
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
  
Da diese **Lösch** Implementierung nicht synchronisiert wird, kann es vorkommen, dass Sie `Cleanup` durch den ersten Thread aufgerufen wird und ein zweiter Thread vor `_myObj` auf **null**festgelegt ist. Ob dies ein Sicherheitsproblem ist, hängt davon ab, was geschieht, wenn der Code ausgeführt wird `Cleanup` . Ein schwerwiegendes Problem bei **nicht synchronisierten** Lösch Implementierungen umfasst die Verwendung von Ressourcen Handles wie z. b. Dateien. Eine nicht ordnungsgemäße Löschung kann dazu führen, dass das falsche Handle verwendet wird. Dies führt häufig zu Sicherheitsrisiken.  
  
## <a name="race-conditions-in-constructors"></a>Racebedingungen in Konstruktoren

In einigen Anwendungen kann es möglich sein, dass andere Threads auf Klassenmember zugreifen können, bevor deren Klassenkonstruktoren vollständig ausgeführt wurden. Überprüfen Sie alle Klassenkonstruktoren, um sicherzustellen, dass keine Sicherheitsprobleme auftreten, oder synchronisieren Sie ggf. Threads.  
  
## <a name="race-conditions-with-cached-objects"></a>Racebedingungen mit zwischengespeicherten Objekten  

Code, der Sicherheitsinformationen zwischenspeichert oder den Code Zugriffs Sicherheits- [Assert](../../framework/misc/using-the-assert-method.md) -Vorgang verwendet, ist möglicherweise auch anfällig für Racebedingungen, wenn andere Teile der Klasse nicht ordnungsgemäß synchronisiert werden, wie im folgenden Beispiel gezeigt.  
  
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
  
Wenn andere Pfade zu vorhanden sind, die `DoOtherWork` von einem anderen Thread mit demselben Objekt aufgerufen werden können, kann ein nicht vertrauenswürdiger Aufrufer über eine Anforderung hinausgehen.  
  
Wenn Ihr Code Sicherheitsinformationen zwischenspeichert, stellen Sie sicher, dass Sie diese Sicherheitslücke überprüfen.  
  
## <a name="race-conditions-in-finalizers"></a>Racebedingungen in Finalizern  

Racebedingungen können auch in einem Objekt auftreten, das auf eine statische oder nicht verwaltete Ressource verweist, die Sie dann im Finalizer freigibt. Wenn mehrere Objekte eine Ressource gemeinsam verwenden, die im Finalizer einer Klasse bearbeitet wird, müssen die Objekte den gesamten Zugriff auf diese Ressource synchronisieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für das Schreiben von sicherem Code](secure-coding-guidelines.md)
- [ASP.net Core Sicherheit](/aspnet/core/security/)
