---
title: "Nicht typisierte Anforderung/Antwort | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0bf0f9d9-7caf-4d3d-8c9e-2d468cca16a5
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Nicht typisierte Anforderung/Antwort
In diesem Beispiel wird das Definieren von Vorgangsverträgen veranschaulicht, die die Message\-Klasse verwenden.  
  
> [!NOTE]
>  Die Setupprozedur und Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).Der Dienstvertrag definiert einen Vorgang, der einen Nachrichtentyp als Argument annimmt und eine Nachricht zurückgibt.Der Vorgang erfasst alle erforderlichen Daten zum Berechnen der Summe aus dem Nachrichtentext und sendet die Summe dann als Nachrichtentext in der Rückgabeantwort.  
  
```  
  
[OperationContract(Action = CalculatorService.RequestAction, ReplyAction = CalculatorService.ReplyAction)]  
Message ComputeSum(Message request);  
  
```  
  
 Im Dienst ruft der Vorgang das Array von ganzen Zahlen ab, das in der Eingabenachricht übergeben wurde, und berechnet dann die Summe.Zum Senden einer Antwortnachricht wird im Beispiel eine neue Nachricht mit der entsprechenden Nachrichtenversion und Aktion erstellt, und die berechnete Summe wird als Nachrichtentext hinzugefügt.Dies wird im folgenden Beispielcode veranschaulicht.  
  
```  
  
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
  
 Der Client verwendet von [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generierten Code zum Erstellen eines Proxys für den Remotedienst.Zum Senden einer Anforderungsnachricht muss der Client über die Nachrichtenversion verfügen, die vom zugrunde liegenden Kanal abhängig ist.Daher wird ein neuer <xref:System.ServiceModel.OperationContextScope> erstellt, der auf den erstellten Proxykanal festgelegt ist. Dieser erstellt einen <xref:System.ServiceModel.OperationContext>, bei dem die richtige Nachrichtenversion in der `OutgoingMessageHeaders.MessageVersion`\-Eigenschaft angegeben ist.Der Client übergibt ein Eingabearray als Nachrichtentext an die Anforderungsnachricht und ruft dann `ComputeSum` beim Proxy auf.Der Client ruft dann die Summe der übergebenen Eingaben ab, indem auf die `GetBody<T>`\-Methode der Antwortnachricht zugegriffen wird.Dies wird im folgenden Beispielcode veranschaulicht.  
  
```  
  
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
  
 Dieses Beispiel ist ein im Web gehostetes Beispiel. Es muss daher nur die ausführbare Datei für den Client ausgeführt werden.Im Folgenden finden Sie die Beispielausgabe auf dem Client.  
  
```  
  
Prompt>Client.exe  
Sum of numbers passed (1,2,3,4,5) = 15  
  
Press <ENTER> to terminate client.  
  
```  
  
 Dieses Beispiel ist ein im Web gehostetes Beispiel. Überprüfen Sie daher den Link in Schritt 3, um Informationen zum Erstellen und Ausführen des Beispiels zu erhalten.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Untyped`  
  
## Siehe auch