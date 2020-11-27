---
title: Nicht typisierte Request-Reply
ms.date: 03/30/2017
ms.assetid: 0bf0f9d9-7caf-4d3d-8c9e-2d468cca16a5
ms.openlocfilehash: bcd35bcac928397cad57384fdecb55d7e5ad13c3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294988"
---
# <a name="untyped-requestreply"></a>Nicht typisierte Anforderung/Antwort

In diesem Beispiel wird das Definieren von Vorgangsverträgen veranschaulicht, die die Message-Klasse verwenden.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten. Der Dienstvertrag definiert einen Vorgang, der einen Nachrichtentyp als Argument annimmt und eine Nachricht zurückgibt. Der Vorgang erfasst alle erforderlichen Daten zum Berechnen der Summe aus dem Nachrichtentext und sendet die Summe dann als Nachrichtentext in der Rückgabeantwort.  
  
```csharp
[OperationContract(Action = CalculatorService.RequestAction, ReplyAction = CalculatorService.ReplyAction)]  
Message ComputeSum(Message request);  
```  
  
 Im Dienst ruft der Vorgang das Array von ganzen Zahlen ab, das in der Eingabenachricht übergeben wurde, und berechnet dann die Summe. Zum Senden einer Antwortnachricht wird im Beispiel eine neue Nachricht mit der entsprechenden Nachrichtenversion und Aktion erstellt, und die berechnete Summe wird als Nachrichtentext hinzugefügt. Dies wird im folgenden Beispielcode veranschaulicht.  
  
```csharp
public Message ComputeSum(Message request)  
{  
    //The body of the message contains a list of numbers which will be
    //read as a int[] using GetBody<T>  
    int result = 0;  
  
    int[] inputs = request.GetBody<int[]>();  
    foreach (int i in inputs)  
    {  
        result += i;  
    }  
  
    Message response = Message.CreateMessage(request.Version,
                                      ReplyAction, result);  
    return response;  
}  
```  
  
 Der Client verwendet Code, der vom [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) generiert wird, um einen Proxy für den Remote Dienst zu erstellen. Zum Senden einer Anforderungsnachricht muss der Client über die Nachrichtenversion verfügen, die vom zugrunde liegenden Kanal abhängig ist. Daher wird ein neuer <xref:System.ServiceModel.OperationContextScope> erstellt, der auf den erstellten Proxykanal festgelegt ist. Dieser erstellt einen <xref:System.ServiceModel.OperationContext>, bei dem die richtige Nachrichtenversion in der `OutgoingMessageHeaders.MessageVersion`-Eigenschaft angegeben ist. Der Client übergibt ein Eingabearray als Nachrichtentext an die Anforderungsnachricht und ruft dann `ComputeSum` beim Proxy auf. Der Client ruft dann die Summe der übergebenen Eingaben ab, indem auf die `GetBody<T>`-Methode der Antwortnachricht zugegriffen wird. Dies wird im folgenden Beispielcode veranschaulicht.  
  
```csharp
using (new OperationContextScope(client.InnerChannel))  
{  
    // Call the Sum service operation.  
    int[] values = { 1, 2, 3, 4, 5 };  
    Message request = Message.CreateMessage(  
        OperationContext.Current.OutgoingMessageHeaders.MessageVersion,
        RequestAction, values);  
    Message reply = client.ComputeSum(request);  
    int response = reply.GetBody<int>();  
  
    Console.WriteLine("Sum of numbers passed (1,2,3,4,5) = {0}",
                                                       response);  
}  
```  
  
 Dieses Beispiel ist ein im Web gehostetes Beispiel. Es muss daher nur die ausführbare Datei für den Client ausgeführt werden. Im Folgenden finden Sie die Beispielausgabe auf dem Client.  
  
```console  
Prompt>Client.exe  
Sum of numbers passed (1,2,3,4,5) = 15  
  
Press <ENTER> to terminate client.  
```  
  
 Dieses Beispiel ist ein im Web gehostetes Beispiel. Überprüfen Sie daher den Link in Schritt 3, um Informationen zum Erstellen und Ausführen des Beispiels zu erhalten.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Untyped`  
