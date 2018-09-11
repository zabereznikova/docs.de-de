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
ms.openlocfilehash: 57ceaedc7c38ae70a0db5a7fd584a765a7474aff
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339338"
---
# <a name="security-and-race-conditions"></a>Sicherheit und Racebedingungen
Ein weiterer Bereich von Bedeutung ist, potenzielle Sicherheitslücken, die durch Racebedingungen ausgenutzt wird. Es gibt mehrere Möglichkeiten, die in denen dies geschehen kann. Die folgenden untergeordneten Themen werden einige der wichtigsten Fehlerquellen, die der Entwickler zu vermeiden, muss.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Racebedingungen, in die Dispose-Methode  
 Wenn einer Klasse des **Dispose** Methode (Weitere Informationen finden Sie unter [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) ist nicht synchronisiert, es ist möglich, Bereinigungscode in **Dispose** kann ausgeführt werden, mehr als einmal, wie im folgenden Beispiel gezeigt.  
  
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
  
 Da dies **Dispose** Implementierung nicht synchronisiert wird, ist es möglich, dass `Cleanup` Aufruf durch einen Thread, und klicken Sie dann einen zweiten Thread vor dem `_myObj` nastaven NA hodnotu **null**. Ob dies ein Sicherheitsproblem ist Was geschieht, hängt bei dem `Cleanup` code ausgeführt wird. Problem mit der nicht synchronisierten **Dispose** Implementierungen schließt die Verwendung eines Ressourcenhandles, z. B. Dateien. Eine fehlerhafte Löschung kann das falsche Handle verwendet werden, was häufig zu Sicherheitsrisiken führt.  
  
## <a name="race-conditions-in-constructors"></a>Racebedingungen in Konstruktoren  
 In einigen Anwendungen ist es möglicherweise möglich, dass andere Threads auf Klassenmember zugegriffen wird, bevor Sie deren Klassenkonstruktoren vollständig ausgeführt haben. Sie sollten überprüfen, dass alle Klassenkonstruktoren, um sicherzustellen, dass keine Sicherheitsprobleme vorliegen, wenn dies geschehen sollte, oder Threads zu synchronisieren, falls erforderlich.  
  
## <a name="race-conditions-with-cached-objects"></a>Racebedingungen mit zwischengespeicherten Objekten  
 Code, speichert Informationen zur Sicherheit oder verwendet die Codezugriffssicherheit [Assert](../../../docs/framework/misc/using-the-assert-method.md) Vorgang möglicherweise auch Racebedingungen anfällig, wenn andere Teile der Klasse nicht ordnungsgemäß synchronisiert sind, wie im folgenden Beispiel gezeigt.  
  
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
  
 Wenn es gibt andere Pfade zu `DoOtherWork` , die von einem anderen Thread mit demselben Objekt aufgerufen werden kann, ein nicht vertrauenswürdiger Aufrufer Forderung verzögern kann.  
  
 Stellen Sie Informationen zur Sicherheit von Ihrem Code zwischengespeichert werden, sicher, dass es hinsichtlich dieser Schwachstelle zu überprüfen.  
  
## <a name="race-conditions-in-finalizers"></a>Racebedingungen im Finalizer  
 Racebedingungen können auch in einem Objekt auftreten, die eine statische oder nicht verwaltete Ressource verweist, die dann in der Finalizer freigegeben. Wenn mehrere Objekte auf eine Ressource, die in den Finalizer einer Klasse geändert wird freigeben, müssen die Objekte alle Zugriffe auf diese Ressource synchronisieren.  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
