---
title: "ASMX-Client mit einem WCF-Dienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# ASMX-Client mit einem WCF-Dienst
Dieses Beispiel zeigt, wie ein Dienst erstellt wird, der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet, und wie dann aus einem Nicht\-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client \(wie einem ASMX\-Client\) auf den Dienst zugegriffen wird.  
  
> [!NOTE]
>  Die Setupprozedur und Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel besteht aus einem Clientkonsolenprogramm \(.exe\) und einer von IIS \(Internet Information Services, Internetinformationsdienste\) gehosteten Dienstbibliothek \(.dll\).Der Dienst implementiert einen Vertrag, der ein Anforderungs\-Antwort\-Kommunikationsmuster definiert.Der Vertrag wird durch die `ICalculator`\-Schnittstelle definiert, die mathematische Operationen \(`Add`, `Subtract`, `Multiply` und `Divide`\) verfügbar macht.Der ASMX\-Client stellt synchrone Anforderungen an eine mathematische Operation, und der Dienst antwortet mit dem Ergebnis.  
  
 Der Dienst implementiert einen `ICalculator`\-Vertrag, wie im folgenden Code definiert.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
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
}  
  
```  
  
 <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Xml.Serialization.XmlSerializer> ordnen CLR\-Typen einer XML\-Darstellung zu.Der <xref:System.Runtime.Serialization.DataContractSerializer> übersetzt einige XML\-Darstellungen anders als XmlSerializer.Nicht\-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Proxygeneratoren \(wie Wsdl.exe\) generieren bei Verwendung des XmlSerializer eine Schnittstelle, die sich bequemer verwenden lässt.Das <xref:System.ServiceModel.XmlSerializerFormatAttribute> wird auf die `ICalculator` \-Schnittstelle angewendet, um sicherzustellen, dass der XmlSerializer zum Zuordnen von CLR\-Typen zu XML verwendet wird.Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück.  
  
 Der Dienst macht einen einzigen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit einer Konfigurationsdatei \(Web.conf\) definiert wird.Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.Der Dienst macht den Endpunkt bei der vom IIS\-Host bereitgestellten Basisadresse verfügbar.Das `binding`\-Attribut wird auf basicHttpBinding festgelegt, was die HTTP\-Kommunikation über SOAP 1.1 ermöglicht, das mit WS\-I BasicProfile 1.1 kompatibel ist, wie in der folgenden Beispielkonfiguration dargestellt.  
  
```  
<services>  
   <service   
       name="Microsoft.ServiceModel.Samples.CalculatorService"  
       behaviorConfiguration="CalculatorServiceBehavior">  
       <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->  
      <endpoint address=""  
               binding="basicHttpBinding"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
</services>  
  
```  
  
 Der ASMX\-Client kommuniziert mit dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst mittels eines typisierten Proxys, der von dem WSDL\-Dienstprogramm \(Web Services Description Language\) Wsdl.exe generiert wird.Der typisierte Proxy ist in der Datei generatedClient.cs enthalten.Das WSDL\-Dienstprogramm ruft Metadaten für den angegebenen Dienst ab und generiert einen typisierten Proxy, den ein Client zur Kommunikation verwenden kann.Standardmäßig macht das Framework keine Metadaten verfügbar.Wenn Sie die Metadaten verfügbar machen möchten, die erforderlich sind, um einen Proxy zu generieren, müssen Sie ein [\<serviceMetadata\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) hinzufügen und dessen `httpGetEnabled`\-Attribute auf `True` festlegen, wie in der folgenden Konfiguration gezeigt.  
  
```  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- Setting httpGetEnabled to True on the serviceMetadata  
           behavior exposes the service's wsdl at <base address>?wsdl :  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Führen Sie den folgenden Befehl an einer Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren.  
  
```  
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl  
  
```  
  
 Unter Verwendung des generierten typisierten Proxys kann der Client auf einen bestimmten Endpunkt zugreifen, indem er die entsprechende Adresse konfiguriert.Der Client gibt den Endpunkt, mit dem er kommunizieren möchte, mithilfe einer Konfigurationsdatei \(App.config\) an.  
  
```  
<appSettings>  
      <add key="CalculatorServiceAddress"   
      value="http://localhost/ServiceModelSamples/service.svc"/>  
</appSettings>  
  
```  
  
 Die Clientimplementierung erstellt eine Instanz des typisierten Proxys, um die Kommunikation mit dem Dienst zu beginnen.  
  
```  
// Create a client to the CalculatorService.  
using (CalculatorService client = new CalculatorService())  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation.  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Multiply service operation.  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
}  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
  
```  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Wenn Sie das Beispiel in einer Konfiguration mit einem Computer oder über Computer hinweg ausführen möchten, folgen Sie den unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Übergeben und Zurückgeben von komplexen Datentypen finden Sie unter: [Datenbindung in einem Windows Forms\-Client](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [Datenbindung in einem Windows Presentation Foundation\-Client](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md) und [Datenbindung in einem ASP.NET\-Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`  
  
## Siehe auch