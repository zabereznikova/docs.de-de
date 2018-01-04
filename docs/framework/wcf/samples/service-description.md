---
title: Dienstbeschreibung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 043172f854c6165019517a1a48f8d41e632afa52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="service-description"></a>Dienstbeschreibung
Im Beispiel "Dienstbeschreibung" wird veranschaulicht, wie ein Dienst seine Dienstbeschreibungsinformationen zur Laufzeit abrufen kann. Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), mit einer zusätzlichen Dienstvorgang definiert, um beschreibende Informationen zum Dienst zurückzugeben. Die zurückgegebenen Informationen enthalten die Basisadressen und Endpunkte für den Dienst. Der Dienst stellt diese Informationen mithilfe der Klassen <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> und <xref:System.ServiceModel.Description.ServiceDescription> bereit.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel enthält eine geänderte Version des Rechnervertrags mit der Bezeichnung `IServiceDescriptionCalculator`. Der Vertrag definiert einen zusätzlichen Dienstvorgang mit der Bezeichnung `GetServiceDescriptionInfo`, über den eine mehrzeilige Zeichenfolge an den Client zurückgegeben wird, die die Basisadressen oder die Adressen und Dienstendpunkte oder die Endpunkte für den Dienst beschreibt.  
  
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
  
 Im Implementierungscode für `GetServiceDescriptionInfo` wird <xref:System.ServiceModel.Description.ServiceDescription> verwendet, um die Dienstendpunkte aufzulisten. Da Dienstendpunkte relative Adressen haben können, werden zuerst die Basisadressen für den Dienst aufgelistet. Der Code ruft seinen Vorgangskontext mithilfe von <xref:System.ServiceModel.OperationContext.Current%2A> ab, um all diese Informationen zu erhalten. Der <xref:System.ServiceModel.ServiceHost> und sein <xref:System.ServiceModel.Description.ServiceDescription>-Objekt werden aus dem Vorgangskontext abgerufen. Um die Basisendpunkte für den Dienst aufzulisten, durchläuft der Code die Auflistung mit <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> des Diensthosts. Um die Dienstendpunkte für den Dienst aufzulisten, durchläuft der Code die Auflistung mit Endpunkten in der Dienstbeschreibung.  
  
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
  
 Bei der Ausführung des Beispiels werden die Rechnervorgänge und dann die vom `GetServiceDescriptionInfo`-Vorgang zurückgegebenen Dienstinformationen angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
  
## <a name="see-also"></a>Siehe auch
