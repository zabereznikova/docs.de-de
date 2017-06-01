---
title: "Kanalfactory | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Kanalfactory
In diesem Beispiel wird veranschaulicht, wie eine Clientanwendung einen Kanal mit der <xref:System.ServiceModel.ChannelFactory>\-Klasse und nicht mit einem generierten Client erstellen kann.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das einen Rechnerdienst implementiert.  
  
> [!NOTE]
>  Die Setupprozedur und Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird mithilfe der <xref:System.ServiceModel.ChannelFactory%601>\-Klasse ein Kanal für einen Dienstendpunkt erstellt.Normalerweise generieren Sie zum Erstellen eines Kanals zu einem Dienstendpunkt einen Clienttyp mit dem [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) und erstellen eine Instanz des generierten Typs.Sie können einen Kanal auch mithilfe der <xref:System.ServiceModel.ChannelFactory%601>\-Klasse erstellen, wie in diesem Beispiel dargestellt.Der im folgenden Beispielcode erstellte Dienst stimmt mit dem Dienst in [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md) überein.  
  
```  
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
WSHttpBinding binding = new WSHttpBinding();  
ChannelFactory<ICalculator> factory = new   
                    ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = factory.CreateChannel();  
```  
  
> [!IMPORTANT]
>  Wenn Sie dieses Beispiel in einem Szenario computerübergreifend ausführen, müssen Sie "localhost" im oben stehenden Code durch den vollqualifizierten Namen des Computers ersetzen, auf dem der Dienst ausgeführt wird.Im Beispiel wird die Endpunktadresse nicht in der Konfiguration festgelegt, daher muss dies im Code erfolgen.  
  
 Nach dem Erstellen des Kanals können Dienstvorgänge wie bei einem generierten Client aufgerufen werden.  
  
```  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
```  
  
 Zum Schließen des Kanals muss dieser zunächst in eine <xref:System.ServiceModel.IClientChannel>\-Schnittstelle umgewandelt werden.Dies ist erforderlich, da der Kanal wie generiert in der Clientanwendung mit der `ICalculator`\-Schnittstelle deklariert wird. Diese verfügt über Methoden wie `Add` und `Subtract`, nicht jedoch über `Close`.Die `Close`\-Methode stammt aus der <xref:System.ServiceModel.ICommunicationObject>\-Schnittstelle.  
  
```  
// Close the channel.  
 ((IClientChannel)client).Close();  
  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.Drücken Sie im Clientfenster die EINGABETASTE, um die Clientanwendung zu schließen.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Version der Lösung folgen Sie den unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.Beachten Sie, dass das Veröffentlichen von Metadaten in diesem Beispiel nicht aktiviert wird.Sie müssen zuerst das Veröffentlichen von Metadaten aktivieren, damit der Clienttyp in diesem Beispiel erneut generiert wird.  
  
3.  Wenn Sie das Beispiel in einer Konfiguration mit einem Computer oder über Computer hinweg ausführen möchten, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### So führen Sie das Beispiel computerübergreifend aus  
  
1.  Ersetzen Sie "localhost" im folgenden Code durch den vollqualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird.  
  
    ```  
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
    ```  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`  
  
## Siehe auch