---
title: IIS-Hosting mithilfe von Inlinecode
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 47d056e35b92654c8e47647c7273c5d69b37bd97
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594646"
---
# <a name="iis-hosting-using-inline-code"></a>IIS-Hosting mithilfe von Inlinecode

Dieses Beispiel zeigt, wie ein von IIS (Internet Information Services, Internetinformationsdienste) gehosteter Dienst implementiert wird, bei dem der Code sich inline in einer SVC-Datei befindet und bei Bedarf kompiliert wird. Dienstcode kann auch direkt in Quellcodedateien, die sich im Verzeichnis \App_Code der Anwendung befinden, oder in einer unter \bin bereitgestellten Assembly implementiert werden. Diese Techniken werden im vorliegenden Beispiel nicht veranschaulicht.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

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

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

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

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.

3. Nachdem die Projekt Mappe erstellt wurde, führen Sie Setup. bat aus, um die Service Model Samples-Anwendung in IIS 7,0 einzurichten. Das Verzeichnis Service Model Samples sollte jetzt als IIS 7,0-Anwendung angezeigt werden.

4. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md). Ein Beispiel zum Erstellen einer Client Anwendung, die diesen Dienst aufruft, finden Sie unter Gewusst [wie: Erstellen eines Clients](../how-to-create-a-wcf-client.md).

## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Hosting- und -Persistenzbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
