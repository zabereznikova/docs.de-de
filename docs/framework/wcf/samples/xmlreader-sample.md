---
title: XmlReader-Beispiel
ms.date: 03/30/2017
helpviewer_keywords:
- XML Reader
ms.assetid: 60e5848d-7d9c-4ea5-bed9-22758c9ac16c
ms.openlocfilehash: bb1cd02a60ec0ba62e1d0d9aa3560bbba0aaf668
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714539"
---
# <a name="xmlreader-sample"></a>XmlReader-Beispiel

Das XmlReader-Beispiel zeigt die Verarbeitung eines Nachrichtentexts mit einem <xref:System.Xml.XmlReader>. Das Beispiel basiert auf dem ersten [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), der einen Rechner Dienst implementiert. Ein weiterer Dienstvorgang wurde hingefügt (`Sum`), der Nachrichten mit einem Array von Werten entgegennimmt, die miteinander addiert werden sollen. Der Dienst liest die Nachricht mit einem <xref:System.Xml.XmlReader>.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Die Rechnerschnittstelle enthält einen Dienstvorgang namens `Sum`, der einen <xref:System.ServiceModel.Channels.Message>-Parameter entgegennimmt, wie im folgenden Beispielcode gezeigt.

```csharp
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
    [OperationContract]
    Message Sum(Message message);
}
```

Der Client greift auf `Sum` zu, indem er zuerst ein Array von ganzzahligen Werten erstellt, dann eine Nachricht aus dem Array erstellt und anschließend die `Sum`-Methode mit der erstellten Nachricht aufruft, wie im folgenden Beispielcode gezeigt.

```csharp
CalculatorClient client = new CalculatorClient();
//...

// Call the Sum service operation.
int[] values = { 1, 2, 3, 4, 5 };
using (new OperationContextScope(client.InnerChannel))
{
    Message request = Message.CreateMessage(OperationContext.Current.OutgoingMessageHeaders.MessageVersion, "http://Microsoft.ServiceModel.Samples/ICalculator/Sum", values);
    Message reply = client.Sum(request);
    int sum = reply.GetBody<int>();

    Console.WriteLine("Sum(1,2,3,4,5) = {0}", sum);
}
```

Im Dienst greift die Implementierung des Dienstvorgangs `Sum` mithilfe eines <xref:System.Xml.XmlReader>-Objekts auf den Nachrichtentext zu, um die zu summierenden Werte zu durchlaufen. Die <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>-Methode wird aufgerufen, um auf den Nachrichtentext zuzugreifen, wie im folgenden Beispielcode gezeigt.

```csharp
public int Sum(Message message)
{
    int sum = 0;
    string text = "";

    //The body of the message contains a list of numbers that are read
    //directly using an XmlReader.
    XmlReader body = message.GetReaderAtBodyContents ();
    while (body.Read())
    {
        text = body.ReadString().Trim();
        if (text.Length>0)
        {
            sum += Convert.ToInt32(text);
        }
    }
    body.Close();
    Message response = Message.CreateMessage(
       "http://Microsoft.ServiceModel.Samples/ICalculator/SumResponse",
       sum);
    return response;
}
```

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten des Vorgangs im Konsolenfenster des Clients angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Sum(1,2,3,4,5) = 15

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\XmlReader`
