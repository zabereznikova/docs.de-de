---
title: "Dienstbeschreibung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Dienstbeschreibung
Im Beispiel "Dienstbeschreibung" wird veranschaulicht, wie ein Dienst seine Dienstbeschreibungsinformationen zur Laufzeit abrufen kann.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), es definiert jedoch einen zusätzlichen Dienstvorgang zur Rückgabe beschreibender Informationen über den Dienst.Die zurückgegebenen Informationen enthalten die Basisadressen und Endpunkte für den Dienst.Der Dienst stellt diese Informationen mithilfe der Klassen <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> und <xref:System.ServiceModel.Description.ServiceDescription> bereit.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung \(.exe\), und der Dienst wird von Internetinformationsdiensten \(IIS\) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Abschnitts.  
  
 Dieses Beispiel enthält eine geänderte Version des Rechnervertrags mit der Bezeichnung `IServiceDescriptionCalculator`.Der Vertrag definiert einen zusätzlichen Dienstvorgang mit der Bezeichnung `GetServiceDescriptionInfo`, über den eine mehrzeilige Zeichenfolge an den Client zurückgegeben wird, die die Basisadressen oder die Adressen und Dienstendpunkte oder die Endpunkte für den Dienst beschreibt.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
  
```  
  
 Im Implementierungscode für `GetServiceDescriptionInfo` wird <xref:System.ServiceModel.Description.ServiceDescription> verwendet, um die Dienstendpunkte aufzulisten.Da Dienstendpunkte relative Adressen haben können, werden zuerst die Basisadressen für den Dienst aufgelistet.Der Code ruft seinen Vorgangskontext mithilfe von <xref:System.ServiceModel.OperationContext.Current%2A> ab, um all diese Informationen zu erhalten.Der <xref:System.ServiceModel.ServiceHost> und sein <xref:System.ServiceModel.Description.ServiceDescription>\-Objekt werden aus dem Vorgangskontext abgerufen.Um die Basisendpunkte für den Dienst aufzulisten, durchläuft der Code die Auflistung mit <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> des Diensthosts.Um die Dienstendpunkte für den Dienst aufzulisten, durchläuft der Code die Auflistung mit Endpunkten in der Dienstbeschreibung.  
  
```  
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
  
```  
  
 Bei der Ausführung des Beispiels werden die Rechnervorgänge und dann die vom `GetServiceDescriptionInfo`\-Vorgang zurückgegebenen Dienstinformationen angezeigt.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
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
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
  
## Siehe auch