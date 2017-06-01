---
title: "Standardnachrichtenvertrag | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Nachrichtenvertrag"
ms.assetid: 5a200b78-1a46-4104-b7fb-da6dbab33893
caps.latest.revision: 35
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 35
---
# Standardnachrichtenvertrag
Das Beispiel zum Standardnachrichtenvertrag zeigt einen Dienst, bei dem eine benutzerdefinierte Nachricht an und aus Dienstvorgängen übergeben wird.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das eine Rechnerschnittstelle als einen typisierten Dienst implementiert.Anstelle der im [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md) verwendeten einzelnen Dienstvorgänge für Addition, Substraktion, Multiplikation und Division übergibt dieses Beispiel eine benutzerdefinierte Nachricht, die die Operanden und den Operator enthält, und gibt das Ergebnis der arithmetischen Berechnung zurück.  
  
 Der Client ist ein Konsolenprogramm \(.exe\), und die Dienstbibliothek \(.dll\) wird von IIS \(Internet Information Services, Internetinformationsdienste\) gehostet.Die Clientaktivität ist im Konsolenfenster sichtbar.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In dem Dienst ist ein Dienstvorgang definiert, der benutzerdefinierte Nachrichten vom Typ `MyMessage` entgegennimmt und zurückgibt.Auch wenn im vorliegenden Beispiel die Anforderung\- und Antwortnachrichten vom selben Typ sind, können sie natürlich auch unterschiedliche Nachrichtenverträge sein, falls erforderlich.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract(Action="http://test/MyMessage_action",  
                  ReplyAction="http://test/MyMessage_action")]  
    MyMessage Calculate(MyMessage request);  
}  
  
```  
  
 Die benutzerdefinierte `MyMessage`\-Nachricht wird in einer mit <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>\- und <xref:System.ServiceModel.MessageBodyMemberAttribute>\-Attributen kommentierten Klasse definiert.In diesem Beispiel wird nur der dritte Konstruktor verwendet.Mithilfe von Nachrichtenverträgen können Sie die volle Kontrolle über die SOAP\-Nachricht ausüben.In diesem Beispiel wird mit dem <xref:System.ServiceModel.MessageHeaderAttribute>\-Attribut `Operation` in einem SOAP\-Header platziert.Die Operanden `N1` und `N2` sowie das `Result` werden im SOAP\-Text angezeigt, da auf sie das <xref:System.ServiceModel.MessageBodyMemberAttribute>\-Attribut angewendet ist.  
  
```  
[MessageContract]  
public class MyMessage  
{  
    private string operation;  
    private double n1;  
    private double n2;  
    private double result;  
  
    //Constructor - create an empty message.  
  
    public MyMessage() {}  
  
    //Constructor - create a message and populate its members.  
  
    public MyMessage(double n1, double n2, string operation,   
                     double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    //Constructor - create a message from another message.  
  
    public MyMessage(MyMessage message)  
    {  
        this.n1 = message.n1;  
        this.n2 = message.n2;  
        this.operation = message.operation;  
        this.result = message.result;  
    }  
  
    [MessageHeader]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [MessageBodyMember]  
    public double N1  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [MessageBodyMember]  
    public double N2  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [MessageBodyMember]  
    public double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
}  
```  
  
 Die Implementierungsklasse enthält den Code für den `Calculate`\-Dienstvorgang.Die `CalculateService`\-Klasse ermittelt die Operanden und den Operator aus der Anforderungsnachricht und erstellt eine Antwortnachricht, die das Ergebnis der angeforderten Berechnung enthält, wie im folgenden Code dargestellt.  
  
```  
// Service class which implements the service contract.  
public class CalculatorService : ICalculator  
{  
    // Perform a calculation.  
  
    public MyMessage Calculate(MyMessage request)  
    {  
        MyMessage response = new MyMessage(request);  
        switch (request.Operation)  
        {  
            case "+":  
                response.Result = request.N1 + request.N2;  
                break;  
            case "-":  
                response.Result = request.N1 - request.N2;  
                break;  
            case "*":  
                response.Result = request.N1 * request.N2;  
                break;  
            case "/":  
                response.Result = request.N1 / request.N2;  
                break;  
            default:  
                response.Result = 0.0D;  
                break;  
        }  
        return response;  
    }  
}  
```  
  
 Der generierte Clientcode für den Client wurde mit dem [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) erstellt.Wenn erforderlich, erstellt das Tool automatisch Nachrichtenvertragstypen im generierten Clientcode.Die `/messageContract`\-Befehlsoption kann angegeben werden, um die Generierung von Nachrichtenverträgen zu erzwingen.  
  
```  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" /o:client\generatedClient.cs http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 Das folgende Codebeispiel zeigt den Client mit der `MyMessage`\-Nachricht.  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
// Perform addition using a typed message.  
  
MyMessage request = new MyMessage();  
request.N1 = 100D;  
request.N2 = 15.99D;  
request.Operation = "+";  
MyMessage response = ((ICalculator)client).Calculate(request);  
Console.WriteLine("Add({0},{1}) = {2}", request.N1, request.N2, response.Result);  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Berechnungen im Clientkonsolenfenster angezeigt.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
  
```  
  
 An dieser Stelle wurden benutzerdefinierte Nachrichten zwischen dem Client und dem Dienstvorgang übergeben.Der Nachrichtenvertrag hat definiert, dass sich die Operanden und Ergebnisse im Nachrichtentextteil und der Operator in einem Nachrichtenheader befinden.Zum Betrachten dieser Nachrichtenstruktur kann Nachrichtenprotokollierung konfiguriert werden.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Default`  
  
## Siehe auch