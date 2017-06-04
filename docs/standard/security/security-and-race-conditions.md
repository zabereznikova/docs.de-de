---
title: "Security and Race Conditions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], race conditions"
  - "race conditions"
  - "secure coding, race conditions"
  - "code security, race conditions"
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Security and Race Conditions
Ein weiteres Problemfeld besteht in der Möglichkeit, dass Sicherheitslücken durch Racebedingungen ausgenutzt werden.  Diesbezügliche Probleme können auf verschiedene Weise auftreten.  In den folgenden untergeordneten Themen werden einige der gravierenden Fehler erläutert, die von Entwicklern vermieden werden müssen.  
  
## Racebedingungen in der Dispose\-Methode  
 Wenn die **Dispose**\-Methode einer Klasse \(weitere Informationen hierzu unter [Garbage Collection](../../../docs/standard/garbage-collection/index.md)\) nicht synchronisiert wird, kann Bereinigungscode in **Dispose** mehrmals ausgeführt werden, wie im folgenden Beispiel veranschaulicht.  
  
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
  
 Da diese Implementierung von **Dispose** nicht synchronisiert wird, kann `Cleanup` u. U. erst durch einen Thread und anschließend durch einen zweiten Thread aufgerufen werden, bevor `_myObj` auf **null** festgelegt wird.  Ob dies ein Sicherheitsproblem darstellt, hängt von den Ereignissen während der Ausführung des `Cleanup`\-Codes ab.  Ein ernstes Problem bei nicht synchronisierten Implementierungen von **Dispose** stellt die Verwendung von Ressourcenhandles \(z. B. Dateien\) dar.  Eine falsche Freigabe kann die Verwendung des falschen Handles bewirken. Dies führt häufig zu Sicherheitsrisiken.  
  
## Racebedingungen in Konstruktoren  
 In einigen Anwendungen können möglicherweise andere Threads auf Klassenmember zugreifen, bevor ihre Klassenkonstruktoren vollständig ausgeführt wurden.  Sie müssen alle Klassenkonstruktoren überprüfen, um sicherzustellen, dass bei einem solchen Ereignis keine Sicherheitsprobleme auftreten. Synchronisieren Sie ggf. die Threads.  
  
## Racebedingungen mit zwischengespeicherten Objekten  
 Code, der Sicherheitsinformationen zwischenspeichert oder die [Assert](../../../docs/framework/misc/using-the-assert-method.md)\-Operation für die Codezugriffssicherheit verwendet, kann ebenso anfällig für Racebedingungen sein, wenn andere Teile der Klasse nicht ordnungsgemäß synchronisiert werden. Dies wird im folgenden Beispiel veranschaulicht.  
  
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
  
 Wenn weitere Pfade zu `DoOtherWork` vorhanden sind, die von einem anderen Thread mit demselben Objekt aufgerufen werden können, kann eine Forderung durch einen nicht vertrauenswürdigen Aufrufer umgangen werden.  
  
 Wenn der Code Sicherheitsinformationen zwischenspeichert, müssen Sie unbedingt eine Überprüfung auf dieses Risiko durchführen.  
  
## Racebedingungen in Finalizern  
 Racebedingungen können auch in einem Objekt auftreten, das auf eine statische oder nicht verwaltete Ressource verweist, die anschließend in seinem Finalizer freigegeben wird.  Wenn mehrere Objekte eine Ressource gemeinsam verwenden und diese im Finalizer einer Klasse bearbeitet wird, müssen die Objekte jeglichen Zugriff auf diese Ressource synchronisieren.  
  
## Siehe auch  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)