---
title: Muster für die asynchrone Programmierung
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: e1efe9c3eb57f317def91e527506c358eb086679
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160052"
---
# <a name="asynchronous-programming-patterns"></a>Muster für die asynchrone Programmierung

In .NET werden drei Muster für das Ausführen asynchroner Vorgänge bereitgestellt:  

- Das **Taskbasierte asynchrone Muster (Task-based Asynchronous Pattern, TAP)** verwendet eine einzelne Methode, um die Initiierung und den Abschluss eines asynchronen Vorgangs darzustellen. TAP wurde in .NET Framework 4 eingeführt. **TAP ist das empfohlene Muster für die asynchrone Programmierung in .NET.** Die Schlüsselwörter [async](../../csharp/language-reference/keywords/async.md) und [await](../../csharp/language-reference/operators/await.md) in C# und die Operatoren [Async](../../visual-basic/language-reference/modifiers/async.md) und [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic fügen Sprachunterstützung für TAP hinzu. Weitere Informationen finden Sie unter [Task-based Asynchronous Pattern (TAP) (Aufgabenbasiertes asynchrones Muster (TAP))](task-based-asynchronous-pattern-tap.md).  

- Das **Ereignisbasierte asynchrones Muster (Event-based Asynchronous Pattern, EAP)** , das das ereignisbasierte Legacymodell für die Bereitstellung des asynchronen Verhaltens ist. Dieses Muster erfordert eine Methode, die das `Async`-Suffix und mindestens ein Ereignis, einen Ereignishandler-Delegattypen und aus `EventArg` abgeleitete Typen hat. EAP wurde in .NET Framework 2.0 eingeführt. EAP ist für neue Entwicklungen nicht mehr empfehlenswert. Weitere Informationen finden Sie unter [Ereignisbasiertes asynchrones Muster (EAP)](event-based-asynchronous-pattern-eap.md).  

- Das Muster für das **Asynchrone Programmiermodell (APM)** (wird auch als <xref:System.IAsyncResult>-Muster bezeichnet), das das Legacymodell ist, in dem die <xref:System.IAsyncResult>-Schnittstelle verwendet wird, um asynchrones Verhalten bereitzustellen. In diesem Muster sind für synchrone Vorgänge eine `Begin`- und eine `End`-Methode erforderlich (z. B. `BeginWrite` und `EndWrite`), um einen asynchronen Schreibvorgang zu implementieren). Dieses Muster ist für neue Entwicklungen nicht mehr empfehlenswert. Weitere Informationen finden Sie unter [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell (APM))](asynchronous-programming-model-apm.md).  
  
## <a name="comparison-of-patterns"></a>Vergleich der Muster

Für einen schnellen Vergleich dazu, wie die drei Muster asynchrone Vorgänge modellieren, sollten Sie eine `Read`-Methode verwenden, die eine angegebene Datenmenge in einen bereitgestellten Puffer beginnend an einem angegebenen Offset liest:  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

Das TAP-Gegenstück zu dieser Methode würde die folgende einzelne `ReadAsync` Methode verfügbar machen:  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

Das EAP-Gegenstück würde den folgenden Satz von Typen und Membern verfügbar machen:  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
Das APM-Gegenstück würde die Methoden `BeginRead` und `EndRead` verfügbar machen:  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a>Weitere Informationen

- [Async ausführlich](../async-in-depth.md)
- [Asynchrone Programmierung in C#](../../csharp/async.md)
- [Asynchrone Programmierung in F#](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md)
