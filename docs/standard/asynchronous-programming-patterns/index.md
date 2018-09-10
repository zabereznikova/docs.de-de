---
title: Muster für die asynchrone Programmierung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e399a512d2bee636aec35e008c0632ce9c5fa781
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44172641"
---
# <a name="asynchronous-programming-patterns"></a>Muster für die asynchrone Programmierung

Das.NET Framework bietet drei Muster für das Durchführen asynchroner Vorgänge:  
  
- **APM-Muster (Asynchronous Programming Model**, auch <xref:System.IAsyncResult>-Muster genannt), in dem asynchrone Vorgänge `Begin`- und `End`-Methoden erfordern (z.B. `BeginWrite` und `EndWrite` für asynchrone Schreibvorgänge). Dieses Muster ist für neue Entwicklungen nicht mehr empfehlenswert. Weitere Informationen finden Sie unter [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell (APM))](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).  
  
- Das **ereignisbasierte asynchrone Muster (EAP)**, das eine Methode mit einem `Async`-Suffix und mindestens ein Ereignis, einen Ereignishandler-Delegattypen und von `EventArg` abgeleitete Typen erfordert. EAP wurde in .NET Framework 2.0 eingeführt. Es für neue Entwicklungen nicht mehr empfehlenswert. Weitere Informationen finden Sie unter [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
- Das **Taskbasierte asynchrone Muster (Task-based Asynchronous Pattern, TAP)** verwendet eine einzelne Methode, um die Initiierung und den Abschluss eines asynchronen Vorgangs darzustellen. TAP wurde in .NET Framework 4 eingeführt und ist die empfohlene Vorgehensweise für die asynchrone Programmierung im .NET Framework. Die Schlüsselwörter [async](~/docs/csharp/language-reference/keywords/async.md) und [await](~/docs/csharp/language-reference/keywords/await.md) in C# und die Operatoren [Async](~/docs/visual-basic/language-reference/modifiers/async.md) und [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic Language fügen Sprachunterstützung für TAP hinzu. Weitere Informationen finden Sie unter [Task-based Asynchronous Pattern (TAP) (Aufgabenbasiertes asynchrones Muster (TAP))](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).  
  
## <a name="comparing-patterns"></a>Vergleichen von Mustern  

Für einen schnellen Vergleich dazu, wie die drei Muster asynchrone Vorgänge modellieren, sollten Sie eine `Read`-Methode verwenden, die eine angegebene Datenmenge in einen bereitgestellten Puffer beginnend an einem angegebenen Offset liest:  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
Das APM-Gegenstück dieser Methode würde die Methoden `BeginRead` und `EndRead` verfügbar machen:  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
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
  
Das TAP-Gegenstück würde die folgende einzelne `ReadAsync`-Methode verfügbar machen:  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
Eine umfassende Erörterung von TAP, APM und EAP finden Sie unter den Links im nächsten Abschnitt.  
  
## <a name="related-topics"></a>Verwandte Themen

| Title | Beschreibung |
| ----- | ----------- |
| [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell (APM))](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | Beschreibt das Legacymodell, das die <xref:System.IAsyncResult>-Schnittstelle verwendet, um asynchrones Verhalten bereitzustellen. Dieses Modell ist für neue Entwicklungen nicht mehr empfehlenswert. |
| [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | Beschreibt das ereignisbasierte Legacymodell für die Bereitstellung des asynchronen Verhaltens. Dieses Modell ist für neue Entwicklungen nicht mehr empfehlenswert. |
| [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Aufgabenbasiertes asynchrones Muster) | Beschreibt das neue asynchrone Muster basierend auf dem <xref:System.Threading.Tasks>-Namespace. Dieses Modell ist der empfohlene Ansatz für die asynchrone Programmierung in .NET Framework 4 und höheren Versionen. |

## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung in C#](~/docs/csharp/async.md)   
- [Asynchrone Programmierung in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)   
- [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/async/index.md)
