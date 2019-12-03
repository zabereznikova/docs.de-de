---
title: ConcurrencyMode Reentrant
ms.date: 03/30/2017
ms.assetid: b2046c38-53d8-4a6c-a084-d6c7091d92b1
ms.openlocfilehash: 0ac3b811c59abfbb3148ddad3d518443f7633adc
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714964"
---
# <a name="concurrencymode-reentrant"></a>ConcurrencyMode Reentrant
In diesem Beispiel werden die Notwendigkeit und Auswirkungen der Verwendung von ConcurrencyMode.Reentrant in einer Dienstimplementierung veranschaulicht. ConcurrencyMode.Reentrant impliziert, dass der Dienst (oder Rückruf) nur jeweils eine Nachricht verarbeitet (analog zu `ConcurencyMode.Single`). Um die Thread Sicherheit sicherzustellen, sperrt Windows Communication Foundation (WCF) die `InstanceContext` Verarbeitung einer Nachricht, sodass keine anderen Nachrichten verarbeitet werden können. Im Reentrant-Modus wird der `InstanceContext` entsperrt, kurz bevor der Dienst einen ausgehenden Aufruf ausführt. So kann der folgende Aufruf (der wie in diesem Beispiel dargestellt wiedereintrittsfähig sein kann) beim nächsten Mal gesperrt werden, wenn er den Dienst erreicht. Zum Veranschaulichen des Verhaltens wird im Beispiel gezeigt, wie ein Client und ein Dienst untereinander Nachrichten mit einem Duplexvertrag senden können.  
  
 Bei dem definierten Vertrag handelt es sich um einen Duplexvertrag, bei dem die `Ping`-Methode vom Dienst und die Rückrufmethode `Pong` vom Client implementiert wird. Ein Client ruft die `Ping`-Methode des Servers mit einer Tickanzahl auf und initiiert so den Aufruf. Der Dienst überprüft, ob die Anzahl der Ticks ungleich 0 (null) ist, und ruft dann die `Pong`-Methode des Rückrufs auf, während die Tickanzahl verringert wird. Dies wird im Beispiel mit dem folgenden Code ausgeführt.  
  
```csharp
public void Ping(int ticks)  
{  
     Console.WriteLine("Ping: Ticks = " + ticks);  
     //Keep pinging back and forth till Ticks reaches 0.  
     if (ticks != 0)  
     {  
         OperationContext.Current.GetCallbackChannel<IPingPongCallback>().Pong((ticks - 1));  
     }  
}  
```  
  
 Die `Pong`-Implementierung des Rückrufs weist die gleiche Logik wie die `Ping`-Implementierung auf. Das heißt, es wird überprüft, ob die Anzahl der Ticks ungleich 0 (null) ist, und dann wird die `Ping`-Methode über den Rückrufkanal aufgerufen, wobei die Anzahl der Ticks um 1 reduziert wird. (in diesem Fall ist der Rückrufkanal der Kanal, über den die ursprüngliche `Ping`-Meldung gesendet wurde.) Wenn die Anzahl der Ticks 0 erreicht, kehrt die Methode zurück und entpackt dabei alle Antworten auf den ersten Aufruf, der vom Client getätigt wurde, der den Aufruf initiiert hat. Dies wird in der Rückrufimplementierung gezeigt.  
  
```csharp
public void Pong(int ticks)  
{  
    Console.WriteLine("Pong: Ticks = " + ticks);  
    if (ticks != 0)  
    {  
        //Retrieve the Callback  Channel (in this case the Channel which was used to send the  
        //original message) and make an outgoing call until ticks reaches 0.  
        IPingPong channel = OperationContext.Current.GetCallbackChannel<IPingPong>();  
        channel.Ping((ticks - 1));  
    }  
}  
```  
  
 Die `Ping`-Methode und die `Pong`-Methode sind Anforderung/Antwort-Methoden. Der erste Aufruf von `Ping` wird daher erst zurückgegeben, wenn der Aufruf von `CallbackChannel<T>.Pong()` zurückgegeben wurde. Auf dem Client kann die `Pong`-Methode erst zurückgegeben werden, wenn der nächste `Ping`-Aufruf, den sie vorgenommen hat, zurückgegeben wurde. Da der Rückruf und der Dienst ausgehende Anforderung/Antwort-Aufrufe ausführen müssen, damit sie für die ausstehende Anforderung antworten können, müssen beide Implementierungen mit dem ConcurrencyMode.Reentrant-Verhalten gekennzeichnet werden.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Erstellen Sie zum Ausführen des Beispiels das Client- und Serverprojekt. Öffnen Sie dann zwei Befehlsfenster, und ändern Sie die Verzeichnisse in das \<Beispiel > \CS\Service\bin\debug und \<Sample > \CS\Client\bin\debug Directories. Starten Sie dann den Dienst, indem Sie `service.exe` eingeben und dann "Client. exe" aufrufen, wobei der anfängliche Wert von Ticks als Eingabe Argument weitergegeben wurde. Es wird eine Beispielausgabe für 10 Ticks veranschaulicht.  
  
```console  
Prompt>Service.exe  
ServiceHost Started. Press Enter to terminate service.  
Ping: Ticks = 10  
Ping: Ticks = 8  
Ping: Ticks = 6  
Ping: Ticks = 4  
Ping: Ticks = 2  
Ping: Ticks = 0  
  
Prompt>Client.exe 10  
Pong: Ticks = 9  
Pong: Ticks = 7  
Pong: Ticks = 5  
Pong: Ticks = 3  
Pong: Ticks = 1  
```  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Reentrant`  
