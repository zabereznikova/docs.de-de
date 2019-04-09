---
title: IIS-Hosting mithilfe von Inlinecode
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 4fa4c7ff92252733fcff65e4fc3ab3c6b3624181
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186887"
---
# <a name="iis-hosting-using-inline-code"></a>IIS-Hosting mithilfe von Inlinecode
Dieses Beispiel zeigt, wie ein von IIS (Internet Information Services, Internetinformationsdienste) gehosteter Dienst implementiert wird, bei dem der Code sich inline in einer SVC-Datei befindet und bei Bedarf kompiliert wird. Dienstcode kann auch direkt in Quellcodedateien, die sich im Verzeichnis \App_Code der Anwendung befinden, oder in einer unter \bin bereitgestellten Assembly implementiert werden. Diese Techniken werden im vorliegenden Beispiel nicht veranschaulicht.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`  
  
 In diesem Beispiel wird ein typischer Dienst gezeigt, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Dienst wird in IIS gehostet, und der gesamte Dienstcode befindet sich in der Datei "Service.svc". Der Dienst wird vom Host aktiviert und erst dann kompiliert, wenn die erste Nachricht an den Dienst gesendet wird. Eine Vorkompilierung ist nicht erforderlich. Der Dienst implementiert einen `ICalculator`-Vertrag, wie im folgenden Code definiert:  
  
```csharp
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
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
  
 Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück.  
  
```svc
<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>   
```
```csharp
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
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
  
3.  Nachdem die Projektmappe erstellt wurde, führen Sie setup.bat aus, um die ServiceModelSamples-Anwendung in [!INCLUDE[iisver](../../../../includes/iisver-md.md)] einzurichten. Das Verzeichnis ServiceModelSamples sollte jetzt als [!INCLUDE[iisver](../../../../includes/iisver-md.md)]-Anwendung angezeigt werden.  
  
4.  Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md). Ein Beispiel zum Erstellen einer Clientanwendung, die diesen Dienst aufrufen kann, finden Sie unter [Vorgehensweise: Erstellen Sie einen Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
## <a name="see-also"></a>Siehe auch

- [AppFabric-Hosting- und -Persistenzbeispiele](https://go.microsoft.com/fwlink/?LinkId=193961)
