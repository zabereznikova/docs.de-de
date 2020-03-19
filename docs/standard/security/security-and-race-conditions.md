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
# <a name="security-and-race-conditions"></a>Sicherheit und Racebedingungen
Ein weiterer Bereich, der Anlass zur Sorge gibt, ist das Potenzial für Sicherheitslücken, die durch die Bedingungen der Rassen ausgenutzt werden. Es gibt mehrere Möglichkeiten, wie dies geschehen kann. Die folgenden Unterthemen skizzieren einige der wichtigsten Fallstricke, die der Entwickler vermeiden muss.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Race-Bedingungen in der Dispose-Methode  
 Wenn die **Dispose-Methode** einer Klasse (weitere Informationen finden Sie unter [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) nicht synchronisiert ist, kann Bereinigungscode in **Dispose** möglicherweise mehr als einmal ausgeführt werden, wie im folgenden Beispiel gezeigt.  
  
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
  
 Da diese **Dispose-Implementierung** nicht synchronisiert ist, ist es möglich, zuerst von einem Thread und dann von einem zweiten Thread aufgerufen `Cleanup` zu werden, bevor `_myObj` auf **null**festgelegt wird. Ob dies ein Sicherheitsproblem ist, `Cleanup` hängt davon ab, was passiert, wenn der Code ausgeführt wird. Ein Hauptproblem bei **Dispose** nicht synchronisierten Dispose-Implementierungen ist die Verwendung von Ressourcenhandles wie Dateien. Unsachgemäße Entsorgung kann dazu führen, dass das falsche Handle verwendet wird, was häufig zu Sicherheitslücken führt.  
  
## <a name="race-conditions-in-constructors"></a>Rennbedingungen in Konstrukteuren  
 In einigen Anwendungen ist es möglicherweise möglich, dass andere Threads auf Klassenmember zugreifen, bevor ihre Klassenkonstruktoren vollständig ausgeführt wurden. Sie sollten alle Klassenkonstruktoren überprüfen, um sicherzustellen, dass keine Sicherheitsprobleme auftreten, falls dies geschehen sollte, oder Threads bei Bedarf synchronisieren.  
  
## <a name="race-conditions-with-cached-objects"></a>Race-Bedingungen mit zwischengespeicherten Objekten  
 Code, der Sicherheitsinformationen zwischenspeichert oder den [Codezugriffssicherheits-Assert-Vorgang](../../../docs/framework/misc/using-the-assert-method.md) verwendet, kann auch anfällig für Racebedingungen sein, wenn andere Teile der Klasse nicht entsprechend synchronisiert werden, wie im folgenden Beispiel gezeigt.  
  
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
  
 Wenn es andere `DoOtherWork` Pfade gibt, zu denen von einem anderen Thread mit demselben Objekt aufgerufen werden kann, kann ein nicht vertrauenswürdiger Aufrufer an einer Anforderung vorbeirutschen.  
  
 Wenn Ihr Code Sicherheitsinformationen zwischenspeichert, stellen Sie sicher, dass Sie sie auf diese Sicherheitsanfälligkeit überprüfen.  
  
## <a name="race-conditions-in-finalizers"></a>Rennbedingungen in Finalizern  
 Race-Bedingungen können auch in einem Objekt auftreten, das auf eine statische oder nicht verwaltete Ressource verweist, die es dann im Finalizer freigibt. Wenn mehrere Objekte eine Ressource gemeinsam nutzen, die im Finalizer einer Klasse bearbeitet wird, müssen die Objekte den gesamten Zugriff auf diese Ressource synchronisieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
