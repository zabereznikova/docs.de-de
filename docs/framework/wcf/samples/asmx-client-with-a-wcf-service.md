---
title: ASMX-Client mit einem WCF-Dienst
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: 63938f866083dac56d6ef43fdd8757c60b9a2f2b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835153"
---
# <a name="asmx-client-with-a-wcf-service"></a>ASMX-Client mit einem WCF-Dienst
Dieses Beispiel veranschaulicht das Erstellen eines Diensts mithilfe von Windows Communication Foundation (WCF), und klicken Sie dann auf den Dienst zugreifen, von einem nicht-WCF-Client, z. B. eine ASMX-Client.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (.dll). Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird durch die `ICalculator`-Schnittstelle definiert, die mathematische Operationen (`Add`, `Subtract`, `Multiply` und `Divide`) verfügbar macht. Der ASMX-Client stellt synchrone Anforderungen an eine mathematische Operation, und der Dienst antwortet mit dem Ergebnis.  
  
 Der Dienst implementiert einen `ICalculator`-Vertrag, wie im folgenden Code definiert.  
  
```csharp  
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
  
 <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Xml.Serialization.XmlSerializer> ordnen CLR-Typen einer XML-Darstellung zu. Der <xref:System.Runtime.Serialization.DataContractSerializer> übersetzt einige XML-Darstellungen anders als XmlSerializer. Nicht-WCF-Proxy-Generatoren wie Wsdl.exe, generieren eine Schnittstelle, wenn das XmlSerializer-Element verwendet wird. Die <xref:System.ServiceModel.XmlSerializerFormatAttribute> gilt, an die `ICalculator` -Schnittstelle, um sicherzustellen, dass das XmlSerializer-Element zum Zuordnen von CLR-Typen zu XML verwendet wird. Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück.  
  
 Der Dienst macht einen einzigen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit einer Konfigurationsdatei (Web.conf) definiert wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Der Dienst macht den Endpunkt bei der vom IIS-Host bereitgestellten Basisadresse verfügbar. Das `binding`-Attribut wird auf basicHttpBinding festgelegt, was die HTTP-Kommunikation über SOAP 1.1 ermöglicht, das mit WS-I BasicProfile 1.1 kompatibel ist, wie in der folgenden Beispielkonfiguration dargestellt.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->  
    <endpoint address=""  
              binding="basicHttpBinding"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </service>  
</services>  
```  
  
 Der ASMX-Client kommuniziert mit den WCF-Dienst mittels eines typisierten Proxys, das vom Hilfsprogramm Web Services Description Language (WSDL) (Wsdl.exe) generiert wird. Der typisierte Proxy ist in der Datei generatedClient.cs enthalten. Das WSDL-Dienstprogramm ruft Metadaten für den angegebenen Dienst ab und generiert einen typisierten Proxy, den ein Client zur Kommunikation verwenden kann. Standardmäßig macht das Framework keine Metadaten verfügbar. Zum Verfügbarmachen von Metadaten erforderlich, um den Proxy zu generieren, müssen Sie hinzufügen, eine [ \<ServiceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) und legen Sie dessen `httpGetEnabled` Attribut `True` wie in der folgenden Konfiguration gezeigt.  
  
```xml  
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
  
```console  
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl  
```  
  
 Unter Verwendung des generierten typisierten Proxys kann der Client auf einen bestimmten Endpunkt zugreifen, indem er die entsprechende Adresse konfiguriert. Der Client gibt den Endpunkt, mit dem er kommunizieren möchte, mithilfe einer Konfigurationsdatei (App.config) an.  
  
```xml  
<appSettings>  
  <add key="CalculatorServiceAddress"   
       value="http://localhost/ServiceModelSamples/service.svc"/>  
</appSettings>  
```  
  
 Die Clientimplementierung erstellt eine Instanz des typisierten Proxys, um die Kommunikation mit dem Dienst zu beginnen.  
  
```csharp
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
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console 
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!NOTE]
>  Finden Sie weitere Informationen zu übergeben und Zurückgeben von komplexen Typen aus: [Die Datenbindung in einer Windows Forms-Client](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [Datenbindung in einem Windows Presentation Foundation-Client](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md), und [Datenbindung in einem ASP.NET-Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`  
  
