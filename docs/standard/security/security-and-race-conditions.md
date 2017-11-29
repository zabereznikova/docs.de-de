---
title: Sicherheit und Racebedingungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c092113f670c5799d98dcb13c9c713bbd1a47fb6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-race-conditions"></a>Sicherheit und Racebedingungen
Eine andere Stelle relevant ist, potenzielle Sicherheitslücken ausgenutzt Racebedingungen. Es gibt mehrere Möglichkeiten, die in denen dies geschehen kann. In den Unterthemen, die Folgen werden einige der gravierenden Fehler, die der Entwickler zu vermeiden, muss.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Racebedingungen, in der Dispose-Methode  
 Wenn einer Klasse **Dispose** Methode (Weitere Informationen finden Sie unter [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) ist nicht synchronisiert, ist es möglich, Bereinigungscode in **Dispose** kann ausgeführt werden, mehr als einmal, wie im folgenden Beispiel gezeigt.  
  
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
  
 Da dies **Dispose** Implementierung nicht synchronisiert wird, ist es möglich, dass `Cleanup` zum Aufrufen durch einen Thread, und klicken Sie dann einen zweiten Thread vor `_myObj` festgelegt ist, um **null**. Ob dies ein Sicherheitsbedenken ist hängt von Was geschieht, wenn die `Cleanup` code ausgeführt wird. Ein ernstes Problem mit nicht synchronisierten **Dispose** Implementierungen umfasst die Verwendung der Ressourcenhandles, wie z. B. Dateien. Unsachgemäße Entsorgung kann die falsche Handle verwendet werden, verursachen, die Websuche zu Sicherheitsrisiken führt.  
  
## <a name="race-conditions-in-constructors"></a>Racebedingungen in Konstruktoren  
 In einigen Anwendungen ist es möglicherweise möglich, dass andere Threads auf Klassenmember zugegriffen wird, bevor Sie deren Klassenkonstruktoren vollständig ausgeführt wurden. Sie sollten überprüfen, dass alle Klassenkonstruktoren, um sicherzustellen, dass keine Sicherheitsprobleme vorliegen, wenn dies der Fall sein sollte, oder Threads zu synchronisieren, falls erforderlich.  
  
## <a name="race-conditions-with-cached-objects"></a>Racebedingungen mit zwischengespeicherten Objekten  
 Code, der Sicherheitsinformationen zwischengespeichert oder verwendet die Codezugriffssicherheit [Assert](../../../docs/framework/misc/using-the-assert-method.md) Vorgang möglicherweise auch anfällig für Racebedingungen auftreten, wenn andere Teile der Klasse nicht ordnungsgemäß synchronisiert werden, wie im folgenden Beispiel gezeigt.  
  
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
  
 Wenn es werden weitere Pfade zu `DoOtherWork` , die von einem anderen Thread mit dem gleichen Objekt aufgerufen werden können, ein nicht vertrauenswürdiger Aufrufer Forderung verzögern kann.  
  
 Wenn Ihr Code Sicherheitsinformationen zwischenspeichert, stellen Sie sicher, dass es für diese Sicherheitslücke zu überprüfen.  
  
## <a name="race-conditions-in-finalizers"></a>Racebedingungen im Finalizer  
 Racebedingungen können auch in einem Objekt auftreten, die eine statische oder nicht verwaltete Ressource verweist, die dann in der Finalizer freigegeben. Wenn mehrere Objekte eine Ressource gemeinsam, die in den Finalizer einer Klasse bearbeitet wird nutzen, müssen alle Zugriff auf die Ressource von der Objekte synchronisiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
